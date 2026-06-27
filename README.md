# Celebal Technologies Data Engineering Internship

## About This Repository
This repository documents my learning journey during the **Celebal Technologies Data Engineering Internship**, with weekly assignments and hands-on projects covering core data engineering concepts.

**Skills covered:**
- Python
- Pandas
- SQL
- Data Cleaning & Exploration
- ETL / ELT Concepts
- Azure Data Factory
- Apache Spark
- Databricks
- Data Pipeline Design

---

# Week 1 — Data Exploration & Cleaning with Pandas

**Dataset:** Combined shopping product dataset

**Tasks completed:**
- Loaded and explored dataset using `head()`, `tail()`, `shape`, `columns`, `dtypes`
- Handled missing values and duplicates
- Filtered and selected relevant data
- Created derived columns (`quantity`, `total_amount`)
- Exported cleaned dataset

---

# Week 2 — SQL E-Commerce Database Assignment

Designed and queried a relational e-commerce database using **MySQL**.

### Section A — SQL Basics
**Concepts:** SELECT, DISTINCT, Primary Keys, UNIQUE, NOT NULL, CHECK constraints

- **Q4:** Primary keys uniquely identify records (`customer_id`, `product_id`, `order_id`, `item_id`)
- **Q5:** Duplicate emails are prevented using `UNIQUE + NOT NULL`
- **Q6:** Negative prices are blocked using `CHECK (unit_price > 0)`

### Section B — Filtering & Optimization
**Concepts:** WHERE, BETWEEN, conditional filtering, indexing, query optimization

Worked with filtered queries and efficient index-aware query design.

### Section C — Aggregation
**Concepts:** COUNT, SUM, AVG, MIN, MAX, GROUP BY, HAVING, ORDER BY

Performed business analysis using aggregated SQL queries.

### Section D — Joins & Relationships
**Concepts:** INNER JOIN, LEFT/RIGHT JOIN, multi-table joins, Foreign Keys

- **Q22:** LEFT JOIN keeps all left-table rows; RIGHT JOIN keeps all right-table rows
- **Q23:** Foreign key relationships:
  - `orders.customer_id → customers.customer_id`
  - `order_items.order_id → orders.order_id`
  - `order_items.product_id → products.product_id`

### Section E — Advanced SQL
**Concepts:** CASE, conditional aggregation, transactions, COMMIT/ROLLBACK, ACID

**ACID Properties:**
- **Atomicity:** all-or-nothing execution
- **Consistency:** valid database state maintained
- **Isolation:** concurrent transactions remain independent
- **Durability:** committed data persists


# Week 3 Assignment: SQL Analysis Using Subqueries, CTEs, and Window Functions

## Objective

Analyze the Superstore dataset using SQL and apply Subqueries, CTEs, and Window Functions to solve business problems.

## Tasks Performed

* Imported the Superstore dataset into MySQL.
* Created `customers`, `products`, and `orders` tables.
* Inserted data from `superstore_raw`.
* Used Subqueries for filtering and analysis.
* Applied CTEs for sales aggregation.
* Used Window Functions (`RANK()`, `ROW_NUMBER()`).
* Performed customer sales analysis and ranking.
* Completed the Customer Sales Insights mini project.

## Files Included

* `WEEK_3_SQL_FILE.sql`
* `Sample - Superstore.csv`
* `Outputs_Of_SQL_Queries/`

## What I Learned

* Importing and managing datasets in MySQL.
* Creating and populating normalized tables.
* Using Subqueries to analyze data.
* Working with CTEs for cleaner queries.
* Applying Window Functions for ranking and ordering.
* Solving real-world business questions using SQL.

## Conclusion

This assignment helped me strengthen my understanding of advanced SQL concepts and their practical application in data analysis.



# Week 4 - Azure Data Pipeline using ADF

## Objective

Build an end-to-end data pipeline using Azure Storage Account and Azure Data Factory (ADF).

## Work Completed

* Created a Resource Group in Azure.
* Created a Storage Account and Blob Container.
* Uploaded the Superstore CSV dataset.
* Created Azure Data Factory.
* Configured Linked Service and Datasets.
* Implemented Get Metadata activity.
* Built a pipeline using Copy Data activity.
* Executed and monitored the pipeline successfully.
* Assigned IAM roles (Reader and Contributor).

## Pipeline Flow

Blob Storage → Azure Data Factory → Destination Storage

## Technologies Used

* Azure Resource Group
* Azure Storage Account
* Azure Blob Storage
* Azure Data Factory (ADF)

## Outcome

Successfully created and executed a data pipeline that validates metadata and copies data from source to destination using Azure Data Factory.


# Week 5 - Spark Data Processing

## Objective
Learn Spark DataFrames and perform data cleaning, filtering, transformations, and aggregations.

## Tasks Performed
- Removed duplicate records
- Handled null values
- Applied filtering conditions
- Performed aggregations using count, sum, avg, min, and max
- Used groupBy operations
- Modified schema using casting and renaming
- Cleaned inconsistent data
- Built a complete data processing pipeline

## Technologies Used
- PySpark
- Apache Spark
- Python
- Jupyter Notebook
  

# Week 6 - Spark Architecture and Data Processing

## Objective

Understand Spark architecture and perform data processing using PySpark DataFrames.

## Work Completed

- Studied Driver, Cluster Manager, and Executor roles in Spark.
- Learned Lazy Evaluation and DAG execution.
- Performed DataFrame operations such as filtering, selection, renaming, and type casting.
- Handled null values and created derived columns.
- Explored wide transformations, shuffle operations, and Predicate Pushdown.
- Compared CSV and Parquet file formats.
- Built simple data processing workflows using Spark DataFrames.


# Week 7 - Data Cleaning using PySpark and Delta Lake

## Objective

Perform data exploration, cleaning, transformation, and data storage using PySpark in Databricks.

## Work Completed

- Loaded the Sample Superstore dataset into a PySpark DataFrame.
- Explored the dataset by checking the first and last 5 rows, schema, row count, column names, and data types.
- Identified and handled missing values.
- Removed duplicate records.
- Filtered data and selected relevant columns.
- Created derived columns (`Unit Price` and `total_amount`).
- Saved the cleaned dataset as a CSV file.
- Stored the cleaned dataset in Delta format.

## Technologies Used

- Python
- PySpark
- Databricks
- Delta Lake
