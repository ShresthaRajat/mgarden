# Network Firewall
#aws #cloud #security 

A new feature in [AWS](Cloud%20Computing/AWS/AWS.md) for [VPC](Cloud%20Computing/AWS/Networking/VPC.md) network protection.  It Includes Stateful & Stateless firewall, Intrusion Prevention System ([IPS](IPS)), and Web filtering. It works with AWS Network Firewall manager for centrally applying policies across VPCs / accounts and uses a VPC endpoint and Gateway Load Balancer.

However they do not deploy resources in the firewall subnet and for High availability we must allocate a subnet per AZ.

![](Attachments/Pasted%20image%2020230322012156.png)