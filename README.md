# vanarsdel-market-analysis

A Power BI dashboard analyzing market performance across manufacturers, built with DAX measures, a custom Date Table, and interactive visuals including a map, donut chart, and trend lines.

## 📊 Overview

This dashboard analyzes revenue and market share for VanArsdel and competing manufacturers (Natura, Aliqui, Currus, Pirum, Abbas, Quibus, and others) across multiple years and countries, with a focus on year-on-year growth trends.

## 🎯 Objectives

- Track total revenue and year-on-year (YoY) growth
- Compare market share across manufacturers
- Visualize revenue trends by manufacturer over time (2014–2021)
- Map sales distribution across countries
- Highlight YoY growth trend and slowdown over time

## 🛠️ Tools & Techniques

- **Power BI Desktop** — dashboard design and data modeling
- **DAX (Data Analysis Expressions)** — custom measures including YoY Growth
- **Date Table** — custom calendar table enabling time intelligence (`SAMEPERIODLASTYEAR`)
- **Map visual** — geographic sales distribution
- **Slicers** — filter by Manufacturer, Year, and Country

## 📐 Key DAX Measures

| Measure | Purpose |
|---|---|
| `Total Revenue` | Sums revenue across the selected filters |
| `YoY Growth` | Compares current year revenue to the same period last year |

Example measure:

```dax
YoY Growth = 
VAR CurrentRevenue = [Total Revenue]
VAR PriorYearRevenue = 
    CALCULATE(
        [Total Revenue],
        SAMEPERIODLASTYEAR('DateTable'[Date])
    )
RETURN
    DIVIDE(CurrentRevenue - PriorYearRevenue, PriorYearRevenue)
```

## 📅 Date Table

A custom Date Table was built to support accurate time intelligence functions (like `SAMEPERIODLASTYEAR`) rather than relying on Power BI's built-in auto date/time.

## 📈 Dashboard

**Market Overview**
- Total Revenue and YoY Growth KPI cards
- Revenue Trend Among Manufacturers (stacked column chart, 2014–2021)
- Market Share Breakdown (donut chart by manufacturer)
- Sales Distribution map (by country)
- YoY Growth trend line (showing growth slowing from ~27% in 2015 to under 7% by 2019, recovering slightly by 2021)

**Filters/Slicers available:** Manufacturer, Year, Country

![Dashboard Overview](VanArsdel%20Dashboard.png)

## 📁 Files in this Repository

- `VanArsdel Dashboard.png` — Dashboard screenshot

## 👤 Author

**Amarachukwu** — Data Entry Specialist & Administrative Secretary, transitioning into Data Analytics.
