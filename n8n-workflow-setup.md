# n8n Workflow Setup: Deviation & CAPA Assistant

## Overview

4 nodes in a straight line:

```
Webhook → Code (format input) → OpenAI → Respond to Webhook
```

---

## Node 1: Webhook

- **Type:** Webhook
- **HTTP Method:** POST
- **Path:** `deviation-analysis` (or whatever you want; this determines your URL)
- **Response Mode:** "Using 'Respond to Webhook' Node" (CRITICAL: do not use "Immediately" or "Last Node")
- **Options → Add Option → Allowed Origins (CORS):** `*` (allows your GitHub Pages site to call it)

Once saved and activated, n8n gives you the **Production URL**. It looks like:
```
https://your-n8n-instance.app.n8n.cloud/webhook/deviation-analysis
```

Copy that URL into your `index.html` where it says `YOUR_N8N_WEBHOOK_URL_HERE`.

---

## Node 2: Code (Format Input)

- **Type:** Code
- **Language:** JavaScript
- **Mode:** Run Once for All Items

Paste this code:

```javascript
const input = $input.first().json;

const userMessage = `## Deviation Input

**Event Description:** ${input.event_description}

**Discovery Date/Time:** ${input.discovery_date}

**Product/Batch:** ${input.product_batch}

**Process Step:** ${input.process_step}

**Expected Parameter:** ${input.expected_parameter}

**Observed Value:** ${input.observed_value}

**Immediate Actions Taken:** ${input.immediate_actions}`;

return [{
  json: {
    userMessage
  }
}];
```

---

## Node 3: OpenAI

