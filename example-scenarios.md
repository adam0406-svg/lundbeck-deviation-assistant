# Example Deviation Scenarios

Three scenarios at different severity levels. These are the structured inputs that will be pre-loaded on the showcase page. Each represents a realistic pharma quality deviation that any quality professional would recognize.

---

## Scenario 1 — Minor (Documentation Error)

**Event Description:** During routine batch record review, a second-person verification signature was found missing on the weighing step for excipient Lactose Monohydrate. The weighing was performed and recorded by the operator, but the verification line was left blank. The correct weight was confirmed by cross-referencing the dispensing log and scale printout.

**Discovery Date/Time:** 2026-04-28, 14:30

**Product/Batch:** Escipra Tablets 10 mg (fictional), Batch EX-2026-0412

**Process Step:** Raw material dispensing — excipient weighing and verification

**Expected Parameter:** All weighing steps require operator signature AND independent second-person verification signature per SOP-RM-003 Section 4.2

**Observed Value:** Operator signature present. Second-person verification signature missing on line 14 of the batch record.

**Immediate Actions Taken:** Batch record flagged and placed on QA hold. The original verifier (Operator B) confirmed verbally that the verification was performed at the time of weighing but the signature was inadvertently missed. No production impact — batch has not progressed beyond dispensing.

---

## Scenario 2 — Major (Temperature Excursion)

**Event Description:** The environmental monitoring system generated an alarm for Cold Storage Room CS-02, indicating that the temperature reached 9.2°C at 03:17. The validated storage range for the room is 2–8°C. The excursion lasted approximately 2 hours and 45 minutes before the temperature returned to within specification. CS-02 stores API intermediates and reference standards for multiple products currently in production.

**Discovery Date/Time:** 2026-04-28, 06:00 (discovered by morning shift operator reviewing overnight alarms)

**Product/Batch:** Multiple — CS-02 contains API intermediates for Batches LU-2026-0087, LU-2026-0088, and LU-2026-0091, as well as 12 reference standards used in QC testing.

**Process Step:** In-process storage of API intermediates between synthesis and formulation

**Expected Parameter:** Storage temperature 2–8°C continuously, per validated storage conditions and material specifications

**Observed Value:** Temperature reached 9.2°C (1.2°C above upper limit) for approximately 2 hours 45 minutes (03:17–06:02). Continuous monitoring data shows a gradual rise beginning at approximately 02:30.

**Immediate Actions Taken:** All materials in CS-02 quarantined. Facilities team dispatched to inspect the cooling unit. Preliminary inspection found the condenser fan had stopped — cause under investigation. Backup cooling unit activated. Temperature returned to 5.1°C by 06:45. QC notified regarding reference standard integrity.

---

## Scenario 3 — Critical (Cross-Contamination Risk)

**Event Description:** During cleaning verification following a product changeover from Product A (Nortriptyline HCl 25 mg tablets) to Product B (Citalopram 20 mg tablets) on Tablet Press TP-03, swab test results from the punch face surfaces returned a residue level of 8.4 µg/cm², exceeding the validated cleaning limit of 4.0 µg/cm². The cleaning had been performed per SOP-CL-011 and signed off as complete. Product B manufacturing had not yet commenced — the deviation was caught during pre-production verification.

**Discovery Date/Time:** 2026-04-28, 07:15

**Product/Batch:** Product B: Citalopram 20 mg tablets, Batch CT-2026-0203 (not yet started). Previous product on the line: Nortriptyline HCl 25 mg tablets, Batch NT-2026-0195 (completed, in quarantine pending release).

**Process Step:** Equipment cleaning verification — post-changeover, pre-production check on tablet press TP-03

**Expected Parameter:** Cleaning verification limit: ≤ 4.0 µg/cm² residue of previous product (Nortriptyline HCl) on product contact surfaces, per Cleaning Validation Protocol CVP-2024-018

**Observed Value:** Swab sample from punch face surfaces: 8.4 µg/cm² (210% of the acceptance limit). Swab samples from hopper and feed frame were within specification (1.2 µg/cm² and 0.8 µg/cm² respectively).

**Immediate Actions Taken:** Tablet press TP-03 placed on hold — not released for Product B manufacturing. Re-cleaning initiated per SOP-CL-011 with additional manual scrubbing of punch faces. QA hold placed on the previous batch (NT-2026-0195) pending investigation into whether cleaning procedure adequacy should trigger a retrospective review. Cleaning team lead notified. All other equipment that underwent changeover cleaning in the same period flagged for review.
