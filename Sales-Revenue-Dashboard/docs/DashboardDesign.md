# Dashboard Design — 3-Page Executive Report

A professional, clean layout reference for building the `.pbix` in Power BI
Desktop. Page size: 16:9. Theme: white background, dark navy header, one accent
color (e.g. #1F4E79 / #2E75B6), cards with soft shading.

## Page 1 — Executive Overview

Top row (KPI cards): **Total Sales**, **Profit**, **Profit Margin %**, **Average Order Value**,
each with a small sales-vs-PY % indicator.

Visuals:
- Line chart — *Sales & Profit by Month* (Date[Year-Month]).
- Donut chart — *Sales by Category*.
- Bar chart — *Top 5 Products by Sales*.
- Clustered bar — *Sales by Region* with target reference line.

Slicers: **Year**, **Category**, **Segment**.

## Page 2 — Regional Drill-Down

- Map — *Sales by State* (bubble size = SalesAmount).
- Column chart — *Sales vs Target by Region* (Target Achievement % as line).
- Table — *Region, Area Manager, Sales, vs PY %, Target %*.
- Waterfall — *Sales vs PY by Region*.

Slicers: **Year**, **Region** (synced with page 1).

## Page 3 — Product & Customer Insights

- Treemap — *Sales by SubCategory*.
- Table — *Top 10 Products*: Sales, Profit Margin %, Rank, % of total.
- Bar chart — *Sales by Customer Segment*.
- Table / matrix — *Customers by Profit*, highlight negative-profit rows.
- Matrix — *Category × Region* sales.

## Interactivity

- Cross-filter between all pages; buttons (bookmarks) to navigate pages.
- Tooltips on KPI cards showing MTD / QTD / YTD.
- Dynamic titles using `SELECTEDVALUE` (e.g. "Sales by Region — 2025 (West)").
- Mobile layout option enabled for phone viewing.

## Checks before publishing

1. All measures from `DAX/Measures.dax` created and formatted.
2. Date table marked as date table; relationships 1:* with single direction.
3. Data categories set (City → City, State → State or Province, Region → Place).
4. `SUMX` measures (discount, profit) verified against Excel sample rows.
5. Conditional formatting on margin and target-achievement columns.