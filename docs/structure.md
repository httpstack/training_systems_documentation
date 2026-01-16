/office-automation-discovery
│
├── 00_inbox_dailies/          <-- TEMPORAL (New file every day)
│   ├── 2026-01-19_log.md
│   ├── 2026-01-20_log.md
│   └── ...
│
├── 01_processes/              <-- PERSISTENT (One file per distinct workflow)
│   ├── README.md              <-- Index of all processes
│   ├── proc_asset_acquisition.md
│   ├── proc_disposal_surplus.md
│   └── proc_inventory_audit.md
│
├── 02_data_schema/            <-- PERSISTENT (Defining the "Nouns")
│   ├── entity_asset.md        <-- Schema for "Equipment"
│   ├── entity_lease.md        <-- Schema for "Leases"
│   └── entity_vendor.md
│
├── 03_business_logic/         <-- PERSISTENT (Rules & Decisions)
│   ├── decision_log.md        <-- The "Changelog" of business rules
│   └── validation_rules.md    <-- Specific logic (e.g., Capitalization thresholds)
│
└── 04_reference/              <-- STATIC (Source materials)
    ├── glossary_of_terms.md   <-- Your "Enum" file
    ├── Property_Mgmt_Handbook.pdf
    └── RICS_Statement.pdf