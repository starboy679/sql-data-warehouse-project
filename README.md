# SQL Data Warehouse & Analytics Project

<p align="center">
  <img src="https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white" />
  <img src="https://img.shields.io/badge/T--SQL-4479A1?style=for-the-badge&logo=databricks&logoColor=white" />
  <img src="https://img.shields.io/badge/ETL-Process-orange?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Data%20Warehouse-0078D4?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" />
</p>

## 📌 Project Overview

This project demonstrates the design and implementation of a modern SQL Data Warehouse using Microsoft SQL Server.

The objective is to consolidate raw sales data from two different source systems (CRM and ERP), transform and cleanse the data, and organize it into a structured Data Warehouse optimized for analytical queries and business intelligence.

The project follows the Medallion Architecture (Bronze, Silver, and Gold), implementing ETL processes, data quality checks, and dimensional modeling using a Star Schema.

## 🎯 Project Objectives

- Build a modern Data Warehouse using Microsoft SQL Server.
- Integrate data from multiple CRM and ERP source systems.
- Develop ETL pipelines using SQL Stored Procedures.
- Clean, standardize, and transform raw datasets.
- Implement the Bronze, Silver, and Gold architecture.
- Design Fact and Dimension Views using Star Schema.
- Perform data quality checks and validation.
- Document data architecture, integration flow, and data models.

## 🏗️ Data Architecture

The project follows the Medallion Architecture, consisting of three layers:

### 🥉 1. Bronze Layer – Raw Data

The Bronze Layer stores raw data imported from CRM and ERP CSV source files.

**Operations:**
- Create raw data tables.
- Load source files using BULK INSERT.
- Preserve the original source data structure.
- Reload raw data using stored procedures.

**Source Tables:**

CRM:
- crm_cust_info
- crm_prd_info
- crm_sales_details

ERP:
- erp_cust_az12
- erp_loc_a101
- erp_px_cat_g1v2

### 🥈 2. Silver Layer – Cleansed & Transformed Data

The Silver Layer processes and standardizes the raw data from the Bronze Layer.

**Transformations:**
- Remove unwanted spaces and standardize text values.
- Handle NULL and duplicate records.
- Normalize customer demographics.
- Standardize product categories and product lines.
- Validate and convert date formats.
- Handle invalid sales values and calculate corrected amounts.
- Integrate and standardize CRM and ERP datasets.

### 🥇 3. Gold Layer – Business-Ready Data

The Gold Layer provides analytical views organized using a Star Schema.

**Dimension Views:**

- `gold.dim_customers`
  - Customer information
  - Demographics
  - Geographic information

- `gold.dim_products`
  - Product details
  - Product categories
  - Product classifications

**Fact View:**

- `gold.fact_sales`
  - Order information
  - Customer and product keys
  - Sales amounts
  - Quantities and prices
  - Order, shipping, and due dates

## 📊 Data Architecture & Diagrams

### High-Level Data Architecture
![High Level Data Architecture](docs/High%20Level%20Data%20Archetecture.jpg)

### Data Flow
![Data Flow](docs/Data%20Flow.jpg)

### Data Integration Model
![Data Integration Model](docs/Data%20Integration%20Model.jpg)

### Gold Layer – Data Mart
![Data Mart](docs/Data%20Mart.jpg)

## 🛠️ Technologies & Tools

| Technology | Purpose |
|---|---|
| Microsoft SQL Server | Database Engine |
| SQL Server Management Studio (SSMS) | Database Development |
| T-SQL | Data Transformation & ETL |
| SQL Stored Procedures | ETL Pipeline Execution |
| BULK INSERT | CSV Data Ingestion |
| Git & GitHub | Version Control |
| Draw.io | Data Architecture & Modeling |

## 📂 Project Structure

```text
sql-data-warehouse-project/
│
├── datasets/
│   ├── source_crm/
│   │   ├── cust_info.csv
│   │   ├── prd_info.csv
│   │   └── sales_details.csv
│   │
│   └── source_erp/
│       ├── CUST_AZ12.csv
│       ├── LOC_A101.csv
│       └── PX_CAT_G1V2.csv
│
├── docs/
│   ├── Data Flow.jpg
│   ├── Data Integration Model.jpg
│   ├── Data Mart.jpg
│   ├── High Level Data Archetecture.jpg
│   └── data_catalog.md
│
├── scripts/
│   ├── bronze/
│   │   ├── ddl_bronze.sql
│   │   └── proc_load_bronze.sql
│   │
│   ├── silver/
│   │   ├── ddl_silver.sql
│   │   └── proc_load_silver.sql
│   │
│   ├── gold/
│   │   └── ddl_gold.sql
│   │
│   └── inti_database.sql
│
├── tests/
│   ├── quality_check_silver.sql
│   └── quality_checks_gold.sql
│
├── LICENSE
└── README.md
```

## 🚀 Execution Workflow

Execute the SQL scripts in the following order:

**1. Database Initialization**
- Run `scripts/inti_database.sql`.
- Creates the `DataWarehouse` database and the Bronze, Silver, and Gold schemas.

**2. Bronze Layer**
- Run `scripts/bronze/ddl_bronze.sql`.
- Run `scripts/bronze/proc_load_bronze.sql`.
- Execute `bronze.load_bronze`.

**3. Silver Layer**
- Run `scripts/silver/ddl_silver.sql`.
- Run `scripts/silver/proc_load_silver.sql`.
- Execute `silver.load_silver`.

**4. Gold Layer**
- Run `scripts/gold/ddl_gold.sql`.
- Creates the customer dimension, product dimension, and sales fact views.

**5. Data Quality Validation**
- Execute `tests/quality_check_silver.sql`.
- Execute `tests/quality_checks_gold.sql`.

**Note:** Update the CSV file paths inside the Bronze loading procedure to match your local dataset directory before execution. The database initialization script drops and recreates the `DataWarehouse` database if it already exists.

## 🔍 Data Quality & Validation

Data quality scripts are included to validate the Silver and Gold layers.

**Silver Layer Checks:**
- NULL and duplicate primary keys.
- Unwanted spaces.
- Data standardization.
- Invalid dates and date ranges.
- Sales amount consistency.
- Invalid or negative product costs.
- Customer demographic consistency.

**Gold Layer Checks:**
- Uniqueness of surrogate keys.
- Fact-to-dimension relationships.
- Referential integrity between dimension and fact views.

## 📚 Key Data Engineering Concepts Applied

- Medallion Architecture
- ETL (Extract, Transform, Load)
- Data Cleansing & Standardization
- Data Integration
- SQL Window Functions
- Common Table Expressions and Subqueries
- Stored Procedures
- BULK INSERT
- Surrogate Keys
- Dimensional Modeling
- Star Schema
- Data Quality & Validation

## 📖 Documentation

Detailed Gold Layer documentation is available in:

[`docs/data_catalog.md`](docs/data_catalog.md)

## 🙏 Acknowledgments

This project was inspired by the SQL Data Warehouse project by **Data With Baraa**.

The implementation, project organization, documentation, and practical learning process were carried out as part of my Data Engineering development journey.

---

## 👨‍💻 About Me

**Abdalbagi Mokhtar**  
Aspiring Data Engineer | SQL | Python | Data Warehousing

### 🌐 Connect With Me

<p align="left">
  <a href="https://starboy679.github.io/Abdalbagi-Personal_Portfolio/" target="_blank">
    <img src="https://img.shields.io/badge/Portfolio-Visit%20My%20Website-6C63FF?style=for-the-badge&logo=googlechrome&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/in/abdalbagi-mokhtar-25151a296">
    <img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" />
  </a>
  <a href="https://github.com/starboy679">
    <img src="https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github&logoColor=white" />
  </a>
  <a href="https://www.instagram.com/starboy_249">
    <img src="https://img.shields.io/badge/Instagram-Follow-E4405F?style=for-the-badge&logo=instagram&logoColor=white" />
  </a>
  <a href="https://x.com/Starboy_249">
    <img src="https://img.shields.io/badge/X-Follow-000000?style=for-the-badge&logo=x&logoColor=white" />
  </a>
</p>


⭐ If you find this project useful, feel free to explore the repository and connect with me!
