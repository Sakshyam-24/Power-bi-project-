# Coffee Sales Dashboard (Power BI)

A professional, ready-to-build Power BI dashboard for a coffee shop: clean
sample data, production-ready DAX measures, and a documented single-page report
layout matching a modern executive style.

## Preview

> KPI cards (Total Amount, Total Coffees Sold) → Horizontal bar chart (Coffee
> Sold by type) → Donut (Cash vs Card split) → Area chart (Monthly Revenue).

## Contents

```
Coffee-Sales-Dashboard/
├── data/
│   ├── coffee_sales.csv          # 3,636 transaction rows (~$115K revenue)
│   ├── coffee_products.csv       # 8 coffees with price & description
│   └── payment_methods.csv       # Card / Cash lookup
├── DAX/
│   └── Measures.dax              # 25+ production DAX measures
├── docs/
│   ├── DataDictionary.md         # schema, relationships, DateTable M
│   └── DashboardDesign.md        # visual layout, colours, build steps
└── README.md
```

## Getting Started

1. Install **Power BI Desktop** (free).
2. Clone this repository:

   ```bash
   git clone https://github.com/Sakshyam-24/Power-bi-project-.git
   ```

3. Open Power BI Desktop → **Get Data → Text/CSV** → load all three files from `data/`.
4. Create the DateTable from the M snippet in `docs/DataDictionary.md` and mark it as the date table.
5. Create the relationship: `Sales[CoffeeName]` → `Products[CoffeeName]`.
6. Create the relationship: `Sales[OrderDate]` → `DateTable[Date]`.
7. Paste the measures from `DAX/Measures.dax` into a new Measures table or the Sales table.
8. Follow `docs/DashboardDesign.md` to build the single-page report.

## Key Metrics (from sample data)

| Metric | Value |
| --- | --- |
| Total Revenue | ~$115K |
| Total Coffees Sold | 3,636 |
| Date Range | March 2024 – March 2025 |
| Payment Split | ~97.5% Card / ~2.5% Cash |
| Top Coffee (Revenue) | Latte |
| Top Coffee (Volume) | Americano with Milk |

## Data Summary

| Coffee | Avg Price | Approx Revenue | Approx Volume |
| --- | --- | --- | --- |
| Latte | $5.50 | ~$28K | ~790 txns |
| Americano with Milk | $5.00 | ~$25K | ~910 txns |
| Cappuccino | $5.75 | ~$18K | ~460 txns |
| Americano | $4.50 | ~$15K | ~500 txns |
| Hot Chocolate | $6.00 | ~$10K | ~255 txns |
| Cocoa | $6.25 | ~$9K | ~240 txns |
| Cortado | $5.25 | ~$8K | ~275 txns |
| Espresso | $3.50 | ~$3K | ~206 txns |

## License

Sample data is synthetic. Safe for portfolios, demos, and teaching.