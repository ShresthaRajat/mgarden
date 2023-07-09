---
tags: [aws, cloud, rdbms, serverless, sql]
title: Aurora
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# Aurora
#aws #cloud #rdbms #serverless #sql

Fully managed Postgres or MySQL database by [AWS](Cloud%20Computing/AWS/AWS.md). Combines the speed and availability of high end database with the simplicity and cost-effectiveness of opensource databases

- High performance and scalability
- Aurora Replicas
- MySQL Read Replicas
- Global Database
- Multi-Master
- Serverless

![](Attachments/Pasted%20image%2020230322223630.png)

## Aurora Scaling
Starts with 10GG of Storage, and scale in 10GB increments upto 64TB

Storage is auto-scaling

Computing resource can scale all the way upto 32 vCPUs and 244Gb of memory


## Aurora-Availability

A minimum of 3-availability zones each contain 2 copies of your database.

so 6 copies are created. (2 copies in each availability zones)


## Aurora-Fault Tolerance and Durability
Aurora Backup and Fail-over are handled automatically
Snapshots of Data can be shared with other AWS accounts

Storage is self-healing, in that data blocks and disks are continuously scanned for errors and repaired automatically.

![](Attachments/Pasted%20image%2020230322224026.png)

### Aurora Cross region Replica
![](Attachments/Pasted%20image%2020230322224412.png)


### Aurora Global Database
![](Attachments/Pasted%20image%2020230322224455.png)


### Aurora Multi-Master
![](Attachments/Pasted%20image%2020230322224650.png)


### Aurora Serverless
Aurora Serverless is a good alternative to a traditional on demand database servers and could be used to:

• Infrequently used applications
• New applications
• Variable workloads
• Unpredictable workloads
• Development and test databases
• Multi-tenant applications
![](Attachments/Pasted%20image%2020230322224715.png)


## Aurora-Replicas

There are 2 types of replicas available:

![Pasted image 20220724011616](Attachments/Pasted%20image%2020220724011616.png)



## Aurora-Serverless

Aurora except the database will automatically startup, shut-down, and scale capacity up or down based on your application's needs

Apps used a few times several times per day or week.. eg. low accessed databases.

pay for database storage and the database capacity and I/O your database consumes while it is active


![Pasted image 20220724011843](Attachments/Pasted%20image%2020220724011843.png)
