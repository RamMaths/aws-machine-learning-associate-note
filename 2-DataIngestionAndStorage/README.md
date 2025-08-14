# Data Ingestion and Storage

## Data Engineering Fundamentals

### Types of Data

#### Structured Data

- Definition: Data that is orgnizied in a defined manner or schema, typically found in relational databases
- Characteristics:
    - Easily queryable
    - Organized in rows and columns
    - Has a consistent structure
- Examples:
    - Database tables
    - CSV files with consistent columns
    - Excel spread sheets

#### Unstructured Data

- Definition: Data that doesn't have a predefined structure or shcema
- Characteristics:
    - Not Easily queryable without preprocessing
    - May come in various formats
- Examples:
    - Text files without a fixed formats
    - Videos and audio files
    - Images
    - Emails and word processing documents

#### Semistructured Data

- Definition: data that is not as organized as structured data but has some level of structure in the form of tags, hierarchies, or other patterns.
- Characteristics:
    - Elements might be tagged or categorized in some way
    - More flexible than structured data but not as chaotic as unstructured data
- Examples:
    - XML and JSON files
    - Email headers (which have a mix of structured fields like date, subject, etc and unstructured data in the body )
    - Log files with varied formats

### Properties of Data

#### Volume

- Definition: Refers to the amount or size of data that organizations are dealing with at any given time.
- Characteristics:
    - May range from gigabytes to petabytes or even More.
    - Challenges in storing, processing, and analyzing high volumes of data.
- Examples:
    - A popular social media platform processing terabytes of data daily from user posts images, and videos.
    - Retailers collecting years' worth of transaction data, amounting to several petabytes.

#### Velocity

- Definition: Refers to the speed at which new data is generated, collected, and processed
- Characteristics:
    - High velocity requires real-time or near-real-time processing capabilities.
    - Rapid ingestion and processing can be critical for certain applications.
- Examples:
    - Sensor data from IoT devices Streaming readings every milisecond.
    - High-frequency trading systems where milliseconds can make a diffrence in decision-making.

#### Variety

- A business analyzing data from relational databases (structured), emails (unstructured), and JSON logs (semi-structured).
- Healthcare systems collecting data from electronic medical records, wearable, health devices, and patient feedback forms.

## Data Warehouses, Lakes and Lakehouses

### Data Warehouse

- Definition: A centralizied repository optimizied for analysis where data from different sources is stored in a structured format.
- Characteristics:
    - Designed for complex queries and analysis.
    - Data is cleaned, transformed, and loaded (ETL process).
    - Typically uses a star or snowflake schema.
    - Optimized for read-heavy operations.
- Examples:
    - Amazon Redshift
    - Google BigQuery
    - Microsoft Azure SQL Data Warehouse

![Datawarehouse](../assets/datawarehouse.png)

### Data Lake

- Definition: A storage repository that holds vast amounts of raw data in its native format, including structured, semi-structured, and unstructured data.
- Characteristics:
    - Can store large volumes of raw data without predefined schema
    - Data is loaded as-is, no need for preprocessing
    - Supports batch, real-time, and stream processing
    - Can be queried for data transformation or exploration purposes
- Examples:
    - Amazon Simple Storage Serivce (S3) when used as a data lake
    - Azure Data Lake Storage
    - Hadoop Distributed File System (HDFS)

### Comparing the two

- Schema:
    - Data Warehouse: Schema-on-write (predefined shcema before writing data)
        - Extract - Transform - Load (ETL)
    - Data Lake: Schema-on-read (schema is defined at the time of reading data)
         - Extract - Load - Transform (ELT)
- Data Types:
    - Data Warehouse: Primarily structured data
    - Data Lake: Both structured and unstructured data
- Agility:
    - Data Warehouse: Less agile due to predefined schema
    - Data Lake: More agile as it accepts raw data without a predefined structure
- Processing:
    - Data Warehosue: ETL (Extract, Transform, Load)
    - Data Lake: ELT (Extract, Load, Transform) or just Load for storage purposes
- Cost:
    - Data Warehouse: Typically more expensive because of optimizations for compex queries
    - Data Lake: Cost-effective storage solutions, but costs casrise when processing large amounts of data

### Choosing a Warehouse vs a Lake

- Use a Data Warehouse when
    - You have structured data sources and require fast and complex queries.
    - Data interation from different sources is essential.
    - Buisness intelligence and analytics are the primary use cases.
- Use a Data Lake when:
    - You have a mix of structured, semi-structured, or unstructured data
    - You need a scalable and cost-effective solution to store massive amounts of data.
    - Future needs for data are uncertain, and you want flexibility in storage and processing
    - Advanced analytics, machine learning, or data discovery are key goals.

### Data Lakehouse

- Definition: A hybrid data architecture that combines the best features of data lakes and data warehouses, aiming to provide the performance, reliability, and capabilities of a data warehouse while maintaining the flexibility, scale, and low-cost storage of data lakes.
    - Characteristics:
        - Supports both structured and unstructured data.
        - Allows for schema-on-write and schema-on-read.
        - Provides capabilities for both detailed analytics and machine learning tasks.
        - Typically built on top of cloud or distribited architectures.
        - Benefits from technologies like Delta Lake, which bring ACID transactions to big data.
    - Examples:
        - **AWS Lake Formation (with S3 and Redshift Spectrum)**
        - **Delta Lake**: An open-source storage layer that brings ACID transactions to Apache Spark and big data workloads.
        - **Databricks Lakehouse Platform**: A unified platform that combines the capabilities of data lakes and data warehouses.
        - **Azure Synapse analytics**: Microsoft's analytics service that brings together big data and data warehousing.

## Data Mesh

- Coined in 2019: it's more about governance and organization
- Individual teams own "data products" within a given domain
- These data products serve various "use cases" around the organization
- "Domain-based data management"
- Federated governance with central standards
- Self-service tooling & infrastructure
- Data lakes, warehouses, etc. may be part of it
    - But a "data mesh" is more about the "data management paradigm" and not the specific technologies or architectures

![Datamesh](../assets/datamesh.png)

## ETL & ELT Pipelines and Orchestration

### ETL Pipelines

- **Definition**: It's a process used to move data from source systems into adata warehouse.

### ETL Pipelines:Extract

- Retrieve raw data from source systems, which can be databases, CRMs, flat files, APIs, or other data repositories
- Ensure data integrity during the extraction phase.
- Can be done in real-time or in batches, depending on requirements

### ETL Pipelines: Transform

- Convert the extract data into a format suitable for the target data warehouses
- Can involve various operations such as:
    - Data cleansing
    - Data enrichment
    - Format changes
    - Aggregations or computations
    - Encoding or decoding data
    - Handling missing values

### ETL Pipelines: Load

- Move the transformed data into the target data warehouse or another data repository.
- Can be done in batches (all at once) or in a streaming manner (as data becomes available)
- Ensure that data maintains its integrity during the loading phase

### Managin ETL Pipelines

- This process must be automated in some reliable way
- AWS Glue
- Orchestration services
    - EventBridge
    - Amazon Managed Workflows for Apache Airflow [Amazon MWAA]
    - AWS Step Functions
    - Lambda
    - Glue Workflows
- We'll get into specific architectures later
