# Adventure-Works-End-to-End-Data-Engineering-and-Analytics-Solution

## Table of Contents
- [Project Overview](#project-overview)
- [Project Workflow](#Project-Workflow)
  -[Data Ingestion](#Data-Ingestion)
  -[Data Storage](#Data-Storage)
  -[Orchestration with Azure Data Factory (ADF)](#ADF)
    - [Linked Services](#Linked-Services)
    - [Datasets](#Datasets)
    - [Activities](#Activities)
    - [Pipeline Design](#Pipeline-Design)
- [Data Transformation](#Data-Transformation)
- [Business Intelligence with Power BI](#Power-BI)

## Project Overview
This project builds a comprehensive End-to-End Azure Data Engineering Solution that integrates Data Ingestion, ETL (Extract, Transform, Load), and Analytics into a unified workflow.

## Project Workflow
### Data Ingestion
- Raw Data Loading:
The raw transactional data was ingested into Azure SQL Database, which serves as the primary source for this data engineering pipeline.

- Data Copy to ADLS Gen2:
Using Azure Data Factory, the raw data from Azure SQL Database was dynamically extracted and copied into the Bronze container of Azure Data Lake Storage Gen2 (ADLS Gen2). This setup ensures that raw data is securely stored in a scalable and organized manner for downstream processing.

## Data Storage

- Organized data using Azure Data Lake Storage Gen2 with tiered storage containers: Bronze, and Silver.

## Orchestration with Azure Data Factory (ADF)

Azure Data Factory (ADF) was used to build a robust and automated data pipeline that seamlessly integrates data sources and destinations. The pipeline was designed with the following key components:

### 1. Linked Services
Linked Services act as connection points to external resources in Azure Data Factory. For this project, the following linked services were created:

- Azure SQL Database: Configured to connect to the database hosting the raw data. The connection included parameters such as serverName and databaseName to enable flexibility and reusability across different environments.
- ADLS Gen2 Storage: Configured to connect to the Azure Data Lake Storage Gen2 for storing data in the Bronze, Silver, and Gold containers.

### 2. Datasets
Datasets define the structure of the data within the linked services and are used in activities for reading or writing data.

- Source Dataset: Defined for Azure SQL Database, representing the tables from which data is to be extracted.
- Sink Dataset: Defined for ADLS Gen2 Storage, specifying the target path in the Bronze container where raw data is stored after ingestion.

### 3. Activities
Activities are the building blocks of ADF pipelines and perform actions like data movement or transformation. Key activities used in this project include:

- Copy Activity:
1) Extracted raw data from the Azure SQL Database source dataset.
2) Loaded the data into the ADLS Gen2 Storage Bronze container.

### 4. Pipeline Design
The pipeline was parameterized for:

- Server Name and Database Name: Applied at the linked service, dataset, and pipeline levels to make it a generic and reusable solution.
- Table Names and Schema: Dynamically retrieved and passed as inputs to ensure flexibility and scalability when working with multiple tables.

![ADF Pipeline](Images/Generic Azure Data Factory Pipeline.png)


## Data Transformation

- Cleaned and transformed data using Databricks Notebooks.

## Business Intelligence with Power BI

- Developed interactive dashboards in Power BI Desktop, connecting to the Silver container in ADLS Gen2 using SAS tokens.
- Delivered actionable insights via dynamic visualizations like KPIs, tables, and charts.

