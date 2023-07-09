---
tags: [cloud, aws, networking]
title: AWS Site-to-Site VPN
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# AWS Site-to-Site VPN
#cloud #aws #networking 


You can use and AWS an managed IPSec [VPN](VPN) From [AWS](Cloud%20Computing/AWS/AWS.md). It supports a static routes for BGP peering, a Customer Gateway will be used to connect customer site to a VPC uisng an VGW.


**VGW** is deployed with an AWS VPN (which is an managed IPSec Service). Then the VPN connection supports static routes/ BGP peering. The route tables in subnets are also pointed towards the VGW to make this setup work.

Also used as a backup connection to a Direct Connect [DX](Cloud%20Computing/AWS/Networking/DX.md) 

![](Attachments/Pasted%20image%2020230311181627.png)


![](Attachments/Pasted%20image%2020230311212527.png)

![](Attachments/Pasted%20image%2020230311182956.png)