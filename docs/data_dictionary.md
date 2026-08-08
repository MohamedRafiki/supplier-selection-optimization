# Data Dictionary

## 1. Suppliers

This table contains the master data related to suppliers.

| Variable | Data Type | Description | Example | Business Rule |
|---|---|---|---|---|
| supplier_id | String | Unique identifier of the supplier | SUP001 | Must be unique |
| supplier_name | String | Name assigned to the supplier | Supplier A | Must not be empty |
| country | String | Supplier's country | Morocco | Must be a valid country |
| supplier_type | String | Type of supplier | OEM | Must belong to a predefined category |
| payment_terms | Integer | Agreed payment period in days | 60 | Must be >= 0 |
| active_status | Boolean | Indicates whether the supplier is currently active | True | True or False |

---

## 2. Spare Parts

This table contains the master data related to spare parts used for production equipment.

| Variable | Data Type | Description | Example | Business Rule |
|---|---|---|---|---|
| part_id | String | Unique identifier of the spare part | PART001 | Must be unique |
| part_name | String | Name of the spare part | Bearing | Must not be empty |
| category | String | Spare part category | Mechanical | Must belong to a predefined category |
| criticality | String | Criticality level of the spare part | High | Low, Medium, High, Critical |
| machine_type | String | Type of machine using the spare part | Injection Molding Machine | Must not be empty |
| annual_demand | Integer | Estimated annual demand | 120 | Must be > 0 |
| target_stock | Integer | Target inventory level | 20 | Must be >= 0 |
