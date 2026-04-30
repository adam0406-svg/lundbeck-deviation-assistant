# Example Output — Critical Deviation (Cleaning Verification Failure)

---

## 1. DEVIATION SUMMARY

On 2026-04-28 at 07:15, cleaning verification following a product changeover on Tablet Press TP-03 revealed that swab test results from punch face surfaces returned a residue level of 8.4 µg/cm² for the previous product (Nortriptyline HCl 25 mg), exceeding the validated cleaning limit of 4.0 µg/cm² by 110%. The changeover was from Nortriptyline HCl 25 mg tablets (Batch NT-2026-0195) to Citalopram 20 mg tablets (Batch CT-2026-0203). Cleaning was performed per SOP-CL-011 and signed off as complete. The deviation was caught during pre-production verification — Product B manufacturing had not commenced. Swab samples from the hopper (1.2 µg/cm²) and feed frame (0.8 µg/cm²) were within specification.

---

## 2. SEVERITY CLASSIFICATION

**Classification: Critical**

This deviation involves a cleaning verification failure for a product changeover between two different active pharmaceutical ingredients (Nortriptyline HCl and Citalopram). Residual Nortriptyline on product contact surfaces at 210% of the validated limit represents a confirmed cross-contamination risk. Although the deviation was detected before Product B manufacturing commenced (preventing actual cross-contamination in this instance), the fact that the cleaning was performed, signed off as complete, and yet failed verification indicates a breakdown in the cleaning process that could have resulted in cross-contamination if the pre-production verification step had been missed or not performed. Additionally, the previous batch (NT-2026-0195) warrants retrospective review to determine whether cleaning adequacy on prior changeovers involving this product should be re-evaluated.

⚠ **HUMAN REVIEW REQUIRED:** Severity classification must be reviewed and confirmed by the QA reviewer. The Critical classification is recommended due to the cross-contamination risk between two active pharmaceutical ingredients, even though actual contamination of Product B was prevented.

---

## 3. IMPACT ASSESSMENT

**Product Quality:**
- **Product B (Citalopram — Batch CT-2026-0203):** Not affected. Manufacturing had not commenced. No product quality impact on this batch, provided re-cleaning is verified as effective before production starts.
- **Product A (Nortriptyline — Batch NT-2026-0195):** The batch itself is not directly affected by this cleaning failure. However, the failure raises a question about whether previous changeovers from other products TO Nortriptyline were adequately cleaned. Retrospective review may be warranted.
- **Cleaning process integrity:** The primary quality concern is that the cleaning process (SOP-CL-011) produced a result that was signed off as complete but failed verification. This indicates the cleaning procedure, execution, or verification process has a gap.

**Patient Safety:** The cross-contamination risk between Nortriptyline (a tricyclic antidepressant) and Citalopram (an SSRI) is clinically significant. Co-exposure to both compounds could cause serious adverse effects including serotonin syndrome. This underscores the importance of the cleaning limit and the severity of exceeding it. In this case, patient safety was protected by the pre-production verification step.

**Batch Disposition:**
- Batch CT-2026-0203 (Citalopram): Not yet manufactured. Hold production until TP-03 passes re-cleaning verification.
- Batch NT-2026-0195 (Nortriptyline): Currently in quarantine. The cleaning failure does not directly affect this batch's quality, but QA should confirm that no retrospective concerns arise from the investigation before proceeding with release.

**Scope:**
- Was this changeover an isolated failure, or could similar failures have occurred on previous changeovers on TP-03 or other tablet presses?
- Review cleaning verification results for the last 12 months of changeovers on TP-03, particularly those involving Nortriptyline HCl.
- Assess whether other equipment cleaned using SOP-CL-011 during the same period should be reviewed.
- Determine whether other operators who performed changeover cleaning recently should be assessed.

