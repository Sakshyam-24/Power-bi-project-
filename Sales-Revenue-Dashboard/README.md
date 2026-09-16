# Sales & Revenue Dashboard (Power BI)

A professional Power BI **project starter** for an executive sales & revenue
report: clean sample data, ready-to-use DAX measures, and a documented report
design. Import the files and build the report in Power BI Desktop in minutes.

> Note: this project ships **data + DAX + design docs** so you can assemble the
> `.pbix` yourself. After publishing, store your `.pbix` in `/reports`.

## Contents

```
Sales-Revenue-Dashboard/
├── data/                       # CSV source data
│   ├── sales_orders.csv        # 2,200 order-line fact rows
│   ├── products.csv            # product catalog (20)
│   ├── customers.csv           # customer master (40)
│   ├── regions.csv             # sales regions (5)
│   └── targets.csv             # annual targets (10)
├── DAX/
│   └── Measures.dax            # 20+ production-ready measures
├── docs/
│   ├── DataDictionary.md       # schema, relationships, M date table
│   └── DashboardDesign.md      # 3-page report layout + styling notes
└── README.md
```

## Getting started

1. Install Power BI Desktop (free).
2. In **Get data → Text/CSV**, load the five files from `data/`.
3. Create the date table from the M snippet in `docs/DataDictionary.md`
   and mark it as the date table.
4. Build relationships: `Customers - Sales Orders - Products`,
   `Regions - Sales Orders`, `Regions - Targets` (via Year + Region).
5. Add the measures from `DAX/Measures.dax`.
6. Follow `docs/DashboardDesign.md` to assemble the 3-page report.

## Key measures

| Measure | What it shows |
| --- | --- |
| Total Sales / Total Profit | Core revenue & gross profit KPIs |
| Profit Margin % | Profit ÷ Sales |
| Average Order Value | Sales ÷ distinct orders |
| Sales vs PY / % | Growth vs previous year |
| Target Achievement % | Sales ÷ regional target |
| Top N Products | Ranked product contribution |

## License

Sample data is synthetic and safe to use for demos, portfolios, and teaching.