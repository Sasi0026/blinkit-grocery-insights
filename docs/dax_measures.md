# DAX Measures Documentation
## Project: Blinkit Grocery Sales Analysis
## Last Updated: May 2026

---

## Base Measures

### Total Sales
**Business Definition:** Sum of all sales transactions
**Formula:**
```dax
Total Sales = SUM(fact_sales[sales])
```
**Format:** Currency, 2 decimal places
**Example:** $1,201,681.55

---

### Avg Sales
**Business Definition:** Average sales per item-outlet row
**Formula:**
```dax
Avg Sales = AVERAGE(fact_sales[sales])
```
**Format:** Currency, 2 decimal places
**Example:** $141.00

---

### Avg Rating
**Business Definition:** Mean customer rating across all items
**Formula:**
```dax
Avg Rating = AVERAGE(fact_sales[rating])
```
**Format:** Number, 1 decimal place
**Example:** 3.9

---

### Total Items
**Business Definition:** Count of distinct items in dataset
**Formula:**
```dax
Total Items = DISTINCTCOUNT(fact_sales[item_identifier])
```
**Format:** Whole number
**Example:** 1,559

---

### Total Outlets
**Business Definition:** Count of distinct outlets
**Formula:**
```dax
Total Outlets = DISTINCTCOUNT(fact_sales[outlet_identifier])
```
**Format:** Whole number
**Example:** 10

---

### Total Transactions
**Business Definition:** Total number of item-outlet rows
**Formula:**
```dax
Total Transactions = COUNTROWS(fact_sales)
```
**Format:** Whole number
**Example:** 8,523

---

## Advanced Measures

### Sales % of Total
**Business Definition:** Contribution of current selection 
to overall total sales
**Formula:**
```dax
Sales % of Total = 
VAR CurrentSales = [Total Sales]
VAR AllSales = 
    CALCULATE([Total Sales], ALL(dim_item, dim_outlet))
RETURN
    DIVIDE(CurrentSales, AllSales, 0)
```
**Format:** Percentage, 1 decimal place
**Example:** Tier 1 = 28%

---

### Avg Sales Vs Overall %
**Business Definition:** How current selection average 
compares to overall average
**Formula:**
```dax
Avg Sales Vs Overall % = 
VAR CurrentAvg = [Avg Sales]
VAR OverallAvg = 
    CALCULATE([Avg Sales], ALL(dim_item, dim_outlet))
RETURN
    DIVIDE(CurrentAvg - OverallAvg, OverallAvg, 0)
```
**Format:** Percentage, 1 decimal place
**Example:** +2.3% above average

---

### Low Fat Sales
**Business Definition:** Total sales for Low Fat items only
**Formula:**
```dax
Low Fat Sales = 
CALCULATE(
    [Total Sales],
    dim_item[item_fat_content] = "Low Fat"
)
```
**Format:** Currency, 2 decimal places

---

### Regular Fat Sales
**Business Definition:** Total sales for Regular fat items only
**Formula:**
```dax
Regular Fat Sales = 
CALCULATE(
    [Total Sales],
    dim_item[item_fat_content] = "Regular"
)
```
**Format:** Currency, 2 decimal places

---

### Sales per Outlet
**Business Definition:** Average revenue generated per outlet
**Formula:**
```dax
Sales per Outlet = 
DIVIDE([Total Sales], [Total Outlets], 0)
```
**Format:** Currency, 2 decimal places


