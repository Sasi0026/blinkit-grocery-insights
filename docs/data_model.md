# Data Model Documentation
## Project: Blinkit Grocery Sales Analysis
## Tool: Power BI Desktop
## Schema Type: Star Schema

---

## Model Overview
The flat dataset (8,523 rows × 12 columns) was 
restructured into a star schema consisting of one fact 
table and two dimension tables using Python (pandas).

This design improves performance, simplifies relationships, 
and enables accurate filtering across visuals in Power BI.

![Data Model](data_model_screenshot.png)

---

## Tables

### dim_item (Dimension)
| Column           | Type    | Description                    |
|------------------|---------|--------------------------------|
| item_identifier  | Text    | Primary Key — unique item code |
| item_type        | Text    | Product category               |
| item_fat_content | Text    | Low Fat or Regular             |
| item_weight      | Decimal | Item weight in kg              |
| item_visibility  | Decimal | Display area percentage        |

### dim_outlet (Dimension)
| Column                    | Type    | Description                      |
|---------------------------|---------|----------------------------------|
| outlet_identifier         | Text    | Primary Key — unique store code  |
| outlet_type               | Text    | Store format                     |
| outlet_size               | Text    | Small / Medium / High            |
| outlet_location_type      | Text    | Tier 1 / Tier 2 / Tier 3         |
| outlet_establishment_year | Integer | Year outlet was established      |
| outlet_age                | Integer | Derived: 2024 − establishment yr |

### fact_sales (Fact)
| Column            | Type    | Description                        |
|-------------------|---------|------------------------------------|
| item_identifier   | Text    | Foreign Key → dim_item             |
| outlet_identifier | Text    | Foreign Key → dim_outlet           |
| sales             | Decimal | Total sales value                  |
| rating            | Decimal | Customer rating 1–5                |

---

## Relationships
| From Table  | Column            | To Table   | Column            | Cardinality | Direction |
|-------------|-------------------|------------|-------------------|-------------|-----------|
| fact_sales  | item_identifier   | dim_item   | item_identifier   | Many to one | Single    |
| fact_sales  | outlet_identifier | dim_outlet | outlet_identifier | Many to one | Single    |

---

## Design Decisions
- Star schema used instead of a flat table to improve performance, 
  simplify relationships, and ensure accurate filtering
- `outlet_age` engineered in Python as a derived feature for 
  improved interpretability of outlet maturity
- Data cleaning and modeling performed in Python prior to Power BI 
  to ensure reproducibility and version control