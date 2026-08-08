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

---

## 3. Supplier Part Prices

This table contains the commercial conditions offered by each supplier for each spare part.

| Variable | Data Type | Description | Example | Business Rule |
|---|---|---|---|---|
| supplier_id | String | Unique identifier of the supplier | SUP001 | Must exist in the suppliers table |
| part_id | String | Unique identifier of the spare part | PART001 | Must exist in the spare_parts table |
| unit_price | Decimal | Purchase price per unit | 125.50 | Must be > 0 |
| currency | String | Currency of the quoted price | EUR | Must be a valid currency |
| minimum_order_qty | Integer | Minimum quantity that can be ordered | 5 | Must be > 0 |
| lead_time_days | Integer | Standard supplier lead time in days | 14 | Must be >= 0 |
| valid_from | Date | Start date of the price validity period | 2026-01-01 | Must be a valid date |
| valid_to | Date | End date of the price validity period | 2026-12-31 | Must be after valid_from |

---

## 4. Purchase Orders

This table contains the purchase orders placed with suppliers for spare parts.

| Variable | Data Type | Description | Example | Business Rule |
|---|---|---|---|---|
| po_id | String | Unique identifier of the purchase order | PO0001 | Must be unique |
| supplier_id | String | Identifier of the selected supplier | SUP001 | Must exist in the suppliers table |
| part_id | String | Identifier of the ordered spare part | PART001 | Must exist in the spare_parts table |
| order_date | Date | Date when the purchase order was created | 2026-02-15 | Must be a valid date |
| ordered_quantity | Integer | Quantity ordered | 10 | Must be > 0 |
| unit_price | Decimal | Agreed purchase price per unit | 125.50 | Must be > 0 |
| promised_date | Date | Date promised by the supplier | 2026-03-01 | Must be after or equal to order_date |
| purchase_order_status | String | Current status of the purchase order | Completed | Must belong to a predefined category |
