# Power BI Projects

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-1F4E79?style=for-the-badge&logo=tableau&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)

A collection of **Power BI** projects and dashboards — data modeling, DAX,
visual design, and business analytics. Each project ships with source data,
documentation, and Power BI Desktop files (`.pbix`).

---

## Table of Contents

- [Projects](#projects)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Author](#author)
- [License](#license)

## Projects

### 1. Coffee Sales Dashboard — `Coffee-Sales-Dashboard/`

A professional single-page coffee shop dashboard: KPI cards (Total Amount ~$115K,
Total Coffees Sold 3,636), horizontal bar chart (coffee sold by type), donut
chart (Cash vs Card payment split ~97.5% / ~2.5%), and a monthly revenue area
chart (March 2024 – March 2025). Includes 25+ ready-to-use **DAX measures**
(KPIs, time intelligence, payment analysis, coffee rankings).

> **Metrics**: Total Revenue, Total Coffees Sold, AOV, Revenue vs PY, Cash %,
> Top Coffee by Revenue, Espresso Based %, and more.

See [`Coffee-Sales-Dashboard/README.md`](Coffee-Sales-Dashboard/README.md).

### 2. Sales & Revenue Dashboard — `Sales-Revenue-Dashboard/`

A professional, ready-to-build executive sales report. Includes a clean sample
dataset (2,200 orders across 2024–2025), 20 production-ready **DAX measures**
(KPIs, time intelligence, target analysis, rankings, customer insights), and a
documented 3-page report design (Executive Overview, Regional Drill-Down,
Product & Customer Insights).

> **Measures**: Total Sales, Profit Margin %, AOV, Sales vs PY, Target
> Achievement %, Top N Products, Repeat Customer Share, and more.

See [`Sales-Revenue-Dashboard/README.md`](Sales-Revenue-Dashboard/README.md).

### 3. US Candy Distributor — `US+Candy+Distributor/`

An end-to-end analytics project built on the Maven Analytics **Candy
Distributor** challenge dataset:

- `Candy_Sales.csv` — ~10,000 order-line records
- `Candy_Products.csv` — 15 Wonka-style products with price & cost
- `Candy_Factories.csv` — 5 factory locations (lat/long)
- `Candy_Targets.csv` — 2024 sales targets by division
- `uszips.csv` — US zip / geo reference for map visuals

Each data field is documented in `candy_distributor_data_dictionary.csv`.

### 4. Power Bi Day 3 — `Power Bi Day 3.pbix`

Practice report built during a Power BI workshop — an easy entry point for
seeing standard visuals, filters, and basic DAX applied to sample data.

`power bi.pbix` — current working dashboard file (candy dataset based).

## Tech Stack

- **Language:** DAX, M (Power Query)
- **Tool:** Power BI Desktop
- **Version control:** Git / GitHub
- **Data sources:** CSV

## Getting Started

1. Install [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).
2. Clone this repository:

   ```bash
   git clone https://github.com/Sakshyam-24/Power-bi-project-.git
   ```

3. Open any `.pbix` file, or import the CSVs (see each project folder for the
   recommended model setup and measures).

## Author

- **Sakshyam Pandit** — [GitHub](https://github.com/Sakshyam-24) ·
  [paditsakshyam321@gmail.com](mailto:paditsakshyam321@gmail.com)

## License

This repository is provided for learning and portfolio purposes. The Maven
dataset is property of Maven Analytics and used for educational demonstration.