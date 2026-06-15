# Week 1 - Basic Data Exploration and Cleaning using Pandas

## Objective

Learn Python basics and perform basic data exploration and cleaning using Pandas.

## Dataset Used

Combined Shopping Product Dataset

## Tasks Performed

### 1. Data Loading

* Loaded the CSV dataset into a Pandas DataFrame using `read_csv()`.

### 2. Data Exploration

Explored the dataset using:

* `head()`
* `tail()`
* `shape`
* `columns`
* `dtypes`
* `info()`
* `describe()`

### 3. Missing Value Handling

* Identified missing values using `isnull().sum()`.
* Filled missing values in the `discount` column with `0`.

### 4. Data Filtering and Selection

* Selected relevant columns from the dataset.
* Filtered records based on specified conditions.

### 5. Duplicate Detection

* Checked for duplicate records using `duplicated().sum()`.
* No duplicate records were found in the dataset.

### 6. Feature Engineering

Created new columns:

* `quantity`
* `total_amount`

`total_amount = final_price × quantity`

### 7. Exporting Cleaned Data

* Saved the cleaned dataset as `cleaned_combined_dataset.csv`.

---

## Skills Learned

* Python Basics
* Pandas DataFrames
* Data Exploration
* Missing Value Handling
* Data Filtering
* Column Selection
* Duplicate Detection
* Feature Engineering
* CSV File Operations

---

## Files Included

```text
Week1.ipynb
Combined_dataset.csv
cleaned_combined_dataset.csv
README.md
```
