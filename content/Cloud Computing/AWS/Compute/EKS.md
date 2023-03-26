# EKS (Elastic Kubernetes Service)
#aws #cloud #Kubernetes #managed-kubernetes-cluster 

Amazon EKS is a managed [Kubernetes](Microservice%20Architecture/Kubernetes/Kubernetes.md) service to run Kubernetes in the [AWS](Cloud%20Computing/AWS/AWS.md) cloud and on-premises data centers. In the cloud, Amazon EKS automatically manages the availability and scalability of the Kubernetes control plane nodes responsible for scheduling containers, managing application availability, storing cluster data, and other key tasks. With Amazon EKS, you can take advantage of all the performance, scale, reliability, and availability of AWS infrastructure, as well as integrations with AWS networking and security services. On-premises, EKS provides a consistent, fully-supported Kubernetes solution with integrated tooling and simple deployment to AWS [Outposts](Outposts), virtual machines, or bare metal servers. 

![](Attachments/Pasted%20image%2020230326144454.png)

Basically AKS is to extend the functionality of orchestrating containers across different cloud service providers easily.


# Auto Scaling
A little different approach to [Scaling](Cloud%20Computing/AWS/Compute/ECS.md#Scaling), Since The kubernetes will handle the service level scaling, EKS can handle the node level scaling with either **Vertical** or **Horizontal** scaling practices. 


# Load Balancer
EKS supports both [Application Load Balancer (ALB)](Cloud%20Computing/AWS/Compute/ELB.md#Application%20Load%20Balancer%20(ALB)) as well as [Network Load Balancer](Cloud%20Computing/AWS/Compute/ELB.md#Network%20Load%20Balancer) 

![](Attachments/Pasted%20image%2020230326145214.png)


## EKS Distro
A distribution of Kubernetes with same dependencies as Amazon EKS. You can use this to create EKS cluster on.




## ECS and EKS Anywhere

Run [ECS](Cloud%20Computing/AWS/Compute/ECS.md) or [EKS](Cloud%20Computing/AWS/Compute/EKS.md) on Customer-managed infrastructure.