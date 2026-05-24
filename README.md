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
