---
tags: [aws, cloud, Iam, Identity]
---
# Identity Federation
#aws #cloud #Iam #Identity 

## Identity Federation Services
In [AWS](Cloud%20Computing/AWS/AWS.md) we can utilize [IAM](Cloud%20Computing/AWS/Security%20&%20Identity/IAM.md), AWS [IAM Identity Center](Cloud%20Computing/AWS/Security%20&%20Identity/IAM%20Identity%20Center.md), and [Cognito](Cloud%20Computing/AWS/Security%20&%20Identity/Cognito.md) to create identities and manage roles and permissions by these services.


Note: AWS SSO is now known as IAM Identity Center

![](Attachments/Pasted%20image%2020230306225306.png)


## Onsite IdP with AWS

we can setup an[[ IdP]] setup on an On premise setup to sign into aws console using the assume role after the authorization is completed in the Onsite IdP.

![](Attachments/Pasted%20image%2020230306225854.png)


## IdP Implementation
Similarly IdPs can also be done through other [Active Directory](Cyber%20Security/Cloud%20Security/Active%20Directory.md) service or other social providers. Amazon strongly suggests to use [Cognito](Cloud%20Computing/AWS/Security%20&%20Identity/Cognito.md)
for this though. This is further explored on AWS [IAM Identity Center](Cloud%20Computing/AWS/Security%20&%20Identity/IAM%20Identity%20Center.md).
![](Attachments/Pasted%20image%2020230306230439.png)