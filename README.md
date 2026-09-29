# Sales Report Dashboard: Tableau

> Interactive Tableau dashboards analyzing sales, profit, returns, and customer behavior on the Superstore dataset, with dynamic parameters, YoY growth KPIs, and a supplementary Netflix titles analysis.

![Tableau](https://img.shields.io/badge/Tableau-Dashboard-E97627?logo=tableau&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

## Overview

This project turns the Superstore sales data into an interactive Tableau workbook that helps business users track performance, find top-selling products and categories, understand profitability, and monitor return rates. Users can switch views on the fly using parameter controls instead of navigating between separate reports.

## Tools & Technologies

- **Tableau Desktop**: data modeling, calculated fields, LOD expressions, parameters, dashboards
- **Data sources**: Superstore Orders (sample) with Returns, and a Netflix titles dataset

## Dataset

**Superstore Orders** (primary): order-level transactions including:

| Category | Fields |
|---|---|
| **Orders** | Order ID, Order Date, Customer ID, Segment |
| **Geography** | Region, State |
| **Products** | Category, Sub-Category, Product Name |
| **Financials** | Sales, Profit, Discount |
| **Returns** | Returned (Yes/No) |

**Netflix Titles** (supplementary): title, type, cast, genre (`listed_in`), rating, release year, duration. Used for the "Top Sports Movies" analysis.

## Key Calculations

- **Total Sales:** `SUM([Sales])`
- **Profit Margin:** `SUM([Profit]) / SUM([Sales])`
- **Return Rate:** `COUNTD(IF [Returned] = 'YES' THEN [Order ID] END) / COUNTD([Order ID])`
- **YoY Profit Growth:** compares the latest year's profit against the previous year using `{MAX(YEAR([Order Date]))}`
- **Order Count per Customer:** `{ FIXED [Customer ID] : COUNTD([Order ID]) }`, binned to build a histogram of customer purchase frequency
- **Percent of Total:** table calculation using `TOTAL()` for the pie and donut charts

## Dynamic Features

- **Metric selector (parameter):** switch the view between Sales, Profit, and Orders
- **View By selector (parameter):** switch the dimension between Region, Category, and Sub-Category
- **Customer set:** a Customer ID set for segmenting customers

## Worksheets

The workbook contains 17 worksheets, including:

- KPI cards (Sales, Profit Margin, Return Rate, Grand Total)
- Category-wise and Sub-Category-wise sales
- Top 5 products by sales
- Sales trend and line charts over time
- Pie and donut charts for share of sales
- Geographic map of sales by state
- Customer order-count histogram
- Group and parameter-driven views
- Top Sports Movies (Netflix dataset)

## Dashboards

1. **Dashboard 2:** the main sales overview combining KPIs, category and product breakdowns, and the map.
2. **KPI Trend:** headline KPIs with year-over-year trend comparison.

## Key Insights

<!-- Add your own findings, for example: -->

- Which category and sub-category drive the most sales and profit
- Which regions and states perform best or worst
- Whether the return rate affects profitability
- How year-over-year profit has changed

## Repository Structure

```
├── SALES_REPORT_PROJECTS.twbx   # Tableau packaged workbook (data + images included)
└── README.md
```

## How to Use

1. Download `SALES_REPORT_PROJECTS.twbx`.
2. Open it in **Tableau Desktop** (or upload it to Tableau Public or Server).
3. Use the parameter controls to change the metric and dimension, and click on charts to filter the dashboard.

## Author

**[Gangadhar Bharkade]** | [LinkedIn](https://www.linkedin.com/in/gangadhar01/) | [Email](gangadharbharkade412@gmail.com)