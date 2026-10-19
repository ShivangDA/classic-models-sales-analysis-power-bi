# Classic Models Sales Analysis | SQL, Excel & Power BI

> **From raw order records to a business-facing sales dashboard.**

## Project Story

Sales data is most useful when it helps a business understand what is happening, where performance is coming from, and which areas deserve closer attention. This project takes the Classic Models sales dataset and turns it into a reporting workflow using **SQL, Excel, and Power BI**.

The workflow starts with the sales data, prepares a reporting view by joining order, order-detail, customer, product, employee, and office information, and then uses Power BI to present the resulting information in dashboard form. The goal is to make sales performance easier to explore across products, customers, dates, and geographies.

This repository contains the dashboard, source dataset, and SQL preparation logic so that the work can be reviewed and reproduced.

## Business Questions

The analysis is designed to help explore questions such as:

- How does sales performance change over time?
- Which product lines and products contribute to sales?
- Which customers and markets are represented in the order data?
- How do order quantities, sales value, and cost of sales compare?
- What patterns become visible when sales data is explored interactively?

These are the questions the dashboard can help investigate. Specific findings should be added after validating the report values and documenting the results observed in the dashboard.

## Project Workflow

1. **Inspect the source data** — review the sales dataset and its available fields.
2. **Prepare the reporting view in SQL** — join orders and order details with product, customer, employee, and office information.
3. **Validate the calculations** — reconcile sales and cost totals with the underlying order-detail records before relying on them.
4. **Explore the report in Power BI** — use dashboard pages and visuals to investigate sales performance.
5. **Communicate the results** — capture dashboard screenshots and document evidence-based findings.

## Tools Used

- **SQL** — joins and reporting-view preparation
- **Microsoft Excel** — source data inspection and storage
- **Microsoft Power BI Desktop** — data modeling and interactive reporting

## Repository Structure

```text
classic-models-sales-analysis-power-bi/
├── README.md
├── data/
│   └── Sales_Data.xlsx
├── sql/
│   └── create_sales_view.sql
├── powerbi/
│   └── Classic_Models_Dashboard.pbix
└── screenshots/
    ├── Page1_PowerBI.png
    └── Page2_PowerBI.png
```

> Keep the filenames in the repository consistent with this structure, or update the paths above to match your actual filenames.

## Dashboard Preview

### Page 1

![Power BI dashboard — Page 1](screenshots/Page1_PowerBI.png)

### Page 2

![Power BI dashboard — Page 2](screenshots/Page2_PowerBI.png)

GitHub displays these images when the screenshot files are committed to the `screenshots/` folder with the filenames shown above.

## Data and SQL Notes

The supplied Excel file is named `Sales Data for Power BI.xlsx`. The SQL document contains a `CREATE OR REPLACE VIEW` statement for `classicmodels.sales_data_for_power_bi`. The view combines fields from orders, order details, customers, products, employees, and offices.

**Calculation validation is important:** the supplied SQL uses expressions equivalent to `SUM(QuantityOrdered) * SUM(priceEach)` for sales value and `SUM(buyPrice) * SUM(QuantityOrdered)` for cost of sales. Multiplying sums can overstate totals when a group contains multiple order-detail rows. Validate these calculations at the appropriate order-detail grain before treating the resulting KPIs as authoritative. A typical row-level calculation is `QuantityOrdered * priceEach` for sales and `QuantityOrdered * buyPrice` for cost, followed by summing those row-level values.

The SQL document should be converted to a `.sql` file for easier review and execution.

## How to Open the Project

1. Clone or download this repository.
2. Open `sql/create_sales_view.sql` in your SQL client and check the database/schema prerequisites.
3. Open `powerbi/Classic_Models_Dashboard.pbix` in Power BI Desktop.
4. If Power BI prompts for a data source, configure the connection to your environment and refresh the model.
5. Review the dashboard pages and compare the displayed metrics with validated SQL results.

The dashboard may depend on a database connection or local data source. A `.pbix` file does not guarantee that another person can refresh the report without configuring the original data source.

## Limitations and Next Steps

- Validate the sales and cost calculations against the underlying order-detail records.
- Document the actual findings and business recommendations supported by the dashboard.
- Add clear KPI definitions and explain any assumptions.
- Confirm that the Power BI file opens and that its data source can be configured by another user.
- Keep the screenshot images in the `screenshots/` folder so the dashboard preview renders on GitHub.

## Author

**Data Analytics Portfolio Project**

Built to demonstrate a practical workflow from data preparation in SQL to interactive reporting in Power BI.
