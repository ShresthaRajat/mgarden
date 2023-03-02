# Aurora
#aws #cloud #rdbms #serverless #sql

Fully managed Postgres or MySQL database by [AWS](AWS/AWS.md).

Combines the speed and availability of high end database with the simplicity and cost-effectiveness of opensource databases

## Aurora Scaling
Starts with 10GG of Storage, and scale in 10GB increments upto 64TB

Storage is auto-scaling

Computing resource can scale all the way upto 32 vCPUs and 244Gb of memory


## Aurora-Availability

A minimum of 3-availability zones each contain 2 copies of your database.

so 6 copies are created. (2 copies in each availability zones)


## Aurora-Fault Tolerance and Durability
Aurora Backup and Failover are handelled automatically
Snapshots of Data can be shared with other AWS accounts

Storage is self-healing, in that data blocks and disks are continiously scanned for errors and repaired automatically.

## Aurora-Replicas

There are 2 types of replicas available:

![Pasted image 20220724011616](AWS/--%20Databases%20--/Pasted%20image%2020220724011616.png)



## Aurora-Serverless

Aurora except the database will automatically startup, shut-down, and scale capacity up or down based on your application's needs

Apps used a few times several times per day or week.. eg. low accessed databases.

pay for database storage and the database capacity and I/O your database consumes while it is active


![Pasted image 20220724011843](AWS/--%20Databases%20--/Pasted%20image%2020220724011843.png)
