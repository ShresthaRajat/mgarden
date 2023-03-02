---
title: AWS
enableToc: true
tags:
- Aws
- Cloud
---

AWS (Amazon Web Services) is one of the comprehensive, [](Cloud%20Computing/Cloud%20Providers.md#Cloud%20Providers) AWS services can offer an organization tools such as compute power, database storage and content delivery services.

AWS launched in 2006 from the internal infrastructure that Amazon.com built to handle its online retail operations. AWS was one of the first companies to introduce a [pay-as-you-go](https://www.techtarget.com/searchstorage/definition/pay-as-you-go-cloud-computing-PAYG-cloud-computing) cloud computing model that [scales](https://www.techtarget.com/searchdatacenter/definition/scalability) to provide users with compute, storage or throughput as needed.

AWS offers many different tools and solutions for enterprises and software developers that can be used in data centers in up to 190 countries. Groups such as government agencies, education institutions, nonprofits and private organizations can use AWS services.
[Elastic Compute Cloud EC2](Cloud%20Computing/AWS/Compute/Elastic%20Compute%20Cloud%20EC2.md)


## AWS Global Infrastructure

### Regions
**Geographically distinct** Location with AWS datacentres clustered around multiple [#Avilability Zones AZ](#Avilability%20Zones%20AZ) within the same region. There are 22 Geographic Regions set up by AWS all around the world.

- 22 Regions
- Largest region = US-EAST
- US-EAST-1 (North Virginia) is the region where you see all of your billing information


![AWS Regions map](Cloud%20Computing/AWS/AWS%20Regions%20map.png)

### Avilability Zones [AZ]

One or more Datacenters within a AWS Region.

There are total of 69 AZ Spread all around the world.

- 69 AZs
- At least 2 AZs in a single regions
- Aming for 3 AZs per region
- Latency between AZ is sub 10 milliseconds

![AZs in a region of EU-AF](Cloud%20Computing/AWS/AZs%20in%20a%20region%20of%20EU-AF.png)


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



---


## Services

![AWS service and resources](Cloud%20Computing/AWS/AWS%20service%20and%20resources.png)


### Free Services:

1. IAM
2. VPC
3. Organizations & Consolidated Billing 
4. AWS Cost Explorer 
5. Auto Scaling
6. CloudFormation
7. Elastic Beanstalk
8. Opswork
9. Amplify
10. AppSync
11. CodeStar

### Business Centric Services
![Pasted image 20220706225126](Cloud%20Computing/Pasted%20image%2020220706225126.png)



## AWS Support Plans
![Pasted image 20220706164829](Cloud%20Computing/Pasted%20image%2020220706164829.png)

## AWS Marketplace
