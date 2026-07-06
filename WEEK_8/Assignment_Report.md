# E-Commerce Order Analytics System

> **Week 8 Assignment Report**  
>
---

## Project Overview

This project presents an end-to-end E-Commerce Order Analytics System developed using Python, Pandas, SQL, and MySQL. The objective of this assignment is to simulate a real-world e-commerce analytics workflow by generating synthetic datasets, introducing intentional data quality issues, performing data cleaning and validation, storing the cleaned data in a relational database, and deriving meaningful business insights using SQL.

The project also includes a command-line reporting tool developed in Python that dynamically generates business reports by querying the database. The entire workflow demonstrates a complete data analytics pipeline from raw data generation to business intelligence reporting.

---

## Assignment Objective

The objective of this assignment is to design and develop a complete data analytics system capable of processing and analyzing e-commerce order data.

The project includes:

- Generate realistic synthetic e-commerce datasets
- Introduce intentional data inconsistencies
- Clean and validate datasets using Pandas
- Ensure data integrity across multiple tables
- Load cleaned datasets into MySQL
- Perform SQL-based business analysis
- Generate reports using a Python command-line application
- Handle critical edge cases for improved system reliability

---

## Technologies Used

- Python
- Pandas
- NumPy
- Faker
- MySQL
- SQL
- SQLAlchemy
- mysql-connector-python
- Jupyter Notebook
- VS Code / PyCharm
- Git & GitHub

---

## Project Structure

```text
Week8_ECommerce_Order_Analytics_System
│
├── Data
│   ├── raw
│   ├── Cleaned_data
│   └── reports
│
├── database
│   ├── create_tables.sql
│   ├── schema.sql
│   └── load_data.py
│
├── notebook
│   └── Ecommerce_Order_Analytics.ipynb
│
├── screenshots
│
├── scripts
│   ├── data_generation.py
│   ├── data_cleaning.py
│   ├── data_validation.py
│   ├── analytics.py
│   ├── reporting.py
│   └── utils.py
│
├── sql
│   ├── basic_queries.sql
│   ├── intermediate_queries.sql
│   └── advanced_queries.sql
│
├── Assignment_Report.md
├── requirements.txt
└── .gitignore
```

---

# Project Workflow

The project follows the workflow shown below.

```text
Synthetic Data Generation
            ↓
Dirty Data Creation
            ↓
Data Cleaning
            ↓
Data Validation
            ↓
MySQL Database
            ↓
SQL Analysis
            ↓
Python Reporting
```

---

# Dataset Information

Four synthetic datasets were generated to simulate an e-commerce business environment.

| Dataset | Records |
|----------|---------|
| Customers | 1000 |
| Products | 250 |
| Orders | 5000 |
| Order Items | 15000 |

---

## Dataset Columns

### Customers

- customer_id
- customer_name
- email
- city
- registration_date
- customer_type

### Products

- product_id
- product_name
- category
- subcategory
- unit_price

### Orders

- order_id
- customer_id
- order_date
- payment_method
- order_status

### Order Items

- item_id
- order_id
- product_id
- quantity
- selling_price
- discount_percent

---

# Data Quality Issues Introduced

To simulate real-world business data, multiple intentional inconsistencies were introduced into the generated datasets.

### Customers

- Duplicate customer records
- Invalid email addresses
- Missing city values
- Blank customer names

### Products

- Extra spaces in product names
- Inconsistent capitalization
- Missing categories
- Negative prices

### Orders

- Missing customer IDs
- Invalid order dates
- Duplicate order IDs
- Incorrect payment methods

### Order Items

- Negative quantities
- Zero quantities
- Invalid product IDs
- Missing order IDs

---

# Data Cleaning

Before loading the datasets into MySQL, extensive cleaning was performed using Pandas.

Cleaning operations included:

- Removed duplicate customer records
- Removed duplicate order IDs
- Removed duplicate item IDs
- Converted date columns into proper datetime format
- Standardized text capitalization
- Removed unnecessary white spaces
- Converted invalid emails to missing values
- Replaced missing categorical values
- Removed invalid prices
- Removed invalid quantities
- Corrected inconsistent payment methods
- Standardized product categories

The cleaned datasets were stored inside:

```text
Data/cleaned/
```

---

# Data Validation

Several validation checks were performed after cleaning to ensure high data quality.

Validation checks included:

- Missing primary keys
- Duplicate primary keys
- Duplicate customer emails
- Missing customer IDs
- Missing product IDs
- Invalid order references
- Invalid product references
- Foreign key consistency
- Negative price count
- Negative quantity count
- Missing values count

Validation reports were generated inside:

```text
Data/reports/
```

---

# Database Integration

The cleaned datasets were loaded into a MySQL database using SQLAlchemy.

Database tables created:

- customers
- products
- orders
- order_items

The following relationships were maintained:

- customers → orders
- orders → order_items
- products → order_items

Primary and foreign key constraints were implemented to maintain data integrity.

---

# SQL Analysis

Business analysis was divided into three separate SQL files.

### Basic Queries

- Total Revenue
- Revenue by Category
- Revenue by Customer
- Top Selling Products
- Top Customers
- Orders by Status
- Monthly Orders
- Average Order Value

### Intermediate Queries

- Customer Purchase Frequency
- Revenue by City
- Products Never Ordered
- Customers Without Orders
- Most Popular Categories
- Highest Revenue Products
- Monthly Customer Growth
- Revenue by Payment Method

### Advanced Queries

- Common Table Expressions (CTEs)
- Window Functions
- ROW_NUMBER()
- RANK()
- DENSE_RANK()
- LAG()
- LEAD()
- FIRST_VALUE()
- LAST_VALUE()
- NTILE()
- Running Revenue
- Rolling Average
- Customer Lifetime Value
- Cohort Analysis
- Customer Retention Analysis
- Self Join
- Year-over-Year Revenue Comparison

---

# Business Insights Generated

The SQL analysis was used to generate several business insights.

Reports include:

- Total Revenue
- Total Orders
- Average Order Value
- Top Revenue Generating Categories
- Top Customers
- Best Selling Products
- Monthly Revenue Trend
- Revenue by City
- Customer Segmentation
- Customer Retention Metrics
- Repeat Customers
- Customer Lifetime Value
- Order Distribution by Status

---

# Python Reporting Tool

A command-line reporting application was developed using Python.

The reporting tool accepts:

- Report Type
- Start Date
- End Date

Generated reports include:

- Total Orders
- Total Revenue
- Average Order Value
- Unique Customers
- Top Products
- Revenue by Category
- Monthly Revenue
- Customer Segmentation
- Previous Period Comparison

Run the reporting tool using:

```bash
python scripts/reporting.py
```

---

# Edge Case Handling

Several critical edge cases were handled to improve the robustness of the system.

Implemented validations include:

- Missing CSV files
- Empty datasets
- Invalid customer IDs
- Invalid product IDs
- Duplicate IDs
- Duplicate emails
- Foreign key mismatches
- Negative prices
- Negative quantities
- Zero quantities
- Invalid payment methods
- Future order dates
- Invalid date formats
- SQL connection failures
- Invalid command-line input

These validations ensure that incorrect business data is identified before analysis.

---

# Screenshots

Project screenshots are available inside the **screenshots** folder.

The screenshots include:

- Synthetic Dataset Generation
- Dirty Dataset
- Data Cleaning Process
- Data Validation Reports
- MySQL Database Tables
- SQL Query Outputs

---

# How to Run the Project

### 1. Clone the repository

```bash
git clone <repository-url>
```

### 2. Install required packages

```bash
pip install -r requirements.txt
```

### 3. Create MySQL database

```sql
CREATE DATABASE ecommerce_order_analytics;
```

### 4. Create database tables

Execute:

```text
database/create_tables.sql
```

### 5. Generate synthetic datasets

```bash
python scripts/data_generation.py
```

### 6. Clean datasets

```bash
python scripts/data_cleaning.py
```

### 7. Validate datasets

```bash
python scripts/data_validation.py
```

### 8. Load cleaned data into MySQL

```bash
python database/load_data.py
```

### 9. Execute SQL analysis

Run the SQL files available inside:

```text
sql/
```

Execution order:

```text
basic_queries.sql

↓

intermediate_queries.sql

↓

advanced_queries.sql
```

### 10. Generate business reports

```bash
python scripts/reporting.py
```

---

# Conclusion

This project demonstrates a complete end-to-end data analytics workflow for an e-commerce order management system. Starting from synthetic data generation and intentional data quality issues, the project covers data cleaning, validation, relational database integration, advanced SQL analysis, and automated business reporting.

The assignment provides practical experience in handling real-world business data while strengthening skills in Python, Pandas, SQL, MySQL, and data analytics. The modular project structure and robust validation process ensure that the system is reliable, scalable, and easy to maintain.

---
