# Example Output — Major Deviation (Temperature Excursion)

---

## 1. DEVIATION SUMMARY

On 2026-04-28, a temperature excursion was detected in Cold Storage Room CS-02, where the recorded temperature reached 9.2°C, exceeding the validated storage range of 2–8°C by 1.2°C. Continuous monitoring data indicates the excursion began at approximately 02:30 with the alarm triggering at 03:17, and the temperature returned to within specification at 06:02, resulting in an excursion duration of approximately 2 hours and 45 minutes. CS-02 contained API intermediates for Batches LU-2026-0087, LU-2026-0088, and LU-2026-0091, as well as 12 reference standards used in QC testing. Preliminary inspection identified a stopped condenser fan as the likely cause.

---

## 2. SEVERITY CLASSIFICATION

**Classification: Major**

This deviation represents a significant departure from validated storage conditions for API intermediates and reference standards. The excursion magnitude (1.2°C above the upper limit) and duration (2 hours 45 minutes) are sufficient to warrant investigation into potential impact on material quality, particularly for temperature-sensitive intermediates and reference standards. While the excursion was not extreme, the number of materials affected (three batches of API intermediates plus 12 reference standards) increases the potential scope of impact. The deviation does not meet the threshold for Critical classification at this stage because the excursion was relatively modest and no direct patient safety impact has been confirmed, but escalation to Critical should be considered if stability data indicates material degradation.

⚠ **HUMAN REVIEW REQUIRED:** Severity classification must be reviewed and confirmed by the QA reviewer. If stability data for the affected materials indicates sensitivity to the excursion conditions (9.2°C for ~3 hours), escalation to Critical may be warranted.

---

## 3. IMPACT ASSESSMENT

**Product Quality:** The primary concern is whether the temperature excursion affected the chemical stability, physical properties, or potency of the stored API intermediates. The impact depends on the specific stability profiles of each material at the excursion temperature. Reference standard integrity must also be assessed — compromised reference standards would affect the validity of all QC test results generated using them.

**Patient Safety:** Indirect risk. If the API intermediates were degraded by the excursion and this went undetected, it could result in subpotent or impure finished product. If reference standards were compromised and continued to be used, QC test results would be unreliable. Both scenarios present potential patient safety risk if not properly investigated.

**Batch Disposition:** Three batches of API intermediates (LU-2026-0087, LU-2026-0088, LU-2026-0091) should remain quarantined until the impact assessment is complete. Finished products already manufactured from earlier batches stored in CS-02 are not affected (the excursion affects only materials currently in storage). Twelve reference standards must be assessed for continued suitability.

**Scope:** 
- Assess whether CS-02 has had previous temperature excursions (trend analysis of monitoring data).
- Determine whether other cold storage rooms share the same cooling system or maintenance schedule.
- Evaluate whether the condenser fan failure indicates a broader equipment maintenance gap.

⚠ **HUMAN REVIEW REQUIRED:** Impact assessment requires review by qualified personnel with knowledge of the specific stability profiles of the affected materials. Batch disposition decisions must be made by authorized QA personnel. QC must assess reference standard integrity before they are used in further testing.

---

## 4. ROOT CAUSE INVESTIGATION PLAN

**Personnel:**
- Who was responsible for monitoring overnight alarms? Was there a delay in responding to the alarm at 03:17?
- What is the escalation procedure for after-hours environmental alarms, and was it followed?
- Was the morning shift operator who discovered the deviation at 06:00 the first person to check, or was the alarm acknowledged earlier without action?

**Process/Method:**
- What is the alarm response SOP for environmental excursions? Does it define maximum response time?
- Is there an automated escalation process (e.g., SMS/call to on-call personnel) for critical alarms, or does it rely on manual monitoring?
- When was the last preventive maintenance performed on the CS-02 cooling system? Is the PM schedule adequate?

**Equipment/Machine:**
- What caused the condenser fan to stop? Electrical failure, mechanical wear, control system issue?
- When was the condenser fan last inspected, serviced, or replaced?
- Is there redundancy in the cooling system for CS-02 (backup unit, dual compressors)? If so, why did the backup not activate automatically?
- Was the cooling unit operating within its rated capacity, or was CS-02 overloaded?
- Review calibration records for the temperature monitoring sensors in CS-02.

**Material:**
- What are the validated storage conditions and stability data for each of the three affected API intermediates at temperatures above 8°C?
- Do the material specifications or stability studies include data for short-term excursions at 9–10°C?
- What is the remaining shelf life of each reference standard? Are any near expiry and therefore more susceptible to degradation?

