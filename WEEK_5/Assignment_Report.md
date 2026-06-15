# Week 5 Assignment: Big Data Fundamentals & PySpark Data Pipelines

A concise overview of the core concepts learned and data engineering tasks implemented using Apache Spark during Week 5.

---

##  What I Learnt: Spark Core Concepts

* **In-Memory Processing vs. MapReduce:** Learned how Apache Spark optimizes big data processing by keeping intermediate data directly in **RAM**. This avoids the massive disk I/O bottlenecks of traditional Hadoop MapReduce, making iterative workflows (like machine learning) significantly faster.
* **Immutability:** Understood that Spark DataFrames cannot be modified in place. Operations like dropping or renaming columns always return a *new* DataFrame reference, which preserves data lineage and makes the cluster fault-tolerant.
* **The Shuffle Process:** Gained a solid grasp of how wide transformations (like `groupBy` or `join`) trigger a network shuffle, redistributing data across cluster nodes to collocate identical keys.

---

##  What I Did: Data Engineering in PySpark

To put these theoretical concepts into practice, I built an end-to-end data cleaning and aggregation pipeline within the [`Week_5.ipynb`](./Week_5.ipynb) notebook using **PySpark**. 

### 1. Data Cleansing & Quality Control
* **Deduplication:** Dropped redundant records using targeted composite keys (`user_id` and `transaction_date`).
* **Handling Nulls & Empties:** Used `.na.fill()` to handle missing numeric values and filtered out corrupt rows (such as missing emails or empty username strings) to safeguard downstream math.

### 2. Schema Evolution
* **Type Casting:** Explicitly cast raw text dates into rigid `TimestampType` profiles and renamed columns using `.withColumnRenamed()` to ensure schema consistency.

### 3. Statistical Aggregations
* **Multi-Metric Analytics:** Used the `.agg()` function to extract multiple metrics ($\min$, $\max$, and $\text{average}$ sales) simultaneously.
* **Pipeline Building:** Chained filtering, filling, and grouping sequentially to calculate total scaled revenue split by `store_id`.

---

##  Key Takeaway

By building a complete, production-ready data pipeline, I learned firsthand how to handle real-world data issues, mitigate the risks of lazy schema inference, and ensure raw data is completely reliable before it hits production environments.
