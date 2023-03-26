# ECS (Elastic Container Service)
#aws #cloud #containers 

Amazon ECS is a fully managed [Container orchestration](Container%20orchestration) service by [AWS](Cloud%20Computing/AWS/AWS.md) that helps you easily deploy, manage, and scale containerized applications. It deeply integrates with the rest of the AWS platform to provide a secure and easy-to-use solution for running [container](container) workloads in the cloud and now on your infrastructure with Amazon ECS Anywhere.


![Pasted image 20230103141505](Attachments/Pasted%20image%2020230103141505.png)

![](Attachments/Pasted%20image%2020230325234542.png)



## IAM roles

There are two types of [IAM](Cloud%20Computing/AWS/Security%20&%20Identity/IAM.md) Roles assigned to the ECS service. the IAM instance Role will be applied to the node or the ec2 instance which is also applicable to the task running within them, while the task role is something that only the assigned task could use.  So be careful on what you apply to the Instance role as it will also be applicable to the tasks running within them.
![](Attachments/Pasted%20image%2020230326140938.png)



## Scaling
There will be scaling on both the cluster level to scale instances like the [ASG](Cloud%20Computing/AWS/Compute/ASG.md) as well as the services to scale the container tasks. 

**Cluster Auto-scaling**
![](Attachments/Pasted%20image%2020230326141926.png)


**Service Auto-scaling**

There is also another scaling type for the service to create new tasks according to the demand.

![](Attachments/Pasted%20image%2020230326142038.png)



## ECS with ALB
An AWS [ALB](ALB) can be used to balance load within the ECS services.

Since the container service will create a dynamic port exposed the ALB can map them automatically. 

A NAT gateway can also be used to give Internet access to the private subnet serices.


![](Attachments/Pasted%20image%2020230326142129.png)


