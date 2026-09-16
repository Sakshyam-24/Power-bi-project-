# Nepal E-Commerce Dashboard - Report Design Specification

## Color Palette

| Element | Color | Hex Code |
|---------|-------|----------|
| Primary | Dark Navy | #1a365d |
| Secondary | Medium Blue | #2c5282 |
| Accent | Orange | #ed8936 |
| Success | Green | #38a169 |
| Warning | Yellow | #d69e2e |
| Danger | Red | #e53e3e |
| Background | Light Gray | #edf2f7 |

## Category Colors

| Category | Color |
|----------|-------|
| Electronics | #2c5282 |
| Clothing | #ed8936 |
| Groceries | #38a169 |
| Home & Kitchen | #805ad5 |
| Beauty | #d53f8c |
| Books | #d69e2e |

## City Colors

| City | Color |
|------|-------|
| Kathmandu | #1a365d |
| Pokhara | #2c5282 |
| Lalitpur | #3182ce |
| Bhaktapur | #4299e1 |
| Biratnagar | #63b3ed |
| Chitwan | #90cdf4 |

## Page Layout

### Page 1: Executive Overview

```
┌─────────────────────────────────────────────────────────┐
│  HEADER: Nepal E-Commerce Sales Intelligence            │
├─────────┬─────────┬─────────┬─────────┬─────────────────┤
│ KPI Card│ KPI Card│ KPI Card│ KPI Card│   Date Slicer   │
│ Revenue │ Orders  │ AOV     │ Rating  │                 │
├─────────┴─────────┴─────────┴─────────┴─────────────────┤
│  Monthly Revenue Trend (Line Chart)                     │
│  - X: Month  - Y: Revenue  - Trend Line: Yes           │
├─────────────────────────┬───────────────────────────────┤
│  Revenue by City        │  Revenue by Category          │
│  (Bar Chart - Horizontal)│  (Bar Chart - Vertical)     │
├─────────────────────────┴───────────────────────────────┤
│  Payment Method Distribution (Donut Chart)              │
└─────────────────────────────────────────────────────────┘
```

### Page 2: Geographic Drill-Down

```
┌─────────────────────────────────────────────────────────┐
│  CITY FILTER SLICER                                     │
├─────────────────────────────────────────────────────────┤
│  Geographic Map Visual                                  │
│  - Bubble size: Revenue                                 │
│  - Color intensity: Order volume                        │
├─────────────────────────┬───────────────────────────────┤
│  City Performance Table │  Category by City Heatmap    │
│  - City, Revenue, Orders│  - Rows: Cities              │
│  - % of Total, Growth   │  - Columns: Categories       │
│                         │  - Values: Revenue            │
└─────────────────────────┴───────────────────────────────┘
```

### Page 3: Customer & Product Insights

```
┌─────────────────────────────────────────────────────────┐
│  AGE GROUP FILTER  │  PAYMENT METHOD FILTER             │
├─────────────────────┴───────────────────────────────────┤
│  Customer Age Distribution (Histogram)                  │
├─────────────────────────┬───────────────────────────────┤
│  Revenue by Age Group   │  Payment Trend Over Time      │
│  (Stacked Bar)          │  (Stacked Area)               │
├─────────────────────────┴───────────────────────────────┤
│  Top 10 Products by Revenue (Bar Chart)                 │
└─────────────────────────────────────────────────────────┘
```

## Visual Specifications

### KPI Cards
- Background: Primary color (#1a365d)
- Text: White
- Font: Segoe UI Bold
- Title size: 10pt
- Value size: 24pt
- Border radius: 8px

### Charts
- Font: Segoe UI
- Title: 14pt Bold
- Axis labels: 10pt
- Data labels: 9pt
- Gridlines: Light gray, dashed
- Background: White

### Filters/Slicers
- Style: Dropdown or list
- Font: 10pt
- Background: Light gray (#edf2f7)
- Selection: Primary blue (#2c5282)

## DAX Measures Reference

### KPI Measures
```dax
Total Revenue = SUM(Sales[TotalAmount])
Total Orders = COUNTROWS(Sales)
Avg Order Value = DIVIDE([Total Revenue], [Total Orders], 0)
Customer Rating = AVERAGE(Sales[Rating])
Unique Cities = DISTINCTCOUNT(Sales[City])
Unique Categories = DISTINCTCOUNT(Sales[Category])
```

### Time Intelligence
```dax
Revenue MTD = TOTALMTD([Total Revenue], 'Date'[Date])
Revenue PY = CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Date'[Date]))
Revenue Growth % = DIVIDE([Total Revenue] - [Revenue PY], [Revenue PY], 0)
Orders PY = CALCULATE([Total Orders], SAMEPERIODLASTYEAR('Date'[Date]))
```

### Category Analysis
```dax
Electronics Revenue = CALCULATE([Total Revenue], Sales[Category] = "Electronics")
Electronics % = DIVIDE([Electronics Revenue], [Total Revenue], 0)
Top Category = TOPN(1, ALL(Sales[Category]), [Total Revenue], DESC)
```

### Geographic Analysis
```dax
Kathmandu Revenue = CALCULATE([Total Revenue], Sales[City] = "Kathmandu")
Kathmandu % = DIVIDE([Kathmandu Revenue], [Total Revenue], 0)
Top City = TOPN(1, ALL(Sales[City]), [Total Revenue], DESC)
City Revenue Rank = RANKX(ALL(Sales[City]), [Total Revenue],, DESC)
```

## Fonts

| Element | Font | Size | Weight |
|---------|------|------|--------|
| Dashboard Title | Segoe UI | 18pt | Bold |
| Page Title | Segoe UI | 14pt | Bold |
| KPI Title | Segoe UI | 10pt | Regular |
| KPI Value | Segoe UI | 24pt | Bold |
| Chart Title | Segoe UI | 12pt | Bold |
| Axis Labels | Segoe UI | 10pt | Regular |
| Data Labels | Segoe UI | 9pt | Regular |
| Table Headers | Segoe UI | 10pt | Bold |
| Table Data | Segoe UI | 9pt | Regular |
