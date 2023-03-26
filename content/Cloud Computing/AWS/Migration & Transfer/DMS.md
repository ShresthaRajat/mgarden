# Database Migration Service (DMS)
#aws #cloud #cloud-migration  #databases 

AWS DMS is a database migration solution by [AWS](Cloud%20Computing/AWS/AWS.md) to migrate onprem to cloud or even from any cloud database to another type of database server hosted on cloud. It is popularly used to migrate to [DynamoDB](Cloud%20Computing/AWS/Databases/DynamoDB.md) or [RDS](Cloud%20Computing/AWS/Databases/RDS.md)
With DMS you can migrate from:
**Cloud to Cloud** – EC2 to RDS, RDS to RDS, RDS to Aurora
**On-Premises to Cloud** - from a local MySQL to RDS, etc

![](Attachments/Pasted%20image%2020230321144300.png)


## Types of DMS operations

### Homogeneous migrations
You can use DMS to migrate database from one system to another using the same platform like:
Oracle to Oracle, 
MySQL to RDS MySQL, 
Microsoft SQL to RDS for SQL Server

### Heterogeneous migrations 
You can migrate data from one type of database to another type but you must convert schema first wit the Shema Conversion Tool (SCT).

For example you can convert and migrate from:
Oracle to Aurora, 
Oracle to
PostgreSQL, 
Microsoft SQL to RDS MySQL 


## Use cases:
you can use DMS to do the following:

• **Development and Test** – use the cloud for dev/test workloads
• **Database consolidation** – consolidate multiple source DBs to a single target DB
• **Continuous Data Replication** – use for DR, dev/test, single source multi-target or multi-source single target