---
tags: [aws, cloud, sql, databases, rdbms]
title: RDS
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# RDS
#aws #cloud #sql #databases #rdbms

A fully managed Relational Database Service by [AWS](Cloud%20Computing/AWS/AWS.md). RDS runs on an [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instance.  A managed relational Database service which supports many RDMS engine which are easy to scale, maintain and update easily.

- A RDS instance can scale only vertically.


## Backups
There are 2 types of backups, [Automated Backups](#Automated%20Backups) and [Manual Backup](Cloud%20Computing/AWS/Databases/RDS.md#Manual%20Backup).

### Automated Backups
Choose a Retention Period between 1 and 35 days, stores transaction logs throughout the day and Automated backups are enabled by default. All data is stored in [S3](Cloud%20Computing/AWS/Storage/S3.md). There is no additional charge for backup storage. You can define your backup window

![](Attachments/Pasted%20image%2020230322222905.png)

### Manual Backup
Manual backups the entire DB instance.
- For single-AZ DB instances there is a brief suspension of I/O
- For Multi-AZ SQL Server, I/O activity is briefly suspended on primary
- For Multi-AZ MariaDB, MySQL, Oracle and PostgreSQL the snapshot is taken from the standby
- Snapshots do not expire automatically(no retention period)


### Maintainance

- Operating system and DB patching can require taking the database offline
- These tasks take place during a maintenance window
- By default a weekly maintenance window is configured
- You can choose your own maintenance window


### Restoring Backups

When recovering AWS it will restore it via the most recently taken snapshot.
It never restores on top of running instance.
You will need to create a new RDS to restore on top of it


## RDS Security

- Encryption at rest can be enabled – includes DB storage, backups, read replicas and snapshots
- You can only enable encryption for an Amazon RDS DB instance when you create it, not after the DB instance is created
- DB instances that are encrypted can't be modified to disable encryption
- Uses AES 256 encryption and encryption is transparent with minimal performance impact
- RDS for Oracle and SQL Server is also supported using Transparent Data Encryption (TDE) (may have performance impact)
-  AWS KMS is used for managing encryption keys
- You can't have an encrypted read replica of an unencrypted DB instance or an unencrypted read replica of an encrypted DB instance
- Read replicas of encrypted master instances are encrypted
- The same key is used if in the same Region as the master
- If the read replica is in a different Region, a different key is used
- You can't restore an unencrypted backup or snapshot to an encrypted DB instance. (But you can create a unencrypted RDS instance to create an snapshot then create a new Encrypted RDS)

![](Attachments/Pasted%20image%2020230322223157.png)

## Encryption

You can turn encryption for all RDS engines


### Multi AZ
- Slave Database
- Makes an exact 
- Synchronous replication (highly durable)
- Used for Durability
- Only the database on the primary instance is active
- Backups are taken automatically
- Always Span across two AZ
- DB engine version upgrade happens on primary
- Automatic fail-over to standby instance when a problem is detected on the primary instance

## Read Replica

- Only allows read
- Asynchronous replication
- Used to improve performance
- All of the replicas are active
- No backups are configured by default
- Can be within a AZ, Cross-AZ or even Cross-Region
- DB engine version upgrade is independent from source instance.
- Should be manually promoted to a standalone database instance


## Multi AZ vs Read Replicas
![](Attachments/Pasted%20image%2020230322222616.png)


## Performance Insights
Gives you a rich performance insights of your database.




## When not to use RDS?
- When using other types of DB than (Mysql, MariaDB, SQL Server, PostgreSQL, Oracle)
- If you need Root access to the instance OS use [Database NoSQLNoSQLNoSQLNoSQLon EC2](Database%20NoSQLNoSQLNoSQLNoSQLon%20EC2)

![](Attachments/Pasted%20image%2020230322225104.png)



![Pasted image 20220724010918](Attachments/Pasted%20image%2020220724010918.png)

![Pasted image 20220724011034](Attachments/Pasted%20image%2020220724011034.png)

