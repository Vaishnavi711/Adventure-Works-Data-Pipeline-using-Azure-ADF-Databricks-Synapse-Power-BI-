## Overview 📝

#### This project demonstrates a real-world, end-to-end data engineering pipeline built on Microsoft Azure, using the Adventure Works dataset. It showcases how to ingest, process, store, and visualize data using modern, enterprise-grade cloud tools.

## Step-1 Azure Data Factory (ADF) 🔄🏭

- **Data Ingestion**: Pulled data from **GitHub (via HTTP)** into **Azure Data Lake (ADLS)**.\
- **Created Static & Dynamic Pipelines 🔄**:
  - **Static Pipelines**: Processed fixed datasets (e.g., daily Products data 📊).
  - **Dynamic Pipelines**: Parameterized to handle **multiple files/folders**, ensuring **scalability & reusability**.
- **Used Activities**:
  - **Copy Activity 📥**: Loaded JSON files from **GitHub** into **ADLS**.
  - **Lookup Activity 🔍**: Retrieved configuration & metadata for dynamic processing.
  - **ForEach Activity 🔁**: Iterated over multiple JSON files to apply transformations dynamically.
- **Data Transformation**: Leveraged **Mapping Data Flows** to clean, join, and standardize data.
- - **Orchestration ⚙️**: Managed end-to-end data workflows by controlling pipeline execution order, dependencies, and monitoring pipeline runs.
- **Integration**: Connected seamlessly with **Azure Databricks (processing)** and **Azure Synapse (analytics)**.


## Step-2 Azure Databricks (Transformation) ⚡
- **Connected ADLS to Databricks 🔐** using **Azure AD App Registration (Service Principal)** with secure OAuth-based access.
- **Purpose**: Processed raw **Bronze layer** data into curated **Silver layer** for analytics.
- **Data Cleaning & Transformation 🧹**: 
  - Removed duplicates, handled missing values, and standardized data formats.
  - Applied business rules and transformations using **PySpark**.
- **Schema Enforcement 📐**: Ensured consistent structure across datasets.
- **Integration 🔗**: Read input from **ADLS (Bronze)** and wrote transformed outputs back to **ADLS (Silver)**.
- **Reusability & Scalability 🚀**: Built modular notebooks and parameterized jobs for dynamic data processing.

## Step-3 Azure Synapse Analytics (Gold Layer) 📊


- **Purpose**: Served as the **analytics & reporting layer (Gold)** for business-ready data.
- **Data Consumption**: Queried curated **Silver data from ADLS** using **serverless SQL pools**.
- **Data Modeling 📐**: Created **views** for KPIs and business insights and created External table from existing table and served in **golden layer**
- **Integration 🔗**: Provided created external datasets to **Power BI** for visualization and reporting.

## Step-4 Power BI (Visualization Layer) 📈



- **Purpose**: Delivered **interactive dashboards & reports** for business stakeholders.  
- **Data Source 🔗**: Connected directly to **Azure Synapse (Gold Layer)** for real-time analytics.  
- **Visualizations 📊**: Built KPIs, trend analysis, and sales performance dashboards.  
  






