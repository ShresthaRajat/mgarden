# AWS Glue
#aws #cloud 

A fully managed [ETL](Software%20Engineering/Datastores/Big%20Data/ETL.md) service by [AWS](Cloud%20Computing/AWS/AWS.md), whihc is used for preparing data for analytics. It runs ETL jobs on fully managed scale-out Apache Spark Environment.  AWS Glue discovers data and stores metadata (e.g. table definition and schema) in the Data Catalog. Works with data lakes like [Snowflake](Snowflake) , data warehouses like [Redshift](Cloud%20Computing/AWS/Databases/Redshift.md), and data stores like [RDS](Cloud%20Computing/AWS/Databases/RDS.md) or [Database on EC2](Cloud%20Computing/AWS/Databases/Database%20on%20EC2.md). 



You can use a crawler to populate the AWS Glue Data Catalog with tables. A crawler can crawl multiple data stores in a single run. Upon completion, the crawler creates or updates one or more tables in your Data Catalog and are used by [ETL](Software%20Engineering/Datastores/Big%20Data/ETL.md) jobs that you define in AWS [Glue](Cloud%20Computing/AWS/Databases/Glue.md).


## Data Catalog