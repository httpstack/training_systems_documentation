# PROCESS DOCUMENTATION
**Process Name:** Asset Ingestion & Tagging
**Trigger:** Physical receipt of item OR Invoice Payment > $5,000

================================
**INPUTS**
- [cite_start]Purchase Order (PO) Number [cite: 1044]
- Physical Asset (for tagging)
- [cite_start]Funding Source Info (State vs. RF vs. Sponsor) [cite: 1285]

--------------------------------
**PROCESS STEPS (The State Machine)**
1. **Validation:** Check Condition & PO Match.
2. **Classification:** Determine Ownership (RF, State, Sponsor).
   - *Logic:* If Funds = State -> State Tag. [cite_start]If Funds = Federal -> RF Tag + US Gov Tag[cite: 952].
3. **Tagging:** Affix physical decal.
   - [cite_start]*Constraint:* If item is too small/delicate, decal goes in "Secure Log" instead[cite: 986].
4. **Data Entry:** Enter into RAMI (Legacy DB).
   - Critical Fields: Description, Location, Cost, Share % (if split funded).
5. [cite_start]**Reconciliation:** (Async) Finance checks AP vs RAMI cost within 90 days[cite: 1017].

--------------------------------
**OUTPUTS**
- New Database Record (Asset ID)
- Physical Asset with Barcode
- [cite_start]Start of Depreciation Timer (Straight Line) [cite: 1087]

--------------------------------
**EXCEPTIONS / VARIATIONS**
- [cite_start]**Donations:** If donated, need Fair Market Value appraisal[cite: 904].
- [cite_start]**Fabrication:** If building a machine from parts, use "Equipment in Progress" (Class 980200) until finished[cite: 917].
