---
tags: [aws, cloud, networking]
---
# Direct Connect (DX)
#aws #cloud #networking 

AWS Direct Connect is a network service that provides an alternative to using the Internet to utilize [AWS](Cloud%20Computing/AWS/AWS.md) cloud services. AWS Direct Connect enables customers to have low latency, secure and private connections to AWS for workloads which require higher speed or lower latency than the internet.

• Private connectivity between AWS and your data center / office
• Consistent network experience – increased speed/latency & bandwidth/throughput
• Lower costs for organizations that transfer large volumes of data

![](Attachments/Pasted%20image%2020230311213812.png)

## Private VIF (Single VPC)
![](Attachments/Pasted%20image%2020230311214126.png)

## Multiple VIF (Multiple VPC)
![](Attachments/Pasted%20image%2020230311214155.png)

- Speeds from 50Mbps to 500Mbps can also be accessed via an APN partner (uses **hosted VIFs** or **hosted connections**):
	• A **hosted VIF** is a single VIF that is shared with other customers (shared bandwidth)
	• A **hosted connection** is a DX connection with a single VIF dedicated
to you
- <span style="color:red">DX Connections are not encrypted</span>.
- <span style="color:green">Use an IPSec S2S VPN connection over a VIF for encryption</span>.
- Link aggregation groups (**LAG**s) can be used to combine multiple physical connections into a single logical connection using **LACP** – provides improved speed


## DX - Native High Availability

**Redundant DX connections through secundary DX location**
![](Attachments/Pasted%20image%2020230311215049.png)

**Redundant Connection through a VPN**
don't use this setup if bandwidth is above 1GBps.
![](Attachments/Pasted%20image%2020230311215020.png)