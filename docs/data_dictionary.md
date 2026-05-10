# Data Dictionary
## Project: Blinkit Grocery Sales & Outlet Performance Analysis

---

## Source Dataset

| Property | Value |
|----------|-------|
| File name | BlinkIT Grocery Data.xlsx |
| Source | Kaggle |
| Date accessed | May 2026 |
| Total rows | 8,523 |
| Total columns | 12 |
| Location | data/raw/ |

---

## Raw Column Definitions

| Column | Type | Description | Example | Known Issues |
|--------|------|-------------|---------|--------------|
| Item Fat Content | Text | Fat content label of the item | Low Fat, Regular | Dirty values: LF, low fat, reg — standardised in cleaning |
| Item Identifier | Text | Unique item code | FDX32, NCB42 | None — used as Primary Key in dim_item |
| Item Type | Text | Product category of the item | Frozen Foods, Dairy | None — 16 unique categories |
| Outlet Establishment Year | Integer | Year the outlet was established | 2012, 2018 | None — used to derive outlet_age |
| Outlet Identifier | Text | Unique store code | OUT049, OUT018 | None — used as Primary Key in dim_outlet |
| Outlet Location Type | Text | City tier classification | Tier 1, Tier 2, Tier 3 | None — 3 unique values |
| Outlet Size | Text | Physical size of the outlet | Small, Medium, High | No nulls found in this dataset |
| Outlet Type | Text | Store format classification | Supermarket Type1, Grocery Store | None — 4 unique values |
| Item Visibility | Decimal | Percentage of total display area allocated to item in store | 0.1000, 0.0259 | Zero values present — data entry errors, imputed with mean per Item Type |
| Item Weight | Decimal | Weight of item in kilograms | 15.1, 11.8 | 17% null values — imputed with median per Item Type |
| Sales | Decimal | Total sales value of item at this outlet | 145.48, 113.35 | None — primary measure |
| Rating | Decimal | Customer rating out of 5 | 3.9, 5.0 | None — secondary measure |

---

## Data Quality Issues Found in EDA

| Column | Issue | % Affected | Fix Applied |
|--------|-------|------------|-------------|
| Item Fat Content | 5 dirty values (LF, low fat, reg, Regular, Low Fat) | 100% of column | Mapped to 2 clean values: Low Fat / Regular |
| Item Weight | Null values | ~17% | Median imputation grouped by Item Type |
| Item Visibility | Zero values (physically impossible) | ~5% | Mean imputation grouped by Item Type |
| Outlet Size | Checked for nulls | 0% | No action needed — clean |

---

## Derived Columns (Engineered in Cleaning Notebook)

| Column | Table | Formula | Description |
|--------|-------|---------|-------------|
| outlet_age | dim_outlet | 2024 − outlet_establishment_year | Measures outlet maturity in years |

---

## Processed Tables (Star Schema)

### dim_item
**Location:** data/processed/dim_item.csv  
**Rows:** 1,559 (one row per unique item)  
**Primary Key:** item_identifier

| Column | Type | Description |
|--------|------|-------------|
| item_identifier | Text | Primary Key — unique item code |
| item_type | Text | Product category |
| item_fat_content | Text | Clean values: Low Fat or Regular |
| item_weight | Decimal | Item weight in kg — nulls imputed |
| item_visibility | Decimal | Display area % — zeros imputed |

---

### dim_outlet
**Location:** data/processed/dim_outlet.csv  
**Rows:** 10 (one row per unique outlet)  
**Primary Key:** outlet_identifier

| Column | Type | Description |
|--------|------|-------------|
| outlet_identifier | Text | Primary Key — unique store code |
| outlet_type | Text | Store format: Supermarket Type1/2/3 or Grocery Store |
| outlet_size | Text | Physical size: Small / Medium / High |
| outlet_location_type | Text | City tier: Tier 1 / Tier 2 / Tier 3 |
| outlet_establishment_year | Integer | Year outlet was established |
| outlet_age | Integer | Derived: 2024 − establishment year |

---

### fact_sales
**Location:** data/processed/fact_sales.csv  
**Rows:** 8,523 (one row per item-outlet transaction)  
**Foreign Keys:** item_identifier → dim_item, outlet_identifier → dim_outlet

| Column | Type | Description |
|--------|------|-------------|
| item_identifier | Text | Foreign Key → dim_item |
| outlet_identifier | Text | Foreign Key → dim_outlet |
| sales | Decimal | Total sales value for this item at this outlet |
| rating | Decimal | Customer rating 1–5 for this item |

---

## Key Statistics

| Metric | Value |
|--------|-------|
| Total Sales | ₹1,201,681.49 |
| Avg Sales per row | ₹140.99 |
| Avg Rating | 3.92 |
| Unique Items | 1,559 |
| Unique Outlets | 10 |
| Outlet Types | 4 |
| Location Tiers | 3 |
| Item Categories | 16 |
| Sales range | ~₹20 — ~₹270 |
| Rating range | 1.0 — 5.0 |