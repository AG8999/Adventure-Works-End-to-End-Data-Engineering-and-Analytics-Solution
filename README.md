# Adventure-Works-End-to-End-Data-Engineering-and-Analytics-Solution

## Table of Contents
- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Results](#results)

## Project Overview
This project builds a comprehensive End-to-End Azure Data Engineering Solution that integrates Data Ingestion, ETL (Extract, Transform, Load), and Analytics into a unified workflow.

## Project Workflow
### Data Ingestion
-Raw Data Loading:
The raw transactional data was ingested into Azure SQL Database, which serves as the primary source for this data engineering pipeline.

-Data Copy to ADLS Gen2:
Using Azure Data Factory, the raw data from Azure SQL Database was dynamically extracted and copied into the Bronze container of Azure Data Lake Storage Gen2 (ADLS Gen2). This setup ensures that raw data is securely stored in a scalable and organized manner for downstream processing.