**Measurement:**
- Confirm accuracy of the temperature monitoring system. Cross-reference the 9.2°C reading with an independent calibrated probe if available.
- Review the continuous monitoring data for the period leading up to the excursion — was there a gradual warming trend, or was the excursion sudden?

**Environment:**
- Was there any external factor affecting CS-02 temperature (e.g., adjacent equipment generating heat, facility HVAC issues, door left open)?
- Review door access logs for CS-02 during the period 02:00–06:00.
- Were there any facility-level power fluctuations or outages that could have affected the cooling unit?

⚠ **HUMAN REVIEW REQUIRED:** The investigator determines which investigation areas are relevant and conducts the actual investigation. Equipment root cause analysis should involve Facilities/Engineering.

---

## 5. DRAFT CAPA RECOMMENDATIONS

**Corrective Actions:**

1. **Complete equipment repair and verification.** Repair or replace the failed condenser fan in CS-02. Perform functional testing and confirm temperature recovery and sustained performance within 2–8°C before returning the room to routine use. *(Owner: Facilities/Engineering — may require requalification of CS-02)*
2. **Conduct stability impact assessment.** Review available stability data for each affected API intermediate to determine whether the excursion conditions (9.2°C for ~3 hours) fall within acceptable limits. If stability data does not cover this scenario, consider accelerated stability testing or retesting of affected materials. *(Owner: QC / Stability)*
3. **Assess reference standard integrity.** Retest or replace the 12 reference standards stored in CS-02 during the excursion. Do not use these reference standards for release testing until their suitability has been confirmed. *(Owner: QC)*
4. **Determine batch disposition.** Based on the stability impact assessment results, make batch disposition decisions for LU-2026-0087, LU-2026-0088, and LU-2026-0091. *(Owner: QA)*

**Preventive Actions:**

1. **Review and upgrade alarm escalation procedures.** Evaluate whether the current after-hours alarm response process is adequate. Consider implementing automated SMS/call escalation for critical environmental alarms with defined maximum response times. *(Owner: QA / Facilities — requires change control if SOP revision needed)*
2. **Review preventive maintenance schedule for cold storage cooling systems.** Assess whether the current PM frequency and scope are adequate to prevent condenser fan failures. Consider adding condenser fan inspection/replacement to the PM schedule at a more frequent interval. *(Owner: Facilities/Engineering — requires change control)*
3. **Evaluate cooling system redundancy.** Assess whether CS-02 (and other critical cold storage rooms) should have automatic backup cooling activation to prevent future excursions from single-point equipment failures. *(Owner: Facilities/Engineering — capital investment may be required)*
4. **Trend analysis of environmental excursions.** Review the last 12 months of temperature monitoring data across all cold storage rooms to identify any patterns or recurring issues. *(Owner: QA)*

⚠ **HUMAN REVIEW REQUIRED:** CAPA recommendations are suggestions only. Final CAPA plan must be developed by the investigation team with input from Facilities, QC, and QA. Equipment modifications and SOP revisions require formal change control.

---

## 6. REGULATORY CONSIDERATIONS

**Applicable Frameworks:**
- **ICH Q10, Section 3.2.1** — Deviation management within the Pharmaceutical Quality System. This deviation must be formally documented, investigated, and resolved.
- **ICH Q1A (Stability Testing)** — Stability data should be consulted to assess the impact of the temperature excursion on affected materials.
- **EU GMP Chapter 3 (Premises and Equipment)** — Storage areas must be designed and equipped to maintain required conditions. Environmental monitoring must demonstrate compliance.
- **EU GMP Annex 15 (Qualification and Validation)** — If CS-02 requires requalification after repair, this should follow the site's qualification protocol.
- **21 CFR 211.142** — Requires appropriate storage conditions for drug components, containers, and closures, with adequate temperature controls.

**Reporting Considerations:**
- Regulatory notification: Not typically required unless the impact assessment reveals that affected batches were released to market with compromised quality. If any finished product made from affected intermediates has already been distributed, a field alert assessment may be needed.
- Annual Product Review: Include in deviation trending and environmental monitoring sections.
- Inspection readiness: Temperature excursions in storage areas are frequently reviewed during regulatory inspections. Ensure thorough documentation of the investigation, impact assessment, and CAPA effectiveness.

⚠ **HUMAN REVIEW REQUIRED:** Regulatory reporting obligations must be assessed by Regulatory Affairs and QA leadership. Particular attention should be given to whether any product manufactured from materials stored in CS-02 has already been released to market.
