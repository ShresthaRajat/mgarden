# DynamoDB
#aws #cloud #databases #nosql

Key value and document fully serverless database [NoSQL](Software%20Engineering/Datastores/Databases/NoSQL.md) solution by [AWS](Cloud%20Computing/AWS/AWS.md) which can guarantee consistent read and write speed at any scale. It is not relational like a [RDS](Cloud%20Computing/AWS/Databases/RDS.md) and is a table not a database

![](Attachments/Pasted%20image%2020230322231449.png)


**Features:**
- Fully managed
- Scales Horizontally
- Multiregion
- Multimaster
- Durable database
- Built-in Security
- Backup and restore
- In-memory cacheing

**Provides:**
Eventual Consistent Reads (default)
Strongly Consistent Reads


## Table Structure
![Pasted image 20220724013608](Attachments/Pasted%20image%2020220724013608.png)

![](Attachments/Pasted%20image%2020230322232626.png)


## Reads:
When data needs to be updated it has to write updates to all copies. It is possible for data to be inconsistent if you are reading from a copy which has yet to be updated. You have the ability to choose the read consistency in DynamoDB to meet your needs.

![Pasted image 20220724013641](Attachments/Pasted%20image%2020220724013641.png)



## DynamoDB Streams
Creates a sort of queue when ever a item is modified for 24 hour. The information could be created on certain triggers.
![](Attachments/Pasted%20image%2020230322234258.png)



## DAX

A highly available, in memory cache for DynamoDB, which improves performance to microsecond level. It only optimizes the read latency and you will not need to modify application logic and can be easily be introduced to application utilizing the DynamoDB directly.

- Optimized only for DynamoDB
- Does not support lazy loading 
- [Elasticache](Cloud%20Computing/AWS/Databases/Elasticache.md) will be harder to be implemented than DAX
- [Elasticache](Cloud%20Computing/AWS/Databases/Elasticache.md)doesnot work out of the box like DAX even though elasticace supports datastores required for DynamoDB
## DynamoDB Global tables

A multi region or multi active database (Multi-master) which does asynchronous replication across different regions.
![](Attachments/Pasted%20image%2020230322234854.png)

![](Attachments/Pasted%20image%2020230322234627.png)


![Pasted image 20220724013804](Attachments/Pasted%20image%2020220724013804.png)