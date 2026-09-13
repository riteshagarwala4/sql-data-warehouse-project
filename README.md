# Data Warehouse and Analytics Project

Welcome to the **Data Warehouse and Analytics Project** repository! 
This project demonstrates a comprehensive data warehousing and analytics solution, from building a data warehouse to generating actionable insights. Designed as a portfolio project that highlights industry best practices in data engineering and analytics.

---

## Architecture at a Glance

```text
ERP + CRM CSV files
        ↓
Bronze layer — raw source data loaded into SQL Server
        ↓
Silver layer — data cleaned, standardised, and integrated
        ↓
Gold layer — star-schema views ready for reporting and analysis
```

The project uses the Medallion Architecture (Bronze → Silver → Gold) to keep raw data, transformation logic, and business-ready data clearly separated.

## My Hands-On Implementation

I completed this as a guided, hands-on implementation while learning from the Data With Baraa SQL Data Warehouse course. I manually worked through the database setup, Bronze/Silver/Gold loading process, data cleaning, dimensional modelling, and data-quality checks to understand how a SQL Server warehouse is built step by step.

The goal was learning and practice: understand each query and stored procedure, run it myself, inspect the outputs, and connect the final Gold layer to analytical reporting.

---

## Project Requirements

### Building the Data Warehouse (Data Engineering)

#### Objective
Develop a modern data warehouse using SQL Server to consolidate sales data, enabling analytical reporting and informed decision-making.

#### Specifications
- **Data Sources**: Import data from two source systems (ERP and CRM) provided as CSV files.
- **Data Quality**: Cleanse and resolve data quality issues before analysis.
- **Integration**: Combine both sources into a single, user-friendly data model designed for analytical queries.
- **Scope**: Focus on the latest dataset only; historization of data is not required.
- **Documentation**: Provide clear documentation on the data model to support both business stakeholders and analytics teams.

### BI: Analytics & Reporting (Data Analytics)

#### Objective
Develop SQL-based analytics to deliver detailed insights into:
- **Customer Behavior**
- **Product Performance**
- **Sales Trends**

These insights give stakeholders key business metrics to support strategic decision-making.

---

## How to Run

**Requirements:** SQL Server, SQL Server Management Studio (SSMS), and the CSV files in the `datasets` folder.

1. Open and run `scripts/init_database.sql`. This creates the `DataWarehouse` database and Bronze, Silver, and Gold schemas. It drops an existing database with the same name, so use it only for this learning project.
2. Run `scripts/bronze/ddl_bronze.sql` and `scripts/silver/ddl_silver.sql` to create the Bronze and Silver tables.
3. In `scripts/bronze/proc_load_bronze.sql`, update the CSV file paths to match the local location of this repository's `datasets` folder. Run the script, then execute `EXEC bronze.load_bronze;`.
4. Run `scripts/silver/proc_load_silver.sql`, then execute `EXEC silver.load_silver;`.
5. Run `scripts/gold/ddl_gold.sql` to create the reporting-ready Gold views.
6. Run `tests/quality_checks_silver.sql` and `tests/quality_checks_gold.sql` to validate the transformed data.

After these steps, the Gold views can be queried directly or used by the companion [SQL Sales Analysis Project](https://github.com/riteshagarwala4/sql-sales-analysis-project).

---

## License

This project is licensed under the [MIT License](LICENSE). You are free to use, modify, and share this project with proper attribution.

## About Me

Hi! I'm **Ritesh Agarwala**. I work as an MIS Analyst at Wipro, working with Power BI and Excel to create reports and dashboards.

I am currently upskilling and transitioning into data/ai engineering. After recently learning SQL, I built this project to apply and practice data warehousing concepts, ETL, and analytical querying step by step.

* **LinkedIn**: [Profile](https://www.linkedin.com/in/ritesh-agarwala-255182297)
* **Email**: [riteshagarwala4@gmail.com](mailto:riteshagarwala4@gmail.com)