- **Type:** OpenAI (the built-in n8n node, not HTTP Request)
- **Credential:** Your OpenAI API key (add it under Credentials if you haven't)
- **Resource:** Chat
- **Operation:** Send Message (or "Complete")
- **Model:** `gpt-4.1` (or whatever model you have access to that performs well)

### System Prompt

Paste the ENTIRE contents of `system-prompt.md` into the System Prompt field. That's the full system prompt starting with "You are a pharmaceutical quality deviation analysis assistant..."

### User Message

Set to **Expression** mode (click the toggle next to the field), then enter:

```
{{ $json.userMessage }}
```

### Options

- **Max Tokens:** 4096
- **Temperature:** 0.3 (low temperature for consistent, structured output)

---

## Node 4: Code (Format Output as HTML)

- **Type:** Code
- **Language:** JavaScript
- **Mode:** Run Once for All Items

This converts the markdown response into styled HTML that matches your page design.

Paste this code:

```javascript
const raw = $input.first().json.message?.content 
  || $input.first().json.text 
  || $input.first().json.content
  || '';

function mdToHtml(md) {
  let html = '';
  const lines = md.split('\n');
  let sectionNum = 0;
  let inList = false;
  let inCapa = false;
  let listItems = [];

  function flushList() {
    if (listItems.length > 0) {
      if (inCapa) {
        html += listItems.join('');
      } else {
        html += '<div class="investigation-category"><ul>' + 
          listItems.map(li => '<li>' + li + '</li>').join('') + 
          '</ul></div>';
      }
      listItems = [];
    }
  }

  for (let i = 0; i < lines.length; i++) {
    const line = lines[i].trim();
    
    // Skip empty lines
    if (!line) {
      flushList();
      inList = false;
      continue;
    }

    // Section headers (### 1. DEVIATION SUMMARY)
    const sectionMatch = line.match(/^###?\s*(\d+)\.\s*(.+)/);
    if (sectionMatch) {
      flushList();
      sectionNum = parseInt(sectionMatch[1]);
      const title = sectionMatch[2].trim();
      html += '<div class="report-section"><h3><span class="section-num">' + 
        sectionNum + '</span> ' + title + '</h3>';
      inCapa = title.includes('CAPA');
      continue;
    }

    // Sub-headings (**Product Quality:** or **Corrective Actions**)
    const subMatch = line.match(/^\*\*(.+?)\*\*\s*$/);
    if (subMatch) {
      flushList();
      html += '<div class="sub-heading">' + subMatch[1].replace(/:$/, '') + '</div>';
      continue;
    }

    // Severity badge
    const sevMatch = line.match(/^\*\*Classification:\s*(Critical|Major|Minor)\*\*/i);
    if (sevMatch) {
      const sev = sevMatch[1].toLowerCase();
      html += '<div class="severity-badge ' + sev + '">' + sevMatch[1] + '</div>';
      continue;
    }

    // Human review warning
    if (line.includes('HUMAN REVIEW REQUIRED')) {
      const text = line.replace(/^⚠\s*/, '').replace(/^\*\*HUMAN REVIEW REQUIRED:?\*\*:?\s*/, '');
      html += '<div class="human-review"><strong>⚠ HUMAN REVIEW REQUIRED:</strong> ' + text + '</div>';
      continue;
    }

    // Information needed
    if (line.includes('INFORMATION NEEDED')) {
      const text = line.replace(/^\*\*INFORMATION NEEDED:?\*\*:?\s*/, '');
      html += '<div class="info-needed"><strong>INFORMATION NEEDED:</strong> ' + text + '</div>';
      continue;
    }

    // Investigation category headers (e.g., **Personnel:**)
    const catMatch = line.match(/^\*\*(.+?):\*\*\s*(.*)/);
    if (catMatch && !line.includes('HUMAN REVIEW') && !line.includes('INFORMATION NEEDED')) {
      flushList();
      const catName = catMatch[1];
      const remainder = catMatch[2];
      
      if (remainder && remainder.startsWith('N/A')) {
        html += '<div class="investigation-category"><h4><span class="cat-icon">●</span> ' + 
          catName + '</h4><p class="na">' + remainder + '</p></div>';
      } else {
        html += '<div class="investigation-category"><h4><span class="cat-icon">●</span> ' + 
          catName + '</h4>';
        if (remainder) {
          html += '<p>' + formatInline(remainder) + '</p>';
        }
        inList = true;
        html += '<ul>';
      }
      continue;
    }

    // List items
    const listMatch = line.match(/^[-•›*]\s+(.+)/);
    const numListMatch = line.match(/^\d+\.\s+(.+)/);
    if (listMatch) {
      if (inList) {
        html += '<li>' + formatInline(listMatch[1]) + '</li>';
      } else {
        listItems.push(formatInline(listMatch[1]));
      }
      continue;
    }
    if (numListMatch) {
      const content = formatInline(numListMatch[1]);
      if (inCapa) {
        html += '<div class="capa-item">' + content + '</div>';
      } else {
        html += '<p>' + content + '</p>';
      }
      continue;
    }

    // Close open list
    if (inList && !listMatch) {
      html += '</ul></div>';
      inList = false;
    }

    // Regular paragraph
    html += '<p>' + formatInline(line) + '</p>';
  }

  flushList();
  if (inList) html += '</ul></div>';
  
  // Close last section
  html += '</div>';
  
  return html;
}

function formatInline(text) {
  // Bold
  text = text.replace(/\*\*(.+?)\*\*/g, '<strong>$1</strong>');
  // Italic owner references
  text = text.replace(/\(Owner:([^)]+)\)/g, '<span class="capa-owner">(Owner:$1)</span>');
  text = text.replace(/\(([^)]*requires change control[^)]*)\)/gi, '<span class="capa-owner">($1)</span>');
  return text;
}

const html = mdToHtml(raw);

return [{
  json: { html }
}];
```

---

## Node 5: Respond to Webhook

- **Type:** Respond to Webhook
- **Response Body:** JSON
- **Response Data → Add Field:**
  - **Name:** `html`
  - **Value:** (Expression mode) `{{ $json.html }}`

### Response Headers (Add Option → Headers)

Add these headers to prevent CORS issues:

| Name | Value |
|------|-------|
| `Access-Control-Allow-Origin` | `*` |
| `Content-Type` | `application/json` |

---

## Testing

### 1. Activate the workflow

Click the toggle in the top-right of the n8n editor to switch from "Inactive" to "Active". The Production webhook URL only works when the workflow is active.

### 2. Update index.html

Replace the placeholder URL:

```javascript
const WEBHOOK_URL = 'https://your-n8n-instance.app.n8n.cloud/webhook/deviation-analysis';
```

### 3. Test with the form

Open your page, type a simple deviation in the form (e.g., "During batch review, tablet weight was found to be 105mg, exceeding the limit of 100mg ± 3%."), and hit Generate Analysis.

### 4. If you get CORS errors

If the browser console shows CORS errors, make sure:
- The Webhook node has `Allowed Origins` set to `*`
- The Respond to Webhook node has the `Access-Control-Allow-Origin: *` header
- The workflow is **Active** (not just saved)

### 5. If the response takes too long

OpenAI can take 20-40 seconds for a full report with GPT-4 class models. The frontend already shows "This may take 15 to 30 seconds..." so this is expected. If it consistently times out, check your n8n instance's timeout settings.

---

## Workflow Summary

```
[Webhook]  POST /deviation-analysis
     ↓     receives: { event_description, discovery_date, product_batch, 
           process_step, expected_parameter, observed_value, immediate_actions }
     
[Code]     Formats the 7 fields into a structured markdown user message
     ↓     
[OpenAI]   System prompt (full system-prompt.md) + user message
     ↓     Returns: markdown analysis
     
[Code]     Converts markdown → styled HTML matching the page CSS classes
     ↓
[Respond]  Returns: { html: "<div class='report-section'>..." }
     ↓     to the browser, which inserts it into the page
```
