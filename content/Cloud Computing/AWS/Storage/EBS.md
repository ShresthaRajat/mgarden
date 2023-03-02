# EBS
#cloud #aws #storage

A device access block storage solution by [AWS](Cloud%20Computing/AWS/AWS.md). 

Highly available and durable solution for attaching persistent block storage volumes to an [Elastic Compute Cloud EC2](Cloud%20Computing/AWS/Compute/Elastic%20Compute%20Cloud%20EC2.md) instance. Volumes are automatically replicated within their Availability Zone (AZ) to protect from component failure.
![Pasted image 20220723215556](Cloud%20Computing/AWS/Storage/Pasted%20image%2020220723215556.png)
![Pasted image 20220723215541](Cloud%20Computing/AWS/Storage/Pasted%20image%2020220723215541.png)

## Moving Volumes

### From one AZ to another
1. Take a snapshot
2. create an AMI from the snapshot 
3. launch an EC2 instance


### From one Region to another
1. Take a snapshot
2. create an AMI from the snapshot 
3. Copy the AMI from one region to another
4. launch an EC2 instance

## EBS - Encrypted Root Volume
You can enable encrypto
![Pasted image 20220723224133](Cloud%20Computing/AWS/Storage/Pasted%20image%2020220723224133.png)



## EBS vs Instance Store Volumes
![Pasted image 20220723224353](Cloud%20Computing/AWS/Storage/Pasted%20image%2020220723224353.png)



![Pasted image 20220723224449](Cloud%20Computing/AWS/Storage/Pasted%20image%2020220723224449.png)