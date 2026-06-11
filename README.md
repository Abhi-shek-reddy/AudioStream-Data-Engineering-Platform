# AudioStream Data Engineering Platform

An end-to-end Azure Data Engineering solution built using Azure Data Factory, Azure Data Lake Storage Gen2, Azure Databricks, Azure Synapse Analytics, and Power BI. The project implements the Medallion Architecture (Bronze, Silver, Gold) to transform raw music streaming data into analytics-ready datasets for reporting and business intelligence.

---

# Project Overview

This project demonstrates a complete modern Data Engineering workflow including data ingestion, transformation, storage, modeling, and reporting using Microsoft Azure services.

The solution is designed to be scalable, dynamic, and production-ready while following industry best practices such as incremental loading, dimensional modeling, Delta Lake architecture, and cloud-native orchestration.

---
# Architecture

Source Music Streaming Data

↓

Azure Data Factory – Dynamic Data Ingestion Pipeline

↓

Bronze Layer (Azure Data Lake Storage Gen2)

Raw data stored without modifications

↓

Azure Databricks – PySpark Transformations

↓

Silver Layer (Azure Data Lake Storage Gen2)

Validated, cleaned, and transformed Delta tables

↓

Azure Synapse Analytics – SQL Views and External Tables

↓

Gold Layer (Azure Data Lake Storage Gen2)

Business-ready analytical datasets

↓

Power BI

Interactive Dashboards and Reports

---

# Technologies Used

| Technology                   | Purpose                           |
| ---------------------------- | --------------------------------- |
| Azure Data Factory           | Data ingestion and orchestration  |
| Azure Data Lake Storage Gen2 | Scalable cloud storage            |
| Azure Databricks             | Data transformation using PySpark |
| Apache Spark                 | Distributed data processing       |
| Delta Lake                   | Reliable ACID-compliant storage   |
| Azure Synapse Analytics      | SQL-based analytics and reporting |
| Power BI                     | Business intelligence dashboards  |
| Git & GitHub                 | Version control and collaboration |

---

# Dataset

The platform processes music streaming data containing:

### User Data

* User profiles
* Subscription plans
* Geographic information

### Artist Data

* Artist information
* Genres
* Regional classifications

### Track Data

* Song metadata
* Album information
* Release details

### Streaming Activity

* Listening events
* Stream duration
* User engagement metrics

### Date Dimension

* Calendar attributes
* Time-based analytics

---

# Data Pipeline

## Bronze Layer – Data Ingestion

Built a dynamic Azure Data Factory pipeline using:

* Lookup Activity
* ForEach Activity
* Copy Activity

Features:

* Parameterized datasets
* Metadata-driven ingestion
* Dynamic source configuration
* Automated file handling

Raw data is stored in the Bronze layer without transformations to preserve source integrity.

---

## Silver Layer – Data Transformation

Implemented using Azure Databricks and PySpark.

Transformations include:

* Schema validation
* Data type standardization
* Null value handling
* Duplicate removal
* Data cleansing
* Incremental processing
* Business rule implementation

Additional enhancements:

* Derived business attributes
* User subscription categorization
* Streaming duration calculations
* Data quality validations

Transformed datasets are stored as Delta Lake tables in the Silver layer.

---

## Gold Layer – Business Analytics

Implemented using Azure Synapse Analytics.

Key activities:

* Creation of analytical views
* Dimensional data modeling
* Fact and Dimension tables
* Aggregated business metrics
* External table generation

The Gold layer serves as the primary reporting source for business intelligence applications.

---

# Data Model

## Dimension Tables

### DimUser

Stores user profile and subscription information.

### DimArtist

Stores artist metadata and genre details.

### DimTrack

Stores track and album information.

### DimDate

Provides date hierarchy for time-based analysis.

---

## Fact Tables

### FactStream

Captures:

* User listening activity
* Track consumption
* Streaming duration
* Engagement metrics

---

# Project Structure

AudioStream-Data-Engineering-Platform/

│

├── README.md

│

├── config/

│ ├── source_config.json

│

├── pipelines/

│ ├── Bronze_Ingestion.json

│ ├── Dynamic_Ingestion.json

│

├── notebooks/

│ ├── silver_layer_transformation.ipynb

│ ├── gold_layer_processing.ipynb

│

├── sql_scripts/

│ ├── 01_schema_setup.sql

│ ├── 02_views.sql

│ ├── 03_external_tables.sql

│

├── source_scripts/

│ ├── spotify_initial_load.sql

│ ├── spotify_incremental_load.sql

---

# Key Concepts Demonstrated

* Medallion Architecture (Bronze, Silver, Gold)
* Dynamic Pipeline Design
* Incremental Data Loading
* Data Warehouse Modeling
* Fact and Dimension Design
* Delta Lake Architecture
* Data Quality Validation
* Azure Cloud Data Engineering
* PySpark Data Processing
* Serverless Analytics
* Business Intelligence Reporting

---

# Pipeline Design

The ingestion framework follows a metadata-driven architecture.

Process:

1. Source metadata stored in configuration files.
2. Azure Data Factory reads metadata dynamically.
3. ForEach loops process incoming datasets.
4. Parameterized pipelines handle ingestion.
5. Data is stored in Bronze storage.
6. Databricks transforms data into Silver Delta tables.
7. Synapse builds Gold analytical datasets.

This architecture allows new datasets to be onboarded with minimal pipeline changes.

---

# Business Insights Enabled

The platform supports analysis such as:

* Top streamed tracks
* Most popular artists
* Premium vs Free user behavior
* Regional listening trends
* Subscription growth analytics
* User engagement metrics
* Listening duration trends

---

# Results

The platform successfully:

* Automated ingestion of music streaming datasets
* Processed large datasets using PySpark
* Implemented scalable Delta Lake architecture
* Built analytical data models for reporting
* Delivered business-ready datasets through Azure Synapse
* Enabled dashboard reporting in Power BI

---

# Future Enhancements

* Real-time streaming using Azure Event Hubs
* Kafka integration
* Delta Live Tables
* CI/CD using Azure DevOps
* Data Quality Monitoring
* Machine Learning Recommendation Engine
* Streaming Analytics Dashboards

---

# Author

Abhishek Reddy

Data Engineer | Azure Databricks | PySpark | SQL | Delta Lake | Azure Data Factory
