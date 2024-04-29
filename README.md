# Formula-1-Project-Using-Azure--Databricks
This is a project on building a pipeline on Azure for reporting and doing analysis of the data from Formula 1 Motorsport.
# Data Source
1. The data for this project is obtained from an open source API called Ergast Developer API (https://ergast.com/mrd/ ). The API provides data for the Formula One series, from the beginning of the world championships in 1950
2. This project is using the database tables in CSV format.
3. The structure of the database is shown in Entity Relationship Diagram as below and explained in the Database User Guide.(http://ergast.com/docs/f1db_user_guide.txt)
![ER-diagram](https://github.com/devavi/Formula-1-Project-Using-Azure--Databricks/assets/24600917/42430529-67d5-44f3-959e-142b1946e0a4)


# Data Pipeline
![data_pipeline](https://github.com/devavi/Formula-1-Project-Using-Azure--Databricks/assets/24600917/333ebb70-88f0-4b75-a94a-7a1458d04599)
The Ergest Developer API data is imported into an Azure Data Lake Storage (ADLS) container as raw data. We then utilize Databricks notebook to process and ingest this data into the ingested raw layer. The ingested data is structured with a schema and stored in columnar parquet format, with partitions created where applicable. Additionally, we include audit-related information such as date and data source. The transformed data is then processed through Databricks notebook for the presentation layer, where we create dashboards to fulfill our analysis requirements. Azure Data Factory is employed for scheduling and monitoring tasks. To meet GDPR and time travel requirements, the pipeline is later converted into the Delta Lakehouse architecture.

# Services Used
1. Azure Databricks
2. Azure Data Lake Storage Gen2
3. Azure Data Factory
4. PySpark and Spark SQL
5. Delta Lake
6. Azure Key Vault
