# Databases and Analytics

## Introduction

- Relational Databases
- NoSQL Databases
  - Non relational
  - Stores data in flexible, non-tabular formats like documents, key-value pairs, wide columns, or graphs, rather than fixed rows and columns

## RDS and Aurora

- Amazon RDS
  - Relational Database Service
    - Managed Relational Database
    - Can't SSH into instances
    - Scalable
    - Multi-AZ setup for DR
    - Read Replicas for improved performance
  - Create databases that are managed by AWS
    - Postgres
    - MySQL
    - MariaDB
    - Oracle
    - MS SQL Server
    - IBM DB2
    - Aurora (Proprietary AWS database)

- Amazon Aurora
  - Proprietary AWS relational database
  - Postgres and MySQL are both supported
  - Cloud optimized
  - Storage automatically grows in increments of 10GB up to 250GB
  - Costs more than RDS but is more efficient

- Amazon Aurora Serverless
  - Automated instatiation and scaling 
  - Prostgres and MySQL are both supported
  - Pay per second
  - Best for infrequent, intermittend or unpredictable workloads

## RDS Deployments

- Read Replicas
  - Scale the read workload of your database
  - Can create up to 15 read replicas
  - Data is only written to the main database
- Multi-AZ
  - Failover incase of AZ outage
  - Data is only written to main database
  - Can only have 1 other AZ as a failover
- Multi-Region
  - Disaster Recovery
  - Local performance for global reads

## ElastiCache

- Managed cache (Redis or Memcached)
- Reduces database load for read intensive workloads

## DynamoDB

- NoSQL database
- Fully managed and highly available with replication across 3 AZ
- Scales to massive workloads
  - Distributed Serverless Database
- Single digit latency
- Integrated with IAM
- Standard and infrequent access table class
- DynamoDB Accelerator - DAX
  - In memory cache for DynamoDB
  - 10x performance improvement
  - Secure and scalable
- DAX is only used with DynamoDB

## DynamoDB - Global Tables

- Makes DynamoDB table accessible with low latency to multiple regions
- Active Active replication - read/write to any AWS region

## Redshift

- Based on Postgres
- Used for online analytical processing (OLAP)
- Load data once per hour
- Columnar data storage (not row)
- Massively Parallel Query Execution (MPP), highly available
- Pay as you go based on instances provisioned
- Has SQL interface for performing queries
- BI tools integrate with it
  - AWS Quicksight
  - Tableau

- Redshift Serverless
  - Automatically provisions and scales data warehouse capacity
  - Run analytics workloads without managing data warehouse infra
  - Use Cases
    - Reporting 
    - Dashboard applications
    - Real time analytics

## EMR

- Elastic MapReduce (EMR)
- Helps create Hadoop clusters to analyze and process data
- Clusters can be made up of hundreds of EC2 instances
- Supports Apache Spark, Hbase, Presto
- EMR takes care of all provesioning and configuration
- Use cases
  - Data processing
  - Machine learning
  - Web indexing 
  - Big data

## Athena

- Serverless query service to perform analytics agains S3 objects
- Uses SQL query language
- Supports CSV, JSON, ORC, Avro, and Parquet
- $5 per TB of data scanned
- Use compressed or columar data for cost savings
- Use cases
  - Business intelligence
  - Analytics
  - Logs

## QuickSight

- Serverless BI tool
- Use Cases
  - Business Analytics
  - Visualizations
  - Ad hoc analysis
- Integrated wqith 
  - RDS
  - Aurora
  - Athena
  - Redshift
  - S3

## Document DB

- AWS implementation of MongoDB
- Store, query and index JSON data
- Fully managed with replication across 3 AZ
- Storage grows in increments of 10GB
- Automatically scales

## Neptune

- Fully managed graph database
- Graph example: Social network
  - Users have friends
  - Posts have comments
  - Comments have likes
- Highly available across 3 AZ with 15 read replicas
- Optimized for highly connected datasets
- Use Cases
  - Knowledge graphs
  - fraud detection
  - Recommendation engines

## Timestream

- Fully managed serverless time series database
- Automatically scales
- Store and analyze trillions of events per day
- Built in time series analytics functions

## Managed Blockchain

- Join public blockchain networks or create your own private network
- Compatible with Hyperledger Fabric and Ethereum

## Glue

- Managed ETL service
- Prepare and transform data for analytics
- Serverless

## DMS

- Database Migration Service
- Migrate databases to AWS