# Problem Statement
## Project: Blinkit Grocery Sales & Outlet Performance Analysis

---

## 1. Business Context

Blinkit (formerly Grofers) is India's quick commerce platform
delivering groceries and household essentials within minutes.
The platform operates across multiple outlet formats (Supermarket
Type1, Type2, Type3 and Grocery Stores) in Tier 1, Tier 2, and
Tier 3 cities across India.

With 10 outlets selling 1,559 unique items across 16 product
categories, Blinkit needs to understand which outlet formats,
city tiers, and product categories are driving revenue —
and which are underperforming.

---

## 2. Problem Statement

The business currently cannot identify:
- Which outlet format and location tier combination
  generates the highest revenue efficiency
- Which product categories drive disproportionate
  sales contribution
- Whether item attributes (fat content, visibility, weight)
  influence customer purchasing behaviour
- How outlet maturity (age) relates to sales performance

Without these insights, inventory investment, outlet expansion,
and product placement decisions are made without data backing.

---

## 3. Analytical Questions

1. Which outlet type and location tier drives the
   highest total and average sales?

2. Which item categories contribute most to revenue
   across different outlet formats?

3. Does item fat content or item visibility influence
   sales performance?

4. Does outlet establishment year (outlet age) correlate
   with sales performance?

---

## 4. Success Criteria

A Power BI dashboard that:
- Allows filtering by outlet type, location tier,
  outlet size, and item type
- Answers all 4 analytical questions with specific numbers
- Identifies at least 5 actionable business insights
- Enables drill-down from overview to outlet to item level

---

## 5. Scope

**In scope:**
- Sales performance analysis across outlet dimensions
- Product category performance analysis
- Customer rating analysis
- Outlet establishment year trend analysis
- Fat content and item visibility impact analysis

**Out of scope:**
- Customer demographic analysis (data not available)
- Profit margin analysis (item price not available)
- Competitor benchmarking
- Geographic mapping analysis

---

## 6. KPI Definitions

| KPI | Business Definition | Formula |
|-----|--------------------|---------| 
| Total Sales | Sum of all sales transactions | SUM(fact_sales[sales]) |
| Avg Sales | Mean sales per item-outlet row | AVERAGE(fact_sales[sales]) |
| Avg Rating | Mean customer rating | AVERAGE(fact_sales[rating]) |
| Total Items | Distinct items in dataset | DISTINCTCOUNT(item_identifier) |
| Total Outlets | Distinct outlets in dataset | DISTINCTCOUNT(outlet_identifier) |
| Sales per Outlet | Revenue per outlet | Total Sales / Total Outlets |
| Sales % of Total | Current selection contribution | Current Sales / All Sales |

---

## 7. Dataset

**Source:** BlinkIT Grocery Data — Kaggle  
**Format:** Single flat Excel file (.xlsx)  
**Rows:** 8,523  
**Columns:** 12  
**Time period:** Outlets established 2010–2022  

---

## 8. Deliverables

| Deliverable | Description |
|-------------|-------------|
| EDA Notebook | Annotated exploratory analysis with findings |
| Cleaning Notebook | Data cleaning and star schema engineering |
| Power BI Dashboard | 3-page interactive dashboard |
| Final Report | Findings, recommendations, limitations |
| Documentation | Data dictionary, data model, DAX measures |