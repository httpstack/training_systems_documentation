# DECISION RECORD & BUSINESS RULES
*Master log of all logic gates and business constraints.*

# DECISION RECORD
**Date:** 1-21-26
**Decision:** Capitalization Threshold Logic

================================
**CONTEXT**
We don't put everything in the database. We need a filter.

--------------------------------
**LOGIC / ALGORITHM**
IF (Cost >= $5,000) AND (Useful Life > 1 Year):
    [cite_start]THEN -> Capitalize (Track in RAMI) [cite: 771]
ELSE IF (Sponsor Requirement exists):
    [cite_start]THEN -> Capitalize regardless of cost [cite: 789]
ELSE:
    THEN -> Expense as "Supplies" (Don't track)

--------------------------------
**RISKS / EDGE CASES**
- "Walkables" (Laptops/Tablets under $5k):
    - *Observation:* We currently track these manually in a spreadsheet because they are high theft risk, even if not "Capitalized".
    - *Future Feature:* Create "Low Value Asset" tracking in new app.
---
## [ID-002] Handling Broken Assets (Disposal)
**Date:** 2026-01-20 | [cite_start]**Source:** Property Handbook p.22 [cite: 1125]
* **Trigger:** Asset is lost, stolen, or damaged.
* **Logic:**
    * [cite_start]IF lost/stolen -> Must file report with Security Office[cite: 1129].
    * [cite_start]IF sponsor owned -> Must notify sponsor within 30 days[cite: 1133].
    * [cite_start]IF tax credit involved (Form 8283) -> Must track for 3 years before disposal[cite: 1195].

---
## [ID-001] Capitalization Threshold
**Date:** 2026-01-19 | [cite_start]**Source:** Property Handbook p.3 [cite: 771]
* **Rule:** Capitalize ONLY if Cost >= $5,000 AND Useful Life > 1 Year.
* [cite_start]**Exception:** If Sponsor requires lower threshold, use that[cite: 789].
