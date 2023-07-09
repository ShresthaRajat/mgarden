---
tags: [aws, cloud, security]
title: DNS Firewall
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# DNS Firewall
#aws #cloud #security 

it is a service by [AWS](Cloud%20Computing/AWS/AWS.md) for extending the function of[Route53](Cloud%20Computing/AWS/Networking/Route53.md) to perform a sort of Resolver [DNS](Networking/DNS.md) Firewall provides protection for outbound DNS requests from your [VPC](Cloud%20Computing/AWS/Networking/VPC.md)s. It is used for

• Filter and regulate outbound DNS traffic for VPCs
• Requests route through Route 53 Resolver for DNS
• Helps prevent DNS exfiltration of data
• Monitor and control the domains applications can query
• Can use AWS Firewall Manager to centrally configure and manage DNS Firewall
• Central management can span VPCs and accounts in [AWS Organization](Cloud%20Computing/AWS/Organizations/AWS%20Organization.md)