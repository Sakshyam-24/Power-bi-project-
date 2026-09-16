# Nepal E-Commerce Sales Dashboard

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-1F4E79?style=for-the-badge&logo=tableau&logoColor=white)
![Nepal](https://img.shields.io/badge/Nepal-DC143C?style=for-the-badge&logo=nepal&logoColor=white)

A professional executive dashboard analyzing **1,200+ e-commerce transactions** across Nepal — Kathmandu, Pokhara, Lalitpur, Bhaktapur, Biratnagar, and Chitwan.

---

## Dashboard Overview

| Feature | Description |
|---------|-------------|
| **KPI Cards** | Total Revenue, Orders, Avg Order Value, Customer Rating |
| **Revenue Trend** | Monthly revenue line chart with growth indicators |
| **Geographic Analysis** | City-wise revenue bubble map |
| **Category Performance** | Horizontal bar chart by product category |
| **Payment Distribution** | Donut chart (eSewa, Khalti, COD, Bank Transfer) |
| **Customer Segmentation** | Age group and spending tier analysis |
| **Filters** | City, Category, Payment Method, Date Range |

---

## Report Pages

### Page 1: Executive Overview
- High-level KPIs
- Revenue trend (monthly)
- Top cities and categories

### Page 2: Geographic Drill-Down
- City-wise revenue comparison
- Province-level filtering
- Regional performance metrics

### Page 3: Customer & Product Insights
- Customer age group analysis
- Payment method trends
- Category profitability heatmap

---

## DAX Measures Included

```dax
Total Revenue = SUM(Sales[TotalAmount])
Total Orders = COUNTROWS(Sales)
Avg Order Value = [Total Revenue] / [Total Orders]
Customer Rating = AVERAGE(Sales[Rating])

// Time Intelligence
Revenue MTD = TOTALMTD([Total Revenue], 'Date'[Date])
Revenue PY = CALCULATE([Total Revenue], SAMEPERIODLASTYEAR('Date'[Date]))
Revenue Growth % = ([Total Revenue] - [Revenue PY]) / [Revenue PY]

// Category Analysis
Electronics Revenue = CALCULATE([Total Revenue], Sales[Category] = "Electronics")
Top City = TOPN(1, ALL(Sales[City]), [Total Revenue], DESC)
```

---

## Data Model

| Table | Description |
|-------|-------------|
| `Sales` | 1,200 transaction records |
| `Date` | Calendar table for time intelligence |
| `Cities` | City and province reference |
| `Categories` | Product category details |

---

## Getting Started

1. Open `Nepal_Ecommerce_Dashboard.pbix` in Power BI Desktop
2. Refresh data connections if needed
3. Use slicers to filter by:
   - City
   - Category
   - Payment Method
   - Date Range

---

## Key Insights from Dashboard

1. **Kathmandu** generates 37% of total revenue
2. **Electronics** is the highest-revenue category
3. **Digital wallets** (eSewa + Khalti) capture 65% of transactions
4. **25-34 age group** is the largest customer segment
5. Revenue peaks during festival seasons (Oct-Nov)

---

## Related Projects

This dashboard complements the Python analysis in:
- [Python-for-Data-Analytics-](https://github.com/Sakshyam-24/Python-for-Data-Analytics-) — Full EDA and ML models

---

**Author:** Sakshyam Pandit  
**Date:** September 2026
