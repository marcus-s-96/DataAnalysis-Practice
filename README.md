# Financial Reporting

Executive financial dashboard built as a Power BI Project (PBIP), on the Microsoft *Financial Sample* dataset.

## Structure

```
Financial.pbip                 Open this in Power BI Desktop
Financial.Report/              Report (PBIR format)
  definition/pages/            Pages and visuals (one folder per visual)
  StaticResources/
    RegisteredResources/       Custom theme: ExecutiveClean.json
Financial.SemanticModel/       Semantic model (TMDL format)
  definition/tables/           Tables, columns and measures
```

## Data source

The `financials` table imports from:

```
...\Documents\Data analysis\Dataset\Financial Sample.xlsx  (table: financials)
```

The path is hard-coded in `Financial.SemanticModel/definition/tables/financials.tmdl`. Update it if the file lives elsewhere, then refresh.

## Measures (`financials` › KPIs)

| Measure          | Definition                                   |
|------------------|----------------------------------------------|
| Net Sales        | `SUM(financials[Sales])`                     |
| Gross Profit     | `SUM(financials[Profit])`                    |
| Profit Margin    | Gross Profit / Net Sales                     |
| Units Sold Total | `SUM(financials[Units Sold])`                |
| Discount Rate    | Discounts / Gross Sales                      |

## Report

**Executive Overview** — KPI row, monthly sales/profit trend, sales by segment, profit by country, product performance table, and margin by discount band. Filter by Year, Segment and Country.

## Working with Git

- Save changes in Power BI Desktop, then commit the PBIP folders.
- `localSettings.json` and `cache.abf` are user/local state and are ignored.
