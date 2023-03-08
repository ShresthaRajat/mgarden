# Elastic Block Storage (EBS)
#cloud #aws #storage

A device access block storage solution by [AWS](Cloud%20Computing/AWS/AWS.md). 

Highly available and durable solution for attaching persistent block storage volumes to an [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instance. Volumes are automatically replicated within their Availability Zone (AZ) to protect from component failure. Currently most types of EBS do not store multi-attach (Except io1 Provisioned IPOS volume on Nitro based systems). 

![](Attachments/Pasted%20image%2020230308222652.png)

**EBS multi-Attach**
You can use a provisioned IOPS io1 volume that could be accessed by Nitro system based [EC2](Cloud%20Computing/AWS/Compute/EC2.md) upto 16 instances.
![](Attachments/Pasted%20image%2020230308222725.png)


## EBS Volume Types

**1. SSD-Backed Volumes**
![](Attachments/Pasted%20image%2020230308223145.png)

**2. HDD-Backed Volumes**
![](Attachments/Pasted%20image%2020230308223353.png)

**Summary:**
![Pasted image 20220723215556](Attachments/Pasted%20image%2020220723215556.png)
![Pasted image 20220723215541](Attachments/Pasted%20image%2020220723215541.png)

## Moving EBS Volumes and Operations

### From one AZ to another
1. Take a snapshot
2. create an AMI from the snapshot 
3. launch an EC2 instance


### From one Region to another
1. Take a snapshot
2. create an AMI from the snapshot 
3. Copy the AMI from one region to another
4. launch an EC2 instance

### EBS - Encrypted Root Volume
You can enable [Encryption](Cyber%20Security/Encryption.md) on the root volume
![Pasted image 20220723224133](Attachments/Pasted%20image%2020220723224133.png)

### EBS Operations Summary
A EBS volume could be recreated through a snapshot. An [Snapshot](Snapshot) is alco created while you create a [AMI](Cloud%20Computing/AWS/Compute/AMI.md). You can also create a AMI from a snapshot. It is discussed in detail on the slides.

![](Attachments/Pasted%20image%2020230308224012.png)

**Snapshot Operations** 
![](Attachments/Pasted%20image%2020230308224018.png)
![](Attachments/Pasted%20image%2020230308224039.png)


## Cheatsheets:
![Pasted image 20220723224449](Attachments/Pasted%20image%2020220723224449.png)
