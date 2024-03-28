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
**Database Security**

**MS SQL DB Authentication-**

- Windows Authentication mode (Recommended
- SQL Server Authentication mode- username and password (connect from anywhere
- Mixed Mode

**Network Connectivity-**

- Public Endpoint
- Private Endpoint

**Azure Defender -** 

- Forr advanced sql security capabilities for vulnerability assessment and advanced threat protection
- available for Azure SQL DB, SQL managed instance, and Synapse Analytics
- 30 days free trial and 15 USD/server/month

**Azure DB Firewall Rules-**

- Azure dbs are protected by server firewall- internal firewall that resides on db server
- all connections are rejected by default to db
- we can set rules within azure portal or via T-SQL
- Connection policy options are - Default, Proxy or Redirect

**Always Encrypted-**

- a feature that encrypts columns in an Azure DB or SQL Server
- uses column encryption keys and column master keys (key-protecting keys)

**Role-Based Access Controls (RBAC)-**

- SQL DB Contributor - manage SQL DB, but not access to them, can’t manage security policies or their parent sql servers
- SQL Managed Instance Contributor- manage SQL managed instances and network config. can’t give access to others
- SQL Security Manager-manage security policies of sql servers and dbs, no access to sql servers
- SQL Server Contributor- manage sql servers and dbs, no access to sql servers

**Transparent Data Encryption (TDW)**

- It encrypts data-at-rest for Microsoft DBs
- It can be applied to SQL Server, Azure SQL DB, Azure Synapse Analytics
- uses a DEK- Data Encryption Key (stored in db boot record)
- DEK is a symmetric key - same key is used at the time of encryption as well as decryption
- Steps to apply TDE to a DB-
    - Create a DB Master Key
    - Create a Certificate to support TDE
    - Create DB Encryption Key
    - Enable TDE on DB

**Dynamic Data Masking-**

- Data masking -a request for data to be transformed to mask sensitive data e.g credit card number
- It can be applied to SQL Server, Azure SQL DB, Azure Synapse Analytics
- The data in the db remains untransformed. On passing through a masking service, it is masked for the output
- Create a Dynamic Data Masking policy:
    - SQL users excluded from masking - users who can get data masked
    - Masking rules - what fields need to be masked
    - Masking functions- how to apply masking to fields

**Private Links-**

- allows to establish secure connections between Azure resources so traffic remains within the Azure Network
- Private Link Endpoint - is an network interface that connects you privately to azure services, it’s a private IP address from your VNet
- Private Link Service- allows you to connect your own workload to private link.
- You need an Azure Standard Internal Load Balancer and associate it with the link service
- Many Azure services by default work with private link eg. Azure Storage, Cosmos DB, SQL
- Third party provides can be powered by Private Link

**Azure Tables and Cosmos DB**

**Key Value Store**-

- dumb and fast, super easy highly scalable
- a unique key alongside each value
- a simple key/value store could resemble a dictionary
- or could also resemble tabular data, but it does not have to have same number of columns for each row, hence it is schema-less

**Document Store-** 

- NOSQL db that stores documents as its primary data structure (XML, JSON or JSON-like)
- Compared to relational DB- Collections are equivalent of ~ Tables, Documents ~ Rows, Fields ~ Columns, Indexes are same in both, Embedding & Linking ~ Joins

**MongoDB-**

- open-source document DB which stores JSON-like documents
- the primary data structure for Mongo DB is called **BSON** (subset of JSON)
- BSON is more efficient both in storage and scan speed, and have more data types than JSON
- Mongo DB supports searches against fields, ranged queries, regular-expressions
- Mongo DB supports primary and secondary indexes
- Mongo DB has replica sets to obtain high availability
- Mongo DB scales horizontally using sharding
- Mongo DB can run over multiple servers via load balancing
- Mongo DB can be used as a File System, called GridFS
- Mongo DB provides 3 ways to perform aggregation (grouping data during a query)
    - aggregation pipeline
    - map-reduce
    - single-purpose aggregation
- Mongo DB supports fixed-size collections called **capped collections**
- Mongo DB claims to support multi-document ACID transactions

**Graph Database-**

- A graph db is a db composed of a data structure that uses **vertices (nodes, dots)** which form **relationships** to other vertices via **edges (arcs, lines).**
- Node will contain data properties while edge can contain relational data such as direction and data properties
- Some of the use cases for graph db are- Master data management, IAM, fraud detection, traceability in manufacturing, feature engineering (ML) product recommendations, social media graphing

**Apache TinkerPop and Gremlin-**

- Apache TinkerPop is a **graph computing framework** for both OLTP (graph databases) and OLAP (graph analytic systems), enables developers to use **an vendor-agnostic distributed framework** to traverse (query) many different graph systems.
    - Commonly used DB are Amazon Neptune, CosmosDB, Hadoop (Spark) (OLAP), Neo4j, OrientDB (OLTP), Titan (OLTP)
- TinkerPop includes a graph traversal language called **Gremlin.**
- Gremlin is a single language that can be used for all these graph systems
- Gremlin is designed to “Write once, run anywhere” **(WORA)**
- **Gremlin Host Language Embedding** means you can use your favorite programming language to write Gremlin
- Gremlin traversal can be evaluated as-
    - real-time database query (OLTP)
    - or as a batch analytics query (OLAP)

**Azure Tables-**

- Azure table storage is a NoSQL key/value datastore
    - can be hosted on Azure storage accounts, designed for single region and single table
    - can be hosted on cosmosDB, designed for scale across multiple regions
    - stores non-relational structured data with a schema-less design
- Azure Table Storage API and MS Azure Storage Explorer - are 2 ways to interact with azure table
- Partition Key and Row Keys are used in Azure tables to make data unique

**CosmosDB-**

- It’s a service for fully-managed NoSQL databases that’re designed to scale and high performance
- Different kinds of **NoSQL db engines** can be used to interact via an API
    - Core SQL (document datastore) - *Default*
    - Azure Cosmos DB API for MongoDB (document datastore)
    - Azure Table ((key/value datastore)
    - Gremlin (graph datastore) based on Apache TinkerPop
- All these engines specify **capacity** to choose from- **provisioned throughput or serverless**
- CosmosDB Explorer is web interface to explore and interact with CosmosDB accounts  at cosmos.azure.com

**Azure Table Vs CosmosDB Table API-**

- Latency- Fast, but no upper boundsVs Single-digit millisecond (read and write)
- Throughput- variable limit 20,000 ops/sec Vs Guaranted backed by SLAs, No upper limit
- Global Distribution- Single region Vs 30+ regions
- Indexing- only primary index on partition key and row key Vs automatic and complete indexing on all properties, no index management
- Query Execution- uses index and scans Vs automatic indexing for fast query times
- Consistency- Strong within primary region, Eventual within sec region Vs 5 well-defined consistency levels
- Pricing- Consumption-based Vs consumption-based or provisioned capacity
- SLAs- 99.99% availability Vs 99.99% availability SLA

**Hadoop Systems-**

**Apache Hadoop-**

- Open Source framework for **distributed processing of large data sets**
- Hadoop allows to distribute across many servers eg. HDFS and computing queries across many servers eg. MapReduce
- these servers don’t need to be specialized hardware and can run on common hardware
- Apache Hadoop Framework has the following:
    - Hadoop Common- common util and libraries
    - Hadoop Distributed File System (HDFS)- resilient and redundant file storage system
    - Hadoop MapReduce- writes apps (to process multi TB data in-parallel on large clusters
    - Hbase- a distributed, scalable, big data store
    - YARN- manages resources, nodes, containers and does scheduling
    - HIVE- used for generating reports using an SQL language
    - PIG- a high-level **scripting**  language to write complex data transformations
- Hadoop components allows Hadoop to integrate with many other open-source projects

**Apache Kafka-**

- open-source **streaming platform -**  to create high -performance data pipelines, streaming analytics, data integration, and mission-critical applications
- originally developed by LinkedIn, and open-sourced in 2011
- written in Scala and Java, we need to write Java code to use Kafka
- In Kafka
    - data is stored on a **Kafka Cluster** which can span multiple machines
    - **Producers-** publish messages in key/value format using the **Kafka Producer API**
    - **Consumers-** listen for messages and consume them using the **Kafka Consumer API**
    - Messages are organized into  **Topics**
    - Producers will push messages to topics and consumers will listen on topics

**Azure HDInsights-**

- a  managed service to run popular open-source analytics service
- HDInsights supports-
    - Apache- Hadoop, Spark, Kafka, Storm, Hive, HBase, Low Latency Analytical Processing (LLAP), R
- HDInsights has broad range of scenarios such as-
    - ETL, Data Warehousing, ML and IoT
- **Apache Ambari-** open-source Hadoop management web-portal to provisioning, managing and monitoring Apache Hadoop Clusters

**Azure and Databricks-**

**Apache Spark-** 

- open-source **unified analytics engine** for **big data and ML**
- can perform 100x speed faster in memory and 10x fast on disk than Hadoop
- described as lightening fast
- Apache Spark- is a collection of libraries that work well together to form an **analytics ecosystem**
    1. **Spark Core-** the underlying engine and API, supports R, SQL, Python, Scala, Java
    2. **Spark SQL-** introduces a data structure called a ** data frame** used to work with structured and semi-structured data
    3. **Spark Streaming-** Allows spark to ingest data from many streaming devices- HDFS, Flume, Kafka, Twitter, Kinesis
    4. **GraphX-** distributed graph-processing framework
    5. **Machine Learning Library (MLib)-** a distributed ML framework with common ML and statistical algos
- **Resilient Distributed Dataset (RDD)-** is a domain specific language (DSL) to execute various parallel operations on an Apache Spark cluster.

**Azure Databricks-**

- Databricks is software company specializing in providing fully managed Apache Spark clusters, the founders were the creators of Apache Spark, Delta Lake, and MLFlow
- Databricks has 2 offerings-
    - **Databricks Platform-** cloud based spark platform with easy to use web UI
        - launch fully managed spark clusters
        - launch notebooks to write code and interact with spark
        - create workspaces to collaborate with team members
        - RBAC
        - create jobs for ELT or data analysis tasks that runs immediately or on a schedule
        - create MLFlow workflows
        - available on all main cloud service providers- AWS, Azure, GCP
    - **Databricks Community edition-** free version for educational user
        - create a free micro-cluster that terminates after 2 hours when idle
        - no workspace, jobs or RBAC
- **Azure Databricks** is a partnership between Microsoft and Databricks to offer the Databricks platform within the Azure portal running on Azure compute services
    - Azure Databricks offer 2 environments-
        - **Azure Databricks Workspace**- runs with integration to other azure services like for Batching- Azure Data Factory, Streaming- Apache Kafka Event Hub, or IoT Hub, Storage- Azure Blob Storage or Azure Data Lake Storage
        - **Azure Databricks SQL Analytics**- run SQL queries on data lake, create multiple visualization types to explore query results, build and share dashboards
- Pricing Tier could be Standard, Premium or Trial (Premium 14 days free DBUs)

**ELT and SQL Tools-**

**SQL Server Management Studio-**

- SSMA is an IDE for managing any SQL infrastructure
- access, configure, manage, administer and develop all components of
    - SQL Server
    - Azure SQL Database
    - Azure Synapse Analytics
- Object Explorer- view and manage all the objects in one or more instances of SQL server
- Template Explorer- build and manage files of boilerplate text that you use to speed the development of queries and scripts

**SQL Server Data Tools-**

- SSDT transforms db development by introducing a ubiquitous, declarative model that spans all the phases of database development **inside Visual Studio**
- SQL Server Object Explorer in Visual Studio

**Azure Data Studio- (Similar to SSMS)**

- It’s a cross-platform database tool for data professionals using on-premise and any cloud data platforms for win, mac and linux to **Query, Design and Manage DBs and Data Warehouses**
- It offers-
    - modern editor very similar to VS Code
    - code snippets
    - source control integration
    - integrated terminal
    - Jupyter notebooks
    - a marketplace of free extensions- SQL db inspector, Kusto (KQL), PostgreSQL and many more!

**Azure Data Factory-**

- A managed service for **ELT, ETL and data integration**
- create data-driven workflows for orchestrating data movement and transforming data at scale
- create **pipelines** to schedule data-driven workflows
- publish transformed data to data stores such as Azure Synapse Analytics
- **activities** - a processing step in a pipeline
- **datasets**- data structures within the data store
- **linked services-** connection information for data sources to connect to data factory
- **data flows-**  logic to determine how data moves through a pipeline or is transformed
- **Integration Runtimes (RI)-** compute infrastructure used by Azure Data Factory
- **control flows-** orchestration of pipeline activities, like chaining activities in a sequence, branching

**SQL Server Integration Services (SSIS)-**

- platform for building enterprise level data integration and data transformations solutions

+ **Data Analyst**: Analyze business data to reveal important information
    + **Responsibilities**: Provides insights into data, visual reporting, modelling data, combines data for visualization & analysis
    + **Common tools**: **Power BI Desktop, Power BI Portal, Power BI Services, Power BI Report Builder**

Database Administrator
