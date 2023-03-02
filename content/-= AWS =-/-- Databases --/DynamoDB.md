# DynamoDB
#aws #cloud #databases #nosql

Key value and document database (NoSQL) solution by [AWS](-=%20AWS%20=-/AWS.md) which can guarantee consistent read and write speed at any scale .

NoSQL is a database which is neither relational and does not use SQL ro query the data for results.

**Features:**
- Fully managed
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
![Pasted image 20220724013608](-=%20AWS%20=-/--%20Databases%20--/Pasted%20image%2020220724013608.png)




## Reads:
When data needs to be updated it has to write updates to all copies. It is possible for data to be inconsistent if you are reading from a copy which has yet to be updated. You have the ability to choose the read consistency in DynamoDB to meet your needs.

![Pasted image 20220724013641](-=%20AWS%20=-/--%20Databases%20--/Pasted%20image%2020220724013641.png)




![Pasted image 20220724013804](-=%20AWS%20=-/--%20Databases%20--/Pasted%20image%2020220724013804.png)