# E-Commerce Data Engineering Pipeline

## Overview

This project implements an end-to-end data engineering pipeline for processing e-commerce datasets using Azure Data Factory, Azure Data Lake Storage Gen2, Azure Databricks, PySpark, Delta Lake, and Unity Catalog.

The pipeline ingests CSV files into ADLS Gen2 and processes them through Landing, Bronze, Silver, and Gold layers using the Medallion Architecture.

## Architecture

Source CSV Files  
→ Azure Data Factory Copy Activity  
→ ADLS Gen2 Landing Container  
→ Azure Databricks Notebook  
→ Landing Layer  
→ Bronze Layer  
→ Silver Layer  
→ Gold Layer  
→ Reconciliation and KPI Outputs

## Technologies Used

- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure Databricks
- Apache Spark (PySpark)
- Delta Lake
- Unity Catalog
- Python

## Data Sources

The pipeline processes four e-commerce datasets:

- `customers.csv`
- `inventory.csv`
- `orders.csv`
- `order_items.csv`

## Pipeline Layers

### Landing Layer

Reads CSV files from ADLS Gen2, preserves source data as strings, and adds ingestion metadata.

### Bronze Layer

Stores raw data in Delta format with ingestion timestamps and load-date metadata.

### Silver Layer

Performs type casting, deduplication, data-quality validation, quarantine handling, and customer updates using Delta MERGE.

### Gold Layer

Creates business aggregates:

- Daily Revenue
- Fulfillment KPIs
- Inventory Health
- Customer Lifetime Value

## Data Quality and Reconciliation

Invalid order and order-item records are stored in quarantine tables.

Reconciliation tables track row counts, pass rates, and quarantine rates across pipeline layers.

## Automation

Azure Data Factory copies source CSV files into the ADLS Gen2 landing container.

The Databricks notebook is scheduled to run every 6 hours and processes the latest landing data through all Medallion Architecture layers.

## Repository Structure

- `adf/` - Azure Data Factory ARM templates
- `databricks_notebooks/` - Databricks pipeline notebook
- `datasets/` - Input CSV datasets
- `screenshots/` - Project execution screenshots

## Project Status

The ADF ingestion pipeline, Databricks transformations, Delta tables, data-quality checks, Gold KPIs, reconciliation, and scheduled notebook execution have been successfully implemented and tested.