⚠ **HUMAN REVIEW REQUIRED:** Impact assessment requires review by qualified personnel with knowledge of the specific products, cleaning validation protocols, and toxicological limits. Batch disposition decisions must be made by authorized QA personnel. The clinical significance of the cross-contamination risk should be confirmed by the site toxicologist or pharmacovigilance team.

---

## 4. ROOT CAUSE INVESTIGATION PLAN

**Personnel:**
- Who performed the cleaning on TP-03? Review their training records for SOP-CL-011 and cleaning verification procedures.
- Has this operator performed changeover cleaning before? What were the results?
- Was the cleaning performed during a shift change, under time pressure, or with any interruptions?
- Who signed off the cleaning as complete? Was this sign-off based on visual inspection only, or did it include a procedural verification?

**Process/Method:**
- Review SOP-CL-011 in detail. Does it include specific instructions for punch face cleaning (disassembly, manual scrubbing, soaking, rinse)?
- Is the current cleaning procedure validated specifically for Nortriptyline HCl residue removal? When was the cleaning validation performed?
- Were any steps in SOP-CL-011 recently changed? If so, was the change validated?
- Is there a difference in cleaning difficulty between punch face surfaces and other components (hopper, feed frame passed while punch faces failed)?
- Does the procedure require disassembly of punches for cleaning, or are they cleaned in place?
- Review the cleaning agent concentration, contact time, and water quality used during this cleaning.

**Equipment/Machine:**
- What is the condition of the punch face surfaces? Are there scratches, pitting, or wear that could trap residue?
- When were the punches on TP-03 last replaced or refurbished?
- Are the punch faces more difficult to clean than other product contact surfaces due to their geometry (engravings, embossing, break lines)?
- Was any cleaning equipment (brushes, spray nozzles, CIP components) worn or malfunctioning?

**Material:**
- Is Nortriptyline HCl known to be difficult to remove from stainless steel surfaces (adhesion, solubility characteristics)?
- Is the cleaning agent used in SOP-CL-011 effective for Nortriptyline HCl removal? Is there solubility data available?
- Were there any changes to the Nortriptyline formulation or excipients in the most recent batch that could affect cleaning difficulty?

**Measurement:**
- Review the swab sampling technique. Was the swab sampling location on the punch faces representative?
- Confirm the analytical method used for residue quantification is validated for Nortriptyline HCl at the relevant concentration range.
- Were the swab recovery factors accounted for in the 8.4 µg/cm² result?
- Cross-check with rinse water results if available.

**Environment:**
- Were there any environmental conditions (temperature of cleaning water, humidity, drying time) that may have affected cleaning effectiveness?
- Was the cleaning performed in the designated wash area, or was it done on the production floor?

⚠ **HUMAN REVIEW REQUIRED:** The investigator determines which investigation areas are relevant and conducts the actual investigation. The root cause may involve a combination of factors (e.g., punch surface condition + inadequate procedure for punch face cleaning). Engineering and cleaning validation specialists should be involved.

---

## 5. DRAFT CAPA RECOMMENDATIONS

**Corrective Actions:**

1. **Complete re-cleaning and verification of TP-03.** Re-clean all product contact surfaces on TP-03 with additional manual scrubbing of punch faces as already initiated. Do not release TP-03 for Product B production until swab results confirm residue levels are within the validated limit (≤ 4.0 µg/cm²). *(Owner: Production / QA)*
2. **Retrospective review of recent changeovers on TP-03.** Review cleaning verification results for all product changeovers on TP-03 in the last 6–12 months, with particular focus on changeovers involving Nortriptyline HCl as the preceding product. Identify any out-of-trend results. *(Owner: QA)*
3. **Assess other equipment cleaned in the same period.** Review whether other tablet presses or equipment that underwent changeover cleaning during the same timeframe (and by the same operator, if relevant) should be re-verified. *(Owner: QA / Production)*
4. **Hold decision on Batch NT-2026-0195.** Maintain QA hold on the Nortriptyline batch until the retrospective review confirms no concerns about prior cleaning adequacy that could have affected this batch. *(Owner: QA)*

**Preventive Actions:**

1. **Review and revise cleaning procedure for punch faces.** Evaluate whether SOP-CL-011 requires enhanced cleaning steps specifically for punch face surfaces — including disassembly, soaking, or additional scrubbing cycles. If changes are warranted, update the SOP and revalidate. *(Owner: Cleaning Validation / QA — requires change control and revalidation)*
2. **Evaluate punch surface condition program.** Implement or review a punch inspection and replacement program. Worn, scratched, or pitted punch faces may trap residue and require more aggressive cleaning or replacement. *(Owner: Engineering / Production — may require change control)*
3. **Assess cleaning agent effectiveness for Nortriptyline HCl.** If the current cleaning agent has limited effectiveness against Nortriptyline HCl residue, evaluate alternative cleaning agents or enhanced cleaning parameters (concentration, temperature, contact time). *(Owner: Cleaning Validation — requires change control and revalidation)*
4. **Reinforce cleaning verification as a critical quality step.** Ensure that all personnel involved in cleaning sign-off understand that their sign-off confirms procedural completion only, and that analytical verification (swab testing) is the definitive measure of cleaning adequacy. Consider adding a checklist or verification prompt to the sign-off step. *(Owner: QA / Training — requires change control if batch record or SOP is modified)*

⚠ **HUMAN REVIEW REQUIRED:** CAPA recommendations are suggestions only. Final CAPA plan must be developed by the investigation team with input from Cleaning Validation, Engineering, QC, and QA. SOP revisions and cleaning procedure changes require formal change control and may trigger cleaning revalidation.

---

## 6. REGULATORY CONSIDERATIONS

**Applicable Frameworks:**
- **ICH Q10, Section 3.2.1** — Deviation management. This deviation must be formally documented, investigated, and resolved within the Pharmaceutical Quality System.
- **ICH Q9 (Quality Risk Management)** — A risk assessment should be conducted to evaluate the probability and severity of cross-contamination had the deviation not been detected.
- **EU GMP Chapter 5, Section 5.19–5.20** — Requirements for prevention of cross-contamination during manufacturing. Cleaning validation must demonstrate that residues are reduced to acceptable levels.
- **EU GMP Annex 15, Section 10** — Cleaning validation requirements, including establishment of acceptance criteria and verification methods.
- **21 CFR 211.67** — Equipment cleaning and maintenance requirements. Equipment must be cleaned at appropriate intervals to prevent contamination.
- **EMA Guideline on Setting Health-Based Exposure Limits (2014)** — If the cleaning limit (4.0 µg/cm²) was established using a health-based approach (PDE/ADE), the exceedance should be assessed in the context of the toxicological threshold.

**Reporting Considerations:**
- Regulatory notification: Not required in this instance because cross-contamination was prevented (Product B was not manufactured). However, if the retrospective review reveals that similar cleaning failures may have occurred on previous changeovers where product was manufactured, a field alert assessment would be necessary.
- Annual Product Review: Include in deviation trending, cross-contamination risk assessment, and cleaning validation sections.
- Inspection readiness: Cross-contamination prevention is a high-priority area for regulatory inspectors. This deviation, its investigation, and CAPA effectiveness will likely be reviewed during inspections. Ensure the investigation is thorough and demonstrates that the cleaning process has been corrected and verified.

**INFORMATION NEEDED:** Confirm whether the cleaning limit of 4.0 µg/cm² was established using a health-based exposure limit (PDE/ADE) approach or a dose-based approach (1/1000th of the therapeutic dose). This affects the regulatory and toxicological interpretation of the exceedance.

⚠ **HUMAN REVIEW REQUIRED:** Regulatory reporting obligations must be assessed by Regulatory Affairs and QA leadership. The retrospective review outcome will determine whether any regulatory notification is required.
