# E-Commerce Data Pipeline

## Objective

The objective of this project is to build an end-to-end e-commerce data engineering pipeline for ingesting, processing, validating, and transforming raw CSV data into analytics-ready business metrics.

The project demonstrates data ingestion using Azure Data Factory, cloud storage using ADLS Gen2, Medallion Architecture implementation using Azure Databricks and PySpark, Delta Lake processing, Unity Catalog integration, data-quality validation, reconciliation, and scheduled notebook execution.

## Architecture

```text
Source CSV Files
        │
        ▼
Azure Data Factory
(Copy Activity)
        │
        ▼
ADLS Gen2 Landing Container
        │
        ▼
Azure Databricks Notebook
        │
        ▼
Landing Layer
        │
        ▼
Bronze Layer
        │
        ▼
Silver Layer
        │
        ▼
Gold Layer
        │
        ▼
Business KPIs and Reconciliation Tables
```

The Databricks notebook is scheduled to execute every 6 hours. Unity Catalog is used to organize and manage the tables created across the different processing layers.

## Working

Azure Data Factory uses a Copy Activity to ingest the four source CSV files into the ADLS Gen2 landing container.

The Databricks notebook reads the CSV files from ADLS Gen2 and processes them through the Medallion Architecture.

The Landing layer preserves the ingested source data and adds ingestion metadata.

The Bronze layer stores the data as Delta tables with additional ingestion and load metadata.

The Silver layer performs schema enforcement, type casting, deduplication, data-quality validation, quarantine handling, and customer updates using Delta MERGE.

The Gold layer generates analytics-ready business KPIs including Daily Revenue, Fulfillment KPIs, Inventory Health, and Customer Lifetime Value.

Reconciliation tables track row counts, data-quality pass rates, and quarantine rates to verify pipeline execution and data consistency.

The Databricks notebook is scheduled to execute every 6 hours using Databricks scheduling.

## Data Sources

- `customers.csv`
- `inventory.csv`
- `order_items.csv`
- `orders.csv`

## File Structure

```text
Celebal_E-Commerce_Data_Pipeline/
│
├── adf/
│   ├── arm_template/
│   │   ├── factory/
│   │   ├── linkedTemplates/
│   │   ├── ARMTemplateForFactory.json
│   │   └── ARMTemplateParametersForFactory.json
│   │
│   └── arm_template.zip
│
├── Databricks_Notebooks/
│   └── ecommerce_data_pipeline.ipynb
│
├── datasets/
│   ├── customers.csv
│   ├── inventory.csv
│   ├── order_items.csv
│   └── orders.csv
│
├── Documentation/
│   └── Summary.md
│
├── Screenshots_Of_Pipeline/
│   ├── Copy_CSV_To_Landing.png
│   ├── Landing_Container_with_copied_CSV's.png
│   ├── Schedule_added_for_every_6_hours.png
│   ├── Successful_pipeline_execution.png
│   └── Tables_in_catalog_Explorer.png
│
├── .gitignore
└── README.md
```

## Key Features

- Automated CSV ingestion using Azure Data Factory
- ADLS Gen2 integration
- Medallion Architecture implementation
- PySpark-based data transformations
- Delta Lake tables
- Unity Catalog integration
- Data deduplication and validation
- Quarantine tables for invalid records
- Delta MERGE for customer updates
- Gold-layer business KPIs
- Row-count and data-quality reconciliation
- Scheduled notebook execution
- ARM template export for Azure Data Factory resources
- Pipeline execution screenshots for project verification

## Improvements

- Integrate Azure Data Factory directly with the Databricks notebook for dependency-based orchestration.
- Add incremental ingestion using file-processing checkpoints.
- Implement centralized monitoring and pipeline failure alerts.
- Add automated testing for data-quality rules and transformations.
- Integrate the Gold layer with a BI tool for dashboards and reporting.

## Conclusion

The project successfully implements a structured e-commerce data engineering pipeline using Azure Data Factory, ADLS Gen2, Azure Databricks, PySpark, Delta Lake, and Unity Catalog.

It processes raw CSV data through multiple data layers, applies data-quality checks, handles invalid records using quarantine tables, generates business metrics, and provides reconciliation outputs for pipeline verification.

The repository also includes the Databricks notebook, source datasets, Azure Data Factory ARM template, project documentation, and execution screenshots required to understand, verify, and reproduce the implemented pipeline.
