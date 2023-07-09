---
tags: [cloud, aws, data-analytics]
title: Amazon Athena
aliases: [Amazon Athena]
linter-yaml-title-alias: Amazon Athena
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# Amazon Athena
#cloud #aws #data-analytics 

A serverless service from [AWS](Cloud%20Computing/AWS/AWS.md) to run [SQL](Software%20Engineering/Datastores/Databases/SQL.md) queries against data stored in [S3](Cloud%20Computing/AWS/Storage/S3.md) like CSV, TSV, JSON, PARQUET, and ORC formats. You can also use AWS [Glue](Cloud%20Computing/AWS/Databases/Glue.md) as a data catalog which stores the metadata information and schema about the databases and tables. • Can be connected to other data sources with [Lambda](Cloud%20Computing/AWS/Compute/Lambda.md) to query the data sources from places like [CloudWatch](Cloud%20Computing/AWS/Monitoring/CloudWatch.md) Logs, [Redshift](Cloud%20Computing/AWS/Databases/Redshift.md), etc.

![](Attachments/Pasted%20image%2020230324214042.png)


## Optimizing for Performance
• Partition your data
• Bucket your data – bucket the data within a single partition
• Use Compression – AWS recommend using either Apache Parquet or Apache ORC
• Optimize file sizes
• Optimize columnar data store generation – Apache Parquet and Apache ORC are popular columnar data stores
• Optimize ORDER BY and Optimize GROUP BY
• Use approximate functions
• Only include the columns that you need

https://aws.amazon.com/blogs/big-data/top-10-performance-tuning-tips-for-amazon-athena/