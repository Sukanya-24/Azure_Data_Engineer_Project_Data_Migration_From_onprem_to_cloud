# End-to-End Azure Data Engineering Project

This project demonstrates a complete data engineering pipeline from an on-premises SSMS to Azure Synapse Analytics, following the Bronze-Silver-Gold data lake architecture. It includes data migration, transformation, data governance, and final analytics-ready data in Azure Synapse.
In this project, I used the following Azure services to implement a secure and robust ETL pipeline:

- **Onprem SQL Server Management Studio**
- **Azure Data Factory**
- **Azure Data Lake Gen2**
- **Azure Key Vault**
- **Databricks (with Spark)**
- **Azure Synapse Analytics**
- **Power-BI**
- **Programming Languages (SQL,Python,Pyspark)**

![image](https://github.com/user-attachments/assets/d8b5b0ca-d29f-4d77-bb16-410f29925839)

![image](https://github.com/user-attachments/assets/e17eba6d-e0e4-410e-b671-f5829fa61b2d)

## Project Overview
In this project, I utilized the following Azure services to build a secure and efficient ETL pipeline:

- **Azure Data Factory (ADF)**: Migrates data from an on-premises SSMS to Azure.
- **Azure Key Vault**: Ensures secure storage of sensitive information like passwords.
- **Azure Databricks**: Transforms data between the Bronze, Silver, and Gold layers.
- **Azure Synapse Analytics**: Provides an analytics-ready data model with automatically updating views.
- **Azure Data Lake Gen2**: Serves as the data storage platform, organized in Bronze, Silver, and Gold layers.
- **Power BI (Optional)**: For visualizing and analyzing the data.

## Architecture
This pipeline follows the Bronze-Silver-Gold data lake model:
1. **Bronze Layer**: Raw data ingestion from the on-prem SSMS using Azure Data Factory.
2. **Silver Layer**: Data cleansing and formatting (e.g., converting datetime to date format).
3. **Gold Layer**: Final data transformation with column renaming, creating analytics-ready tables.
4. **Azure Synapse Analytics**: Creation of views for each table in the gold layer.
5.  **Power-BI**: for building reports

## Project Steps

### 1. Data Migration with Azure Data Factory
- **Source**: On-premises SSMS
- **Target**: Azure Data Lake (Bronze Layer) in parquet form
- **Security**: Passwords and sensitive connection details are securely stored in **Azure Key Vault** for data governance.
- The data was migrated in raw format (parquet form) for initial storage and further transformation.

### 2. Transformation in Databricks (Silver Layer)
- Transformed datetime columns (e.g., `startdate`, `shipdate`) to a simpler date format.
- Moved the cleaned data to the Silver Layer (Delta format) in Azure Data Lake.

### 3. Additional Transformations in Databricks (Gold Layer)
- Renamed columns (e.g., `ColumnNames` to `Column_Names` for consistency).
- Stored transformed data in the Gold Layer (delta Format).

### 4. Data Presentation in Azure Synapse Analytics
- Created a **Synapse Database**.
- Built **views** for each table in the Gold Layer, enabling real-time updates based on changes in the gold tables.

## Technologies Used
- **Azure Data Factory** for data migration
- **Azure Key Vault** for secure password storage and data governance
- **Azure Databricks** (Spark) for data transformation
- **Azure Data Lake Storage** for data lake layers
- **Azure Synapse Analytics** for final data presentation
- **Power-BI** for building reports

## Programming/Scripting language Used
- **Python**
- **SQL**
- **Pyspark**
