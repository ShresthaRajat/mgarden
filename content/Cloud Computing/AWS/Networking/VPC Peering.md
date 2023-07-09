---
tags: [aws, cloud, networking]
title: VPC Peering
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# VPC Peering
#aws #cloud #networking 


It allows internal connection between [VPC](Cloud%20Computing/AWS/Networking/VPC.md)s in [AWS](Cloud%20Computing/AWS/AWS.md) Using the [AWS Global infrastructure](Cloud%20Computing/AWS/Networking/AWS%20Global%20infrastructure.md). 

![](Attachments/Pasted%20image%2020230305195912.png)


## Demo:

To create a simple VPC peering connection between two accounts, make two VPC with different root CIDRs (so that the IPs do not collide). Then peer it and you can access the instances in one VPC from another.


### Steps:

1. Create two different VPCs with different CIDR blocks.
2. Create a VPC peering request from one VPC to another
3. Accept the VPC peering connection
4. Configure the route table to accept the root CIDRs of each VPC  by setting the opposite VPC CIDR block as destination and VPC peering interface as Target. (Do on both ends)
5. Now you can access the resources on the opposite VPC.
![](Attachments/Pasted%20image%2020230310225715.png)