# DBR361 Assignment 2 – Group O

## AdventureWorks Business Intelligence Report

## Overview

**DBR361 Assignment 2 – Group O** is a business intelligence and database reporting project developed for **Database Reporting 361**.

The project demonstrates the use of **Microsoft Power BI Report Builder** to create a structured business intelligence report using data from the **AdventureWorks2022 SQL Server database**.

The report transforms relational database data into meaningful **charts, tables, matrices, calculations, and summary information** that can be used to analyse sales performance, products, customers, stores, and business operations.

The final report was designed with a professional layout that includes a cover page, consistent headers and footers, visualisations, detailed data tables, and a report summary.

---

## Features

### Sales Analysis

The report provides visual analysis of sales performance across different years and product categories.

* Compares yearly sales performance.
* Analyses sales for **Accessories** and **Clothing**.
* Displays total sales values.
* Helps identify changes in sales performance over time.

### Customer Tax & Freight Analysis

The report includes a chart showing the relationship between customers, tax, and freight costs.

* Displays tax paid by customers.
* Displays freight/delivery costs.
* Allows comparison of costs between customers.
* Provides insight into how additional costs affect sales.

### Store & Salesperson Performance

A matrix report provides detailed information about stores and their salespeople.

The matrix includes:

* Store Name
* Salesperson
* Sales Quota
* Order Quantity
* Line Total
* Quota Achievement Indicator

The report allows users to compare salesperson and store performance against their assigned sales quotas.

### Product Category Analysis

A second matrix groups products according to their categories.

The report displays:

* Product Category
* Product Name
* Order Quantity
* Total Sales

This allows users to identify products with high order volumes and compare performance between different product categories.

### Report Summary

The report includes an overall summary containing key business metrics such as:

* Total Customers
* Total Products
* Total Sales

The report calculates an overall total sales value of approximately:

**R109,846,381.40**

---

## Technologies Used

### Business Intelligence & Reporting

* Microsoft Power BI Report Builder
* SQL Server Reporting Services (SSRS)
* Report Definition Language (RDL)

### Database

* Microsoft SQL Server
* AdventureWorks2022 Database
* Relational database queries
* SQL

### Data Analysis

* SQL queries
* Aggregations
* Grouping
* Calculated values
* Parameters
* Matrix reports
* Data visualisations

---

## Database

The project uses the **AdventureWorks2022** sample database as its primary data source.

The report retrieves information from areas of the database including:

```text
AdventureWorks2022
│
├── Production
│   ├── Product
│   ├── ProductSubcategory
│   └── ProductCategory
│
├── Sales
│   ├── SalesOrderDetail
│   ├── SalesOrderHeader
│   ├── Customer
│   ├── SalesPerson
│   └── Store
│
└── Other supporting tables
```

The SQL queries join related tables to produce meaningful business information for the report.

---

## Report Components

### Chart 1 – Total Sales per Year

This chart analyses total sales per year for the **Accessories** and **Clothing** categories.

It provides a visual comparison of category performance and demonstrates how sales change over time.

### Chart 2 – Total Tax & Freight per Customer

This chart compares customer-related tax and freight values.

It helps demonstrate the impact of additional costs associated with customer orders.

### Matrix 1 – Store & Salesperson Performance

This matrix provides a detailed view of stores, salespeople, sales quotas, order quantities, and total sales.

A quota indicator is included to show whether the relevant sales target was achieved.

### Matrix 2 – Product Category & Sales

This matrix groups products by category and displays the quantity ordered and total sales generated.

It provides a detailed view of product performance within each category.

---

## Report Parameter

The report includes a **Product Name parameter** that allows users to select products for the relevant product information report.

The parameter supports multiple product selections and is connected to the SQL query used to retrieve product information.

Example query structure:

```sql
SELECT 
    p.ProductID,
    p.Name AS ProductName,
    ps.Name AS SubcategoryName,
    pc.Name AS CategoryName,
    sod.OrderQty,
    sod.LineTotal
FROM Production.Product p
INNER JOIN Production.ProductSubcategory ps 
    ON p.ProductSubcategoryID = ps.ProductSubcategoryID
INNER JOIN Production.ProductCategory pc 
    ON ps.ProductCategoryID = pc.ProductCategoryID
INNER JOIN Sales.SalesOrderDetail sod 
    ON p.ProductID = sod.ProductID
WHERE p.Name IN (@ProdName);
```

---

## Project Structure

```text
DBR361_Assignment_2_Group_O/
│
├── DBR361_Assignment_2-Group_O.final..pdf
│   └── Final generated business intelligence report
│
└── DBR361_Assignment_2-Group_O.final..rdl
    └── Power BI Report Builder / SSRS report definition
```

---

## Report Workflow

### 1. Connect to Database

The report connects to the **AdventureWorks2022** SQL Server database.

### 2. Retrieve Data

SQL queries retrieve relevant information from the Production and Sales schemas.

### 3. Transform Data

The retrieved data is grouped and aggregated to calculate values such as:

* Order quantities
* Total sales
* Line totals
* Tax
* Freight
* Sales quotas

### 4. Create Visualisations

The processed data is presented using charts and matrix tables.

### 5. Analyse Performance

Users can compare:

* Sales across years
* Product categories
* Individual products
* Stores
* Salespeople
* Customer costs
* Sales quotas

### 6. Present Business Insights

The final report brings the different visualisations and tables together into a structured business intelligence report designed to support business decision-making.

---

## Learning Objectives

This project demonstrates:

* SQL database querying
* Relational database concepts
* Data aggregation and analysis
* Business intelligence reporting
* Power BI Report Builder
* SSRS report development
* RDL report structure
* Report parameters
* Matrix visualisations
* Data-driven charts
* Calculated fields
* Business performance analysis
* Professional report formatting

---

## Key Business Insights

The report provides several useful business insights, including:

* Comparison of yearly sales performance between product categories.
* Identification of products generating high sales values.
* Analysis of order quantities across product categories.
* Comparison of store and salesperson performance.
* Evaluation of sales quotas against actual sales.
* Analysis of customer tax and freight costs.
* Overall sales performance across the AdventureWorks dataset.

The final report records total sales of approximately **R109.85 million**, providing an overall view of the sales represented in the dataset.

---

## Future Enhancements

Future versions of the report could include:

* Interactive report filters and slicers.
* Additional sales performance KPIs.
* Profit and profit-margin analysis.
* Regional sales comparisons.
* Monthly and quarterly sales trends.
* Customer segmentation.
* Salesperson ranking dashboards.
* Drill-through reports.
* More advanced Power BI visualisations.
* Automated data refresh.
* Additional calculated measures.
* Interactive dashboards for management reporting.

---

## Team Members

### Group O

* **Alisa Peacock** – 601813
* **Ian Bruyns** – 603188
* **Miranda Itumeleng Mhlanga** – 602106

---

## Assignment Information

**Module:** Database Reporting 361 (DBR361)
**Assignment:** Assignment 2
**Group:** Group O
**Report Type:** Business Intelligence / Database Report
**Reporting Tool:** Microsoft Power BI Report Builder
**Database:** AdventureWorks2022
**Report Format:** RDL
**Submission Date:** 15 October 2025

---

## Author

**Group O – DBR361**

A database reporting project demonstrating the use of SQL Server data, Power BI Report Builder, SSRS, SQL queries, data visualisation, and business intelligence reporting to transform raw business data into meaningful insights.
