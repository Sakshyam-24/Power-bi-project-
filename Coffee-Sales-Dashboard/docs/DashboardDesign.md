# Coffee Sales Dashboard — Report Design

Clean, modern, single-page executive dashboard. Page size: 16:9. Background:
off-white (#F5F3EE). Accent colours: dark teal (#4A6670) primary, warm gold
(#C9A96E) highlight, white card backgrounds.

---

## Layout (top-to-bottom, left-to-right)

### Row 1 — KPI Cards (4 equal-width cards, height ~90 px)

| Card | Value | Subtitle |
| --- | --- | --- |
| Total Amount | `$115K` formatted | SUM of TotalAmount |
| Total Coffees Sold | `3,636` formatted | SUM of Quantity |
| Average Order Value | `$XX.XX` | AOV |
| Total Transactions | `N/A` | DISTINCTCOUNT of OrderID |

Each card has a small KPI arrow: green ▲ or red ▼ vs previous year.

### Row 2 — Two visuals, 50/50 split

**Left (50%)** — *Coffee Sold* (Horizontal Bar Chart)
- Axis: `CoffeeName` (sorted descending by value)
- Values: `SUM of Quantity`
- Label: data labels showing count
- Colour: single dark teal

**Right (50%)** — *Coffees Sold by Cash* (Donut Chart)
- Legend: `PaymentMethod` (Cash / Card)
- Values: `DISTINCTCOUNT of OrderID` or `SUM of Quantity`
- Inner label: total
- Slice colours: teal (Card) and gold (Cash)
- Annotation: percentages on each slice

### Row 3 — Full-width, tall

**Full width (100%)** — *Monthly Revenue* (Area / Line Chart)
- Axis: `DateTable[Date]` (Month granularity)
- Values: `SUM of TotalAmount`
- Smooth line with filled area beneath
- Data labels on each point (formatted in K)
- Secondary analytics: trend line, forecast optional
- Tooltip: Year-Quarter-Month + Revenue value

---

## Colour Palette

| Token | Hex | Use |
| --- | --- | --- |
| Primary | `#4A6670` | Bars, lines, card borders |
| Accent | `#C9A96E` | Cash slice, highlights |
| Background | `#F5F3EE` | Page + card fill |
| Card Background | `#FFFFFF` | KPI cards |
| Text Primary | `#2C2C2C` | Headings, labels |
| Text Secondary | `#6E6E6E` | Subtitles, axis text |

## Typography

- Headings: Segoe UI Semibold 14 pt
- KPI values: Segoe UI Bold 24 pt
- Subtitles / axis: Segoe UI 10 pt

## Interaction Notes

- All visuals cross-filter each other.
- Clicking a coffee bar filters the area chart and donut.
- Month axis is continuous, not categorical.
- Card titles use dynamic measure names (e.g. `SELECTEDVALUE`).

## Build Steps in Power BI Desktop

1. Import `coffee_sales.csv` → "Sales" table.
2. Import `coffee_products.csv` → "Products" table.
3. Create the DateTable from the M snippet in `DataDictionary.md` and mark as date table.
4. Create relationship: `Sales[CoffeeName]` → `Products[CoffeeName]`.
5. Create relationship: `Sales[OrderDate]` → `DateTable[Date]`.
6. Paste all measures from `DAX/Measures.dax`.
7. Build visuals following the layout above.