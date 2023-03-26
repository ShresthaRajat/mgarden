# Amazon Elasticache
#aws #cloud #databases 

A fully managed [AWS](Cloud%20Computing/AWS/AWS.md) Implementation of [Redis](Redis) and [Memcached](Memcached). It is a key/value store which is In-memory for high performance reads and low latency. It is usually put infront of a database like [RDS](Cloud%20Computing/AWS/Databases/RDS.md) and [DynamoDB](Cloud%20Computing/AWS/Databases/DynamoDB.md) To increase read speeds.

It can be used for caching
• Data that is same for a long time and frequently accessed
• Applications that are tolerant of stale data (cannot be used in real-time)
• Data is slow and expensive to get compared to cache retrieval
• Require push-button scalability for memory, writes and reads
• Often used for storing session state

![](Attachments/Pasted%20image%2020230322225739.png)
![Pasted image 20220724124451](Attachments/Pasted%20image%2020220724124451.png)

## Scaling


### Memcached
- can be scaled by adding nodes to a cluster or by scaling an individual instance vertically.
![](Attachments/Pasted%20image%2020230322230305.png)


### Redis Cluster mode disable
Can add a replica or change nodetype.

![](Attachments/Pasted%20image%2020230322230438.png)

### Redis Cluster mode enabled

Use **Online Resharding** to add or vertically scaling.
Use **Offline Resharding** to add or upgrade engine (more flexible than online)
![](Attachments/Pasted%20image%2020230322230423.png)
