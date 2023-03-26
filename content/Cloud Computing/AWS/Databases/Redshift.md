# Redshift
#aws #cloud #storage #data-warehouse

It is a fully managed Petabase-sized [Data Warehouse](Software%20Engineering/Datastores/Big%20Data/Data%20Warehouse.md) solution for by [AWS](Cloud%20Computing/AWS/AWS.md). Redshift is singe AZ. Snapshots can be restored at a different AZ. usually data from various databases ([RDS](Cloud%20Computing/AWS/Databases/RDS.md), [DynamoDB](Cloud%20Computing/AWS/Databases/DynamoDB.md), etc) will be loaded into redshift to perform [OLAP](Software%20Engineering/Datastores/Big%20Data/OLAP.md) queries.

![](Attachments/Pasted%20image%2020230324223315.png)

## Redshift Data Sourcees
We can fetch data from many places, like:
- [RDS](Cloud%20Computing/AWS/Databases/RDS.md)
- [DynamoDB](Cloud%20Computing/AWS/Databases/DynamoDB.md)
- [Glue](Cloud%20Computing/AWS/Databases/Glue.md)
- [EMR](Cloud%20Computing/AWS/Databases/EMR.md)
- [S3](Cloud%20Computing/AWS/Storage/S3.md)
- etc.

![](Attachments/Pasted%20image%2020230324223618.png)

## Use cases
- To perform complex queries on big data (structured and semi-structured data) with fast performance
- For Frequently accessed data with consistent structured format.
- S3 objects can be accessed wit [Spectrum](Spectrum)
- Managed data warehouse solution with:
	• Automated provisioning, configuration and patching
	• Data durability with continuous backup to S3
	• Scales with simple API calls
	• Exabyte scale query capability




Pricing starts at $0.25 per hour with no upfront costs or commitments.
Scale up to petabytes for $1000 


![Pasted image 20220724012000](Attachments/Pasted%20image%2020220724012000.png)


![Pasted image 20220724012758](Attachments/Pasted%20image%2020220724012758.png)

![Pasted image 20220724013125](Attachments/Pasted%20image%2020220724013125.png)