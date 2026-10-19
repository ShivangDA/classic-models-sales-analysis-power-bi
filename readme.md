# Classic Models Sales Analysis | SQL, Excel & Power BI

> **Project story:** turning sales records into an interactive dashboard for exploring business performance.

## Project Overview

This project uses the Classic Models sales dataset to demonstrate a data analytics workflow with SQL, Excel, and Microsoft Power BI. The SQL query combines order information with product, customer, employee, and office details, while the Power BI report presents the data through dashboard pages.

The goal is to make sales performance easier to explore across time, products, customers, and geographic markets.

## Business Questions

This project is designed to help investigate:

- How does sales performance change over time?
- Which products and product lines contribute to sales?
- Which customers and geographic markets appear in the sales data?
- How do order quantities, sales value, and cost of sales compare?
- What patterns can be explored through the Power BI dashboard?

Specific findings should be added after checking the dashboard and validating the underlying calculations.

## Tools Used

- **SQL** — joins and reporting-view preparation
- **Microsoft Excel** — source dataset
- **Microsoft Power BI Desktop** — data modeling and interactive visualization

## Project Files

- `Classic+Models+Dashboard+with+Data.pbix` — Power BI dashboard and data model
- `Query+-+Create+View+for+Power+BI+.docx` — original SQL query document
- `Sales+Data+for+Power+BI.xlsx` — source sales dataset
- `screenshots/` — dashboard screenshots

## Dashboard Preview

### Page 1

![Power BI dashboard – Page 1](screenshots/Page1_PowerBI.png)

### Page 2

![Power BI dashboard – Page 2](screenshots/Page2_PowerBI.png)
## SQL and Data Validation

The SQL document defines a reporting view that joins orders and order details with customer, product, employee, and office information.

**Important calculation check:** the original query uses expressions equivalent to `SUM(QuantityOrdered) * SUM(priceEach)` for sales value and `SUM(buyPrice) * SUM(QuantityOrdered)` for cost of sales. Multiplying independent sums can overstate totals when a group contains multiple order-detail records.

A safer row-level calculation is:

- Sales value per order-detail row: `QuantityOrdered * priceEach`
- Cost per order-detail row: `QuantityOrdered * buyPrice`

Then sum those row-level values to calculate totals. Validate the measures against the underlying records before relying on the dashboard's KPIs.

## How to Open the Project

1. Open the `.pbix` file in Power BI Desktop.
2. If prompted, configure the required data source and refresh the report.
3. Review the SQL query document and adapt the query to your database and SQL dialect if needed.
4. Compare dashboard totals with validated SQL results.

The Power BI report may depend on a database connection or local source path. Another user may need to configure that source before refreshing the report.

## Future Improvements

- Validate sales, cost, and profit calculations.
- Add evidence-based findings and business recommendations.
- Document KPI definitions and assumptions.
- Include a runnable `.sql` script alongside the original Word document.
- Verify that the Power BI report can be opened and refreshed on another machine.

## Author

**Data Analytics Portfolio Project**
