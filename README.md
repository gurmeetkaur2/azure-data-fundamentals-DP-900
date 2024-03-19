# Azure Data Fundamentals Certification (DP-900) - Study Notes
## Core Data-Related Azure Services
1. Azure Storage accounts - An umbrella service for various storage accounts - types are tables, files, blobs
2. Azure Blob Storage - Data stored as objects
3. Azure Tables - Key/Value, NOSQL
4. Azure Files
5.**Azure Storage Explorer**- Stand alone applications
6.**Azure Synapse Analytics** - Prviously known as Azure SQL Warehouse
7. **CosmoDB** - NoSQL DB service, can host various NoSQL engines
8. **Azure Data Lake Store (Gen2)** - A centralized data repo for big data, Blob storage designed for vast amount of data
9. **Azure Data Analytics** - BigData as a Service (BDaS), Wirte U-SQL to query Azure Data Lake
10. Azure Data Box - Import/export TBs of data via hard drive
11. SQL Server on Azure Virtual Machines
12. SQL Managed Instances
13. Azure SQL - Fully-managed MS SQL DB
14. Azure DB for <open source> managed relational DBs on AzureE.g. MySQL, MariaDB, PSQL
15. Azure Cache for Redis - In memory data store for returning extremely vast but extrmely volatile data
16. MS Office 365 Sharepoint - Shared file-system for orgs, Role Based Account Access
17. **Azure Databricks** - 3rd party espcially to handle Apache Spark to provide very fast ETL jobs, ML and Streaming
18. MS Power BI
19. HDInsights - fully managed Hadoop system, can run many open-source Big Data engines for data transformations for ETL
20. **Azure Data Studio** - Similar to SSMS
21. **Azure Data Factory** - ETL Pipeline Builder
22. SSIS - stand-alone windows app to prepare data for SQL workloads via transformation pipeline

[Azure SQL Family](https://azure.microsoft.com/en-us/blog/the-azure-sql-family-innovation-and-value-in-the-cloud/)

## Azure Data Roles
+ **Database Administrator**: Configures/maintains a database eg Azure Data Services or SQL Server
    + **Responsibilities**: DB management, manage security, granting user access, backups, monitor performance
    + **Common tools**: **Azure Data Studio, SSMS, Azure portal**

+ **Data Engineer**: Design and implement data tasks related to the transfer and storage of big data
    + **Responsibilities**: DB pipelines & process, Data ingestion storage, prepare data for analytics and analytical processing
    + **Common tools**: **Azure Synapse Analytics, SQL, Azure CLI**

+ **Data Analyst**: Analyze business data to reveal important information
    + **Responsibilities**: Provides insights into data, visual reporting, modelling data, combines data for visualization & analysis
    + **Common tools**: **Power BI Desktop, Power BI Portal, Power BI Services, Power BI Report Builder**

Database Administrator
