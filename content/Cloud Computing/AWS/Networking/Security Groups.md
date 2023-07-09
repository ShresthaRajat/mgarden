---
tags: [aws, cloud, networking]
---
# Security Groups
#aws #cloud #networking 


An [AWS](Cloud%20Computing/AWS/AWS.md) stateful firewall service that controls the traffic that is allowed to reach and leave the resources that it is associated with in an instance level.

When you create a VPC, it comes with a default security group. You can create additional security groups for each VPC. You can associate a security group only with resources in the VPC for which it is created.

For each security group, you add _rules_ that control the traffic based on protocols and port numbers. There are separate sets of rules for inbound traffic and outbound traffic.

[Defence In Depth](Cyber%20Security/Cloud%20Security/Defence%20In%20Depth.md)
[Zero-Trust](Cyber%20Security/Cloud%20Security/Zero-Trust.md)

Security group can be applied to aws resources within a VPC such as:
[EC2](Cloud%20Computing/AWS/Compute/EC2.md)
[RDS](Cloud%20Computing/AWS/Databases/RDS.md)
[ELB](Cloud%20Computing/AWS/Compute/ELB.md)

![](Attachments/Pasted%20image%2020230305173953.png)