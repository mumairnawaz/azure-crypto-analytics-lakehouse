# Architecture Explanation

## Overview

The Azure Crypto Analytics Platform is an enterprise-style cloud-native data engineering solution designed to automate cryptocurrency market data ingestion, transformation, storage, and orchestration using Microsoft Azure services.

The platform follows a Medallion Architecture approach consisting of Bronze, Silver, and Gold layers to support scalable and structured data processing workflows.

---

## Core Architecture Components

### 1. CoinGecko REST API
The system retrieves cryptocurrency market data from the CoinGecko API.

The API provides:
- Coin pricing
- Market capitalization
- Trading volume
- ATH/ATL metrics
- Market ranking information

---

### 2. Azure Data Factory (ADF)

Azure Data Factory orchestrates the complete ETL workflow.

Responsibilities include:
- API ingestion
- Activity orchestration
- Bronze → Silver → Gold execution flow
- Databricks notebook triggering
- Automated scheduling

---

### 3. Azure Data Lake Storage Gen2 (ADLS)

ADLS serves as the centralized storage layer.

The solution follows a Medallion Architecture:

#### Bronze Layer
Stores raw ingested cryptocurrency data.

#### Silver Layer
Stores cleaned and standardized analytical datasets.

#### Gold Layer
Stores business-ready KPIs and aggregated market insights.

---

### 4. Azure Databricks

Azure Databricks performs distributed data transformation using PySpark.

Responsibilities include:
- Data cleaning
- Schema standardization
- KPI generation
- Market classification
- Aggregation logic

---

## Medallion Architecture

### Bronze Layer
Raw source ingestion layer.

Characteristics:
- Immutable raw data
- Historical ingestion support
- API response preservation

---

### Silver Layer
Data cleansing and standardization layer.

Transformations include:
- Data type corrections
- Null handling
- Standardized schema
- Derived business columns

---

### Gold Layer
Business-facing analytical layer.

Includes:
- Market status KPIs
- Aggregated statistics
- Analytical datasets
- Dashboard-ready outputs

---

## Automation Workflow

The entire platform is automated through Azure Data Factory triggers.

Workflow:
1. API Ingestion
2. Bronze Storage
3. Silver Transformation
4. Gold Aggregation
5. Databricks Notebook Execution
6. Scheduled Automation

---

## Technology Stack

- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure Databricks
- PySpark
- Python
- REST APIs
- GitHub

---

## Architecture Objective

The platform demonstrates:
- Cloud-native ETL design
- Enterprise orchestration patterns
- Distributed data processing
- Automated pipeline execution
- Scalable analytical architecture
