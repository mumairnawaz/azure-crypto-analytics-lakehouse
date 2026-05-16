# Pipeline Automation Strategy

## Overview

The Azure Crypto Analytics Platform is fully automated using Azure Data Factory scheduling and orchestration capabilities.

The automation strategy ensures that cryptocurrency market data is continuously ingested, processed, transformed, and stored without manual intervention.

---

## Automation Objectives

The automation workflow was designed to:

- Eliminate manual execution
- Enable recurring data ingestion
- Automate transformation workflows
- Maintain historical analytical datasets
- Simulate production-grade ETL orchestration

---

## Pipeline Workflow

The pipeline consists of the following sequential activities:

### 1. copy_crypto_api
Retrieves cryptocurrency market data from the CoinGecko REST API.

Output:
- Bronze layer raw data

---

### 2. copy_bronze_to_silver
Moves raw data into the Silver layer for transformation and cleaning.

---

### 3. copy_silver_to_gold
Processes cleaned datasets into analytical Gold layer outputs.

---

### 4. crypto_etl_notebook
Triggers Azure Databricks notebook execution for PySpark transformations and KPI generation.

---

## Trigger Strategy

The platform uses scheduled triggers in Azure Data Factory.

### Current Configuration
- Frequency: Every 6 Hours
- Trigger Type: Schedule Trigger
- Execution Mode: Automated

---

## Automation Benefits

The scheduling strategy enables:

- Continuous market monitoring
- Automated historical dataset accumulation
- Near real-time analytical refresh
- Reduced operational overhead

---

## Monitoring & Execution

Pipeline execution is monitored using:

- Azure Data Factory Monitor
- Activity execution logs
- Databricks execution status
- Pipeline success/failure tracking

---

## Production-Oriented Design

The automation workflow follows enterprise ETL orchestration principles:

- Sequential activity dependency management
- Isolated transformation stages
- Distributed notebook execution
- Cloud-native orchestration

---

## Future Enhancements

Potential future improvements include:

- Retry policies
- Failure alerting
- Incremental ingestion
- Event-driven triggers
- Azure Monitor integration
- CI/CD automation
