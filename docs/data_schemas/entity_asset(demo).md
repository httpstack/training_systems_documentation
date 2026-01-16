# ENTITY: Asset (Equipment)

## Attributes (Columns)
| Field Name | Type | Required | Notes |
| :--- | :--- | :--- | :--- |
| `asset_id` | String | Yes | Barcode (10 digits). [cite_start]9th digit = 'R' for RF owned[cite: 969]. |
| `description` | String | Yes | Details features. [cite_start]Note if untaggable[cite: 989]. |
| `ownership_code` | Enum | Yes | [cite_start]See Appendix C. 'R'=RF, 'S'=State, 'T'=Transferred[cite: 1284]. |
| `useful_life` | Int | Yes | Years. [cite_start]Based on Appendix D (e.g., Lab Equip = 13 yrs)[cite: 1339]. |

## Relationships
- **Belongs To:** `Award` (Project)
- **Located At:** `Building/Room`
- **Managed By:** `Principal Investigator`
