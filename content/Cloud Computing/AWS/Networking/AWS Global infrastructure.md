---
tags: [aws, cloud, networking]
---
# AWS Global Infrastructure
#aws #cloud #networking 

![](Attachments/Pasted%20image%2020230305151607.png)

### Regions
**Geographically distinct** Location with AWS datacentres clustered around multiple [#Avilability Zones AZ](#Avilability%20Zones%20AZ) within the same region. There are 22 Geographic Regions set up by AWS all around the world.

- 22 Regions
- Largest region = US-EAST
- US-EAST-1 (North Virginia) is the region where you see all of your billing information


![AWS Regions map](Attachments/AWS%20Regions%20map.png)

### Avilability Zones [AZ]

One or more Datacenters within a AWS Region.

There are total of 69 AZ Spread all around the world.

- 69 AZs
- At least 2 AZs in a single regions
- Aming for 3 AZs per region
- Latency between AZ is sub 10 milliseconds

![AZs in a region of EU-AF](Attachments/AZs%20in%20a%20region%20of%20EU-AF.png)


### Edge Locations
Data Centers owned by AWS or partners used for accelerating data access across the world. It as direct connection to the AWS network.


- Many Edge locations (~225)
- To upload/download data fast
- Serves requests for CloudFront and Route 53
- [S3](Cloud%20Computing/AWS/Storage/S3.md) Transfer Acceleration traffic and API Gateway endpoint traffic also utilizes edge locations


### GovCloud (US)

AWS GovCloud Region allow customers to host sensitive **Controlled Unclassified Information** and other types of regulated workload.

- GovCloud Regions are only operated by employees who are US citizens, on US soil.
- So they are exclusively for US
- Made for customers who require secure solutions that comply with us government regulations