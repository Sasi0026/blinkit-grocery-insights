# Blinkit Grocery Sales — Final Analysis Report

**Author:** **Sasi Kiran** 
  
**Tools:** Python (Pandas, Matplotlib, Seaborn) · Power BI Desktop  
**Dataset:** BlinkIT Grocery Data (Kaggle) — 8,523 rows · 12 columns  
**GitHub:** [blinkit-grocery-insights](https://github.com/yourusername/blinkit-grocery-insights)

---

## 1. Executive Summary

Blinkit operates across **10 outlets** in **3 location tiers** (Tier 1, 2, 3)
selling **1,559 unique items** across 16 product categories.
The platform generated **₹1.20M in total sales** with an average sale
of **₹140.99 per transaction** and an average customer rating of **3.92 out of 5**.

This analysis investigates sales performance across outlet formats,
location tiers, product categories, and customer engagement metrics
to identify growth opportunities and operational inefficiencies.

**Sales per Outlet: ₹120,170** — a key normalised performance metric
used throughout this report to remove outlet count bias.

---

## 2. Business Questions Answered

1. Which outlet type and location tier drives the highest sales?
2. Which item categories contribute most to revenue?
3. Does fat content or item visibility influence sales performance?
4. How does outlet establishment year relate to sales performance?
5. Which outlet format delivers the best customer engagement?

---

## 3. Dashboard Overview

| Page | Title | Purpose |
|------|-------|---------|
| Page 1 | Sales Analysis Dashboard | Overall sales performance across all dimensions |
| Page 2 | Outlet Analysis Dashboard | Deep dive into outlet format and location performance |
| Page 3 | Item Analysis Dashboard | Product category performance and customer engagement |

---

## 4. Key Findings

### Finding 1 — Supermarket Type1 dominates revenue with 65.54% sales share

**Page:** Sales Analysis · Outlet Type Sales Distribution (Pie Chart)

Supermarket Type1 generates **₹787,550 (65.54%)** of total revenue —
more than the combined sales of all other outlet formats:
- Grocery Store: ₹151,940 (12.6%)
- Supermarket Type2: ₹131,480 (10.94%)
- Supermarket Type3: ₹130,710 (10.88%)

However the Outlet Performance Summary table (Page 2) reveals that
**average sales per transaction is virtually identical across all formats**
(~₹140–₹141), confirming that Type1's dominance is driven by
outlet count (6 outlets) — not genuine per-item efficiency.

**Implication:** Blinkit's revenue is volume-driven, not format-driven.
Expanding any outlet format proportionally will drive equivalent revenue growth.

---

### Finding 2 — Tier 2 is the most efficient location despite lower total sales

**Page:** Sales Analysis · Sales Performance Across Location Tiers

Total sales by tier:
- Tier 3: ~₹0.40M (highest — 4 outlets)
- Tier 2: ~₹0.35M
- Tier 1: ~₹0.30M (lowest — 3 outlets)

Tier 3 leads in total sales due to having **4 outlets vs 3** in Tier 1 and Tier 2.
However Tier 2 generates **₹393,150 with 3 outlets** vs Tier 1's **₹336,397
with the same 3 outlets** — making Tier 2 the most efficient location tier
on a per-outlet basis (~₹131,050 per outlet vs ~₹112,132 for Tier 1).

**Implication:** Tier 2 cities represent the highest return on new outlet investment.

---

### Finding 3 — Outlet establishment year shows a peak performance in 2018

**Page:** Outlet Analysis · Sales Trend by Outlet Establishment Year

Sales trend by establishment year:
- 2012: ₹78K (lowest — newest entrant)
- 2014–2016: ₹130K–₹132K (stable)
- 2018: **₹205K (peak)**
- 2020: ₹129K (sharp decline)
- 2022: ₹131K (recovery)

Outlets established in **2018 generate the highest sales (₹205K)**,
significantly outperforming all other establishment years.
Post-2018 outlets show lower performance, potentially reflecting
newer outlets still building customer base and brand loyalty.

**Implication:** Outlet maturity positively influences sales up to a point.
Newer outlets (post-2018) need targeted growth strategies to reach
the performance levels of established outlets.

---

### Finding 4 — Fruits & Vegetables and Snack Foods are revenue leaders

**Page:** Item Analysis · Top 5 Item Categories by Sales

Top 5 categories by total sales:
1. Fruits and Vegetables → **₹0.18M**
2. Snack Foods → **₹0.18M**
3. Household → **₹0.14M**
4. Frozen Foods → **₹0.12M**
5. Dairy → **₹0.10M**

Bottom performers:
- Seafood → lowest sales across all outlet types
- Breakfast → second lowest across all formats
- Starchy Foods → consistently low performance

**Item Performance Across Outlet Types matrix** confirms
Supermarket Type1 dominates in every single category —
with Fruits & Vegetables (₹117,431) and Snack Foods
leading within Type1 specifically.

**Implication:** Inventory investment should prioritise the top 3 categories
across all Supermarket Type1 outlets to maximise revenue per outlet.

---

### Finding 5 — Regular fat content drives 64.6% of total sales

**Page:** Item Analysis · Sales Contribution by Fat Content

- Regular fat items: **₹776,320 (64.6%)**
- Low Fat items: **₹425,360 (35.4%)**

The **Fat Content Preference by Outlet Location** chart (Page 3)
shows this pattern is consistent across all 3 tiers:
- Tier 3: Regular ₹0.31M vs Low Fat ₹0.17M
- Tier 2: Regular ₹0.25M vs Low Fat ₹0.14M
- Tier 1: Regular ₹0.22M vs Low Fat ₹0.12M

Regular fat items outsell Low Fat by approximately
**1.8× in every location tier without exception.**

**Implication:** Product mix should favour Regular fat items.
Low Fat items may benefit from targeted promotions to
improve their 35.4% contribution.

---

### Finding 6 — Customer engagement is consistent — ratings do not vary by category

**Page:** Item Analysis · Customer Engagement by Item Category

Average rating across all item categories ranges between
**3.83 and 3.98** — a variation of only 0.15 points.

Notable observations:
- Soft Drinks: highest transactions (with consistent rating ~3.95)
- Seafood: lowest transactions (0.2K) AND lowest rating (3.83)
- Fruits & Vegetables: highest transactions (1.2K) with rating 3.91

**Implication:** Customer satisfaction is uniformly consistent
across categories — Blinkit maintains quality perception
regardless of product type. Seafood's low rating combined
with low transactions suggests both a demand and quality issue.

---

### Finding 7 — Fat content sales split by outlet size reveals Small outlets lead

**Page:** Sales Analysis · Fat Content Sales by Outlet Size

- Small outlets: Total Sales ~₹0.6M (highest)
- Medium outlets: ~₹0.45M
- High outlets: ~₹0.25M (lowest)

Regular fat items dominate across all outlet sizes.
Small outlets generating highest total sales is consistent
with earlier finding — Small outlets have **6 locations**
same as Medium, but their item mix leans toward
higher-selling categories.

---

## 5. Recommendations

### Recommendation 1 — Prioritise Tier 2 expansion with Supermarket Type1 format
Tier 2 cities with Supermarket Type1 format represent
the single highest revenue opportunity. New outlet investment
should target this combination first — confirmed by both
total sales and per-outlet efficiency analysis.

### Recommendation 2 — Stock and promote top 3 categories aggressively
Fruits & Vegetables, Snack Foods, and Household items
drive disproportionate revenue across all outlet types.
Ensure full stock availability and prominent placement
in all Supermarket Type1 outlets — especially in Tier 2 locations.

### Recommendation 3 — Investigate and intervene on underperforming categories
Seafood shows both lowest sales AND lowest customer rating (3.83).
This dual underperformance warrants:
- Pricing review
- Quality assessment
- Potential catalogue reduction in low-traffic outlets

### Recommendation 4 — Review shelf space allocation strategy
Item visibility has near-zero correlation with sales performance
(confirmed in EDA scatter plot analysis). Current shelf space
allocation policy should be reviewed — display area investment
is not driving revenue and resources could be better deployed
on pricing and category placement decisions.

### Recommendation 5 — Develop outlet maturity growth programme
Post-2018 outlets underperform the 2018 peak (₹205K) significantly.
A structured onboarding and growth programme for newer outlets —
focusing on category mix optimisation and local marketing —
could accelerate their path to peak performance levels.

---

## 6. Methodology

### Data Source
BlinkIT Grocery Data — Kaggle  
Single flat table: 8,523 rows × 12 columns  
Accessed: May 2026

### Tools and Technologies
| Tool | Purpose |
|------|---------|
| Python (Pandas, NumPy) | Data cleaning and transformation |
| Matplotlib, Seaborn | Exploratory data analysis visualisation |
| Power BI Desktop | Data modelling, DAX measures, dashboard |
| GitHub | Version control and portfolio documentation |

### Data Cleaning Steps
1. Standardised column names to snake_case
2. Fixed Item Fat Content — 5 dirty values mapped to 2 clean categories
3. Imputed Item Weight nulls — median per Item Type (17% null rate)
4. Replaced Item Visibility zeros — mean per Item Type (data entry errors)
5. Verified Outlet Size — no nulls found in dataset
6. Engineered outlet_age — derived from outlet_establishment_year
7. Split flat table into star schema — dim_item, dim_outlet, fact_sales
8. Validated FK integrity using Python assert statements

### Data Model
Star schema with 3 tables:
- **dim_item** — 1,559 rows · 5 columns (Primary Key: item_identifier)
- **dim_outlet** — 10 rows · 6 columns (Primary Key: outlet_identifier)
- **fact_sales** — 8,523 rows · 4 columns (2 Foreign Keys + 2 measures)

### Analytical Approach
| Section | Method | Purpose |
|---------|--------|---------|
| Univariate | Histograms, value counts | Understand individual column distributions |
| Bivariate | Bar charts, scatter plots | Find relationships between Sales and dimensions |
| Multivariate | Heatmaps, clustered bars | Identify combined variable patterns |

### DAX Measures Used
Total Sales · Avg Sales · Avg Rating · Total Items · Total Outlets ·
Total Transactions · Sales % of Total · Low Fat Sales · Regular Fat Sales ·
Sales per Outlet · Sales per Outlet Age

---

## 7. Limitations

- **No item pricing data** — profit margin, revenue per unit,
  and price elasticity analysis not possible
- **No time series data** — seasonal trends and month-over-month
  growth cannot be analysed beyond establishment year proxy
- **Small outlet sample (10 outlets)** — findings are directional,
  not statistically conclusive at population level
- **No customer demographics** — cannot segment analysis by
  buyer age, gender, or income profile
- **Item visibility post-cleaning** — zero values imputed with mean;
  true visibility data may differ

---

## 8. Next Steps

1. Collect transaction-level data with timestamps for
   seasonality and time series analysis
2. Add item pricing data to enable margin and profitability analysis
3. Expand dataset to 50+ outlets for statistically significant findings
4. Build predictive model for sales forecasting by outlet and category
5. Integrate customer demographic data for buyer segmentation analysis

---

## 9. Dashboard Screenshots

### Page 1 — Sales Analysis Dashboard
![Sales Overview](screenshots/sales_overview.png)

### Page 2 — Outlet Analysis Dashboard
![Outlet Analysis](screenshots/outlet_analysis.png)

### Page 3 — Item Analysis Dashboard
![Item Analysis](screenshots/item_analysis.png)

---



