## Data Warehousing Portfolio Project
This repository showcases a complete data warehousing and analytics solution, built as a portfolio project.
It covers the full lifecycle from designing and building a data warehouse to extracting meaningful, actionable insights. The project follows industry best practices in data engineering, data modeling, ETL processes, and analytics, making it a strong demonstration of real-world skills.

### Data Archietecture 
This project implements the Medallion Architecture framework, structured into three layers:
1. Bronze Layer: Captures raw, unprocessed data directly from source systems. In this project, data is ingested from CSV files into a SQL Server database.
2. Silver Layer: Focuses on data refinement, including cleansing, standardization, and normalization, to ensure high-quality, analysis-ready data.
3. Gold Layer: Contains business-ready, curated data, modeled into a star schema to support reporting, analytics, and actionable insights.
   
![Screenshot 2025-04-27 at 1 23 20 pm](https://github.com/user-attachments/assets/8e7e7169-9194-4d33-b141-30c783679e4c)

### Project Overview
1. **`Data Architecture:`** Built a modern data warehouse based on the Medallion Architecture, leveraging Bronze, Silver, and Gold layers for structured data flow.
2. **`ETL Development:`** Designed and implemented ETL pipelines to ingest, transform, and load data from source files into the warehouse.
3. **`Data Modeling:`** Created optimized fact and dimension tables to enable efficient analytical querying and reporting.
4. **`Analytics & Reporting:`** Developed SQL queries and dashboards to translate raw data into meaningful, actionable business insights.

### Project Setup
#### 1. Install SQL Server on MacBook: Since SQL Server does not run natively on macOS,set it up using Docker:
**`Step 1:`** Install Docker Desktop for Mac.
**`Step 2:`** Pull the SQL Server Docker image:
```
docker pull mcr.microsoft.com/mssql/server
```
**`Step 3:`** Run the SQL Server container:
```
docker run -e 'ACCEPT_EULA=Y' -e 'SA_PASSWORD=YourStrongPassword!' \
-p 1433:1433 --name sql_server_container -d mcr.microsoft.com/mssql/server
```
If you wanted to load the local files in the computer in the sql server then we  have to explicityly mount the folder into the docker container.
```
docker run -e "ACCEPT_EULA=Y" \
  -e "MSSQL_SA_PASSWORD=MyStrongPassword123" \
  -p 1433:1433 \
  -v <path of the Dataset> \
  --name sql-server-container \
  -d mcr.microsoft.com/mssql/server:2022-latest

```
Replace YourStrongPassword! with a strong password (must meet SQL Server password requirements) & <path of the Dataset> with actual path of the data.
**`Step 4:`** Connect to SQL Server using a SQL client like: Azure Data Studio (recommended for Mac)

#### 2. Set Up the Database
**`Step 1:`** Open Azure Data Studio, click on: New Connection

**`Step 2:`** Fill in the connection details:

Server: localhost
Port: 1433 (SQL Server inside Docker maps container's 1433 port to your Mac’s 1433)
Authentication type: SQL Login
Username: sa
Password: the password you set in Docker (YourStrongPassword!)

**`Step 3:`** Connect — and you’re in!


