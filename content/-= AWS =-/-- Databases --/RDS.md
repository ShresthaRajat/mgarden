# RDS

#aws #cloud #sql #databases #rdbms
A fully managed Relational Database Service by [AWS](-=%20AWS%20=-/AWS.md)

A managed relational Database service which supports many RDMS engine which are easy to scale, maintain and update easily.

## Encryption

You can turn encryption for all RDS engines





## Backups

There are 2 types:

### Automated Backups
Choose a Retention Period between 1 and 35 days, stores transaction logs throughout the day and Automated backups are enabled by default. All data is stored in S3
 There is no additional charge for backup storage
 Yo can define your backup window

### Manual Backup
Manual backups


## Restoring Backups

When recovering AWS it will restore it via the most recently taken snapshot.

It never restores ontop of running instance.

You will need to create a new RDS to retore on top of it


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
- Should be manually promoted to a standalone dataabase instance



## Performance Insights
Gives you a rich performance insights of your database.


## Aurora Server-less
A fully managed Serverless solution provided by aws for RDBMS. 



![Pasted image 20220724010918](-=%20AWS%20=-/--%20Databases%20--/Pasted%20image%2020220724010918.png)

![Pasted image 20220724011034](-=%20AWS%20=-/--%20Databases%20--/Pasted%20image%2020220724011034.png)

