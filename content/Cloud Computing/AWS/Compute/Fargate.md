# Fargate
#aws 

A fully managed serverless, pay-as-you-go compute engine for [Containers](Microservice%20Architecture/Docker/Containers.md) that lets you focus on building applications without managing servers in [AWS](Cloud%20Computing/AWS/AWS.md) . AWS Fargate is compatible with both [ECS](Cloud%20Computing/AWS/Compute/ECS.md) and [EKS](Cloud%20Computing/AWS/Compute/EKS.md). 



## IAM role

Fargate has a different approach to assigning the roles, it is simpler because AWS manages the host instance that the Fargate task runs on. So unlike [IAM roles](Cloud%20Computing/AWS/Compute/ECS.md#IAM%20roles) it does not require a Instance role

![](Attachments/Pasted%20image%2020230326141223.png)