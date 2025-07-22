# celebal_project

# Azure Data Factory Pipeline: CSV to Azure SQL Database

This project demonstrates how to use **Azure Data Factory (ADF)** to move and transform **unstructured CSV data stored in Azure Blob Storage** into **structured data stored in Azure SQL Database**.

## 📌 Overview

Using this pipeline:
- CSV files from an Azure Storage Account are ingested.
- Data is transformed (optionally).
- Structured data is stored in an Azure SQL Database.
- Pipelines and triggers are used for automation and orchestration.

## ⚙️ Components

### 1. **Azure Blob Storage**
- Used as the source to store unstructured CSV files.
- Folder structure or naming convention can be used for organization.

### 2. **Azure SQL Database**
- Target database to hold structured and cleaned data.
- Tables and schema must be pre-created to match the expected structure.

### 3. **Azure Data Factory**
- Used to orchestrate the ETL (Extract, Transform, Load) process.
- Consists of:
  - **Linked Services**: Define connection details for Blob Storage and SQL Database.
  - **Datasets**: Define the structure and format of the data (CSV and SQL Table).
  - **Pipelines**: Handle the copy activity and data movement.
  - **Triggers**: Automate the pipeline execution (e.g., scheduled daily runs).

## 🔗 Linked Services
- **AzureBlobStorageLS**: Connects to the Azure Storage Account.
- **AzureSQLDBLS**: Connects to the Azure SQL Database using SQL authentication or managed identity.

## 📁 Datasets
- **InputDataset_CSV**: Represents the CSV file (can be parameterized for filename/folder).
- **OutputDataset_SQL**: Represents the target SQL table in Azure SQL Database.

## 🔄 Pipeline
- **CopyCSVToSQL**:
  - Uses the **Copy Activity** to move data from Blob Storage to Azure SQL Database.
  - Optionally includes data mapping and schema transformation.

## ⏰ Trigger
- **ScheduleTrigger**: Runs the pipeline at a specified interval (e.g., daily at midnight).
- Can also be triggered manually for testing or debugging.

## ✅ Prerequisites
- Azure Storage Account with access to container and CSV files.
- Azure SQL Database with appropriate schema and permissions.
- Azure Data Factory instance with necessary permissions to access both storage and SQL DB.

## 🚀 Deployment Steps
1. Create linked services for Blob and SQL DB.
2. Create datasets for source and destination.
3. Build the pipeline with copy activity.
4. Configure and test data mappings.
5. Add triggers for automation.
6. Monitor pipeline execution via ADF monitoring tab.

## 📌 Notes
- Ensure proper access rights (IAM roles or firewall rules) are configured.
- Handle schema drift or mapping mismatches using ADF data mapping UI.
- Use parameterized pipelines for reusable logic across multiple files/tables.

## 📊 Monitoring
Use the ADF Monitor tab to:
- Track pipeline runs
- View activity durations
- Troubleshoot failed executions

## 📁 Repository Structure
