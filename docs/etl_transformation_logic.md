# ETL Transformation Logic

## Overview

The ETL workflow follows a Medallion Architecture pattern designed to progressively refine cryptocurrency market data from raw ingestion to business-ready analytical datasets.

The transformation pipeline is implemented using Azure Data Factory and Azure Databricks with PySpark.

---

# Bronze Layer

## Purpose
The Bronze layer stores raw cryptocurrency market data exactly as received from the external API source.

---

## Data Characteristics

The Bronze layer includes:
- Raw JSON payloads
- Unmodified API responses
- Historical ingestion records
- Source-of-truth datasets

---

## Ingestion Process

The ingestion workflow:
1. Calls the CoinGecko REST API
2. Retrieves cryptocurrency market data
3. Writes raw data into Azure Data Lake Storage

---

# Silver Layer

## Purpose
The Silver layer transforms raw data into a clean and standardized analytical dataset.

---

## Transformations Performed

### Data Cleaning
- Null handling
- Data type standardization
- Invalid record filtering

---

### Schema Standardization
Standardized:
- Pricing fields
- Market capitalization metrics
- Supply metrics
- Percentage change columns

---

### Derived Columns

Additional business columns were created including:

#### market_status
Classifies coins as:
- Bullish
- Bearish
- Strong Bullish
- Strong Bearish

Based on:
- 24-hour price change percentage

---

### Metadata Columns
Additional metadata fields include:
- ingestion_time
- processing timestamps

---

# Gold Layer

## Purpose
The Gold layer generates business-facing analytical KPIs and aggregated metrics.

---

## KPI Aggregations

The Gold layer includes:
- Total coins by market status
- Average coin price
- Average market movement
- Market distribution insights

---

## Analytical Objectives

The Gold layer is optimized for:
- Executive reporting
- Dashboard consumption
- Trend analysis
- Business intelligence

---

## Transformation Technologies

The transformation workflow uses:
- PySpark
- Spark SQL
- Azure Databricks
- Azure Data Factory orchestration

---

## ETL Design Principles

The transformation architecture emphasizes:

- Layered data refinement
- Scalable distributed processing
- Business-oriented KPI generation
- Reusable analytical datasets
