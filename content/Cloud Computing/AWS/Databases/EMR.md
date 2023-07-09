---
tags: [aws, cloud, bigdata, data-analytics]
---
# EMR
#aws #cloud #bigdata #data-analytics 

A managed cluster platform by [AWS](Cloud%20Computing/AWS/AWS.md) for Apache Hadoop and Apache Spark and used mostly for processing data for analytics, BI or to transform data by performing [ETL](Software%20Engineering/Datastores/Big%20Data/ETL.md) functions.


## EMR integrations

[EC2](Cloud%20Computing/AWS/Compute/EC2.md) instances are used for running the nodes in the cluster. 
[VPC](Cloud%20Computing/AWS/Networking/VPC.md) is used to for networking
[S3](Cloud%20Computing/AWS/Storage/S3.md) is used for storing input/output data
[CloudWatch](Cloud%20Computing/AWS/Monitoring/CloudWatch.md) for monitoring cluster 
[IAM](Cloud%20Computing/AWS/Security%20&%20Identity/IAM.md) for managing permissions
[CloudTrail](Cloud%20Computing/AWS/Monitoring/CloudTrail.md) for auditing
[AWS DataPipeline](AWS%20DataPipeline) to schedule and start clusters
[Lake Formation](Lake%20Formation) To create data in S3 [Data Lake](Software%20Engineering/Datastores/Big%20Data/Data%20Lakes.md)

![](Attachments/Pasted%20image%2020230324224508.png)

## Use cases:

1. For loading data into [Redshift](Cloud%20Computing/AWS/Databases/Redshift.md) for [Data Warehousing](Software%20Engineering/Datastores/Big%20Data/Data%20Warehouse.md) BI analytics.
2. For loding into [S3](Cloud%20Computing/AWS/Storage/S3.md) after performing a ETL transformation for analytics.

![](Attachments/Pasted%20image%2020230324224539.png)