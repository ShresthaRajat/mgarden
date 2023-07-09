---
tags: [aws, cloud, storage, nfs]
title: Elastic File Store (EFS)
aliases: [Elastic File Store (EFS)]
linter-yaml-title-alias: Elastic File Store (EFS)
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# Elastic File Store (EFS)
#aws #cloud #storage #nfs

A scalable, Elastic Cloud-native NFS file System offered by [AWS](Cloud%20Computing/AWS/AWS.md). Acts as a single drive which could be utilized by multiple [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instances. EFS is using Network File System version 4 (NFSv4) protocol. It is basically a [NAS](Networking/NAS.md) server on AWS which integrates well with aws managed services and is commonly pared with [EC2](Cloud%20Computing/AWS/Compute/EC2.md) Instances to stare and share files between them. 

- Based on Linux NFS
- Could be pared to instances in other region using VPC peering.
- It is not supported on windows as it is based on NFS.
- Is joined to instances through mount targets on each AZ.



![](Attachments/Pasted%20image%2020230308232301.png)


**Example of a setup using EFS**
![](Attachments/Pasted%20image%2020230308232704.png)
The EFS is used to store 







## EFS 
EFS create multiple mount targets to mount to various AZs

It can expand elastically just like an S3.
