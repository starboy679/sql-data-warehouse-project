# SQL Data Warehouse Project

![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Data Engineering](https://img.shields.io/badge/Data%20Engineering-0078D4?style=for-the-badge)
![ETL](https://img.shields.io/badge/ETL-Process-orange?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-In%20Progress-yellow?style=for-the-badge)

## 📌 Project Overview

This project focuses on building a modern SQL Data Warehouse using Microsoft SQL Server.

The main objective is to integrate raw sales data from CRM and ERP source systems, transform it into clean and structured datasets, and prepare it for analytical reporting and business intelligence.

This is a hands-on Data Engineering learning project designed to develop practical skills in SQL, ETL processes, data modeling, and data quality management.

## 🎯 Project Objectives

- Build a modern Data Warehouse using SQL Server.
- Integrate data from multiple source systems (CRM and ERP).
- Develop ETL processes to extract, transform, and load data.
- Clean and standardize raw datasets.
- Implement the Bronze, Silver, and Gold architecture.
- Design a Star Schema for analytical reporting.
- Perform data quality checks and validation.

## 🏗️ Data Architecture

The project follows the Medallion Architecture:

### 1. Bronze Layer
Stores raw data imported from CRM and ERP CSV files without major transformations.

### 2. Silver Layer
Cleans, validates, standardizes, and transforms the raw data into structured datasets.

### 3. Gold Layer
Contains business-ready data organized into fact and dimension tables using a Star Schema.

## 🛠️ Technologies & Tools

- Microsoft SQL Server
- SQL Server Management Studio (SSMS)
- T-SQL
- Git & GitHub
- CSV Data Sources
- Draw.io (Data Architecture & Modeling)

## 📂 Project Structure

```text
sql-data-warehouse-project/
│
├── 00_setup/
├── 01_datasets/
│   ├── source_crm/
│   └── source_erp/
│
├── 02_docs/
│
├── 03_scripts/
│   ├── bronze/
│   ├── silver/
│   ├── gold/
│   └── init_database.sql
│
├── 04_tests/
│
└── README.md
```

## 📊 Expected Deliverables

- A fully structured SQL Data Warehouse.
- Automated ETL stored procedures.
- Clean and integrated datasets.
- Fact and Dimension tables.
- Data quality validation scripts.
- Data architecture and documentation.

## 🚀 Project Progress

- [x] Repository created.
- [x] Project files organized.
- [ ] SQL Server environment setup.
- [ ] Database and schemas creation.
- [ ] Bronze Layer implementation.
- [ ] Silver Layer implementation.
- [ ] Gold Layer implementation.
- [ ] Data quality testing.
- [ ] Final documentation.

## 📚 Learning Resources & Credits

This project is based on the SQL Data Warehouse project by **Data With Baraa**.

Original Repository: https://github.com/DataWithBaraa/sql-data-warehouse-project

YouTube Tutorial: https://youtu.be/9GVqKuTVANE

The project is being implemented as a hands-on learning experience, with additional practice, explanations, and documentation.

---

**Author:** Abdalbagi Mokhtar

**Field:** Aspiring Data Engineer

**GitHub:** https://github.com/starboy679
