---
tags: [cloud, aws, storage]
---
# Instance Store
#cloud #aws #storage 

Instance Store in [AWS](Cloud%20Computing/AWS/AWS.md) is fundamentally different to [EBS](Cloud%20Computing/AWS/Storage/EBS.md). These stores are in the same server rack as the [EC2](Cloud%20Computing/AWS/Compute/EC2.md) Servers are hosted and are high performance.  These Store are Ephemeral (data are not persisted and will be lost when powered off). These store will have several differences to a normal EBS volume on the:

• Instance stores are ideal for temporary storage of information that changes frequently, such as buffers, caches, or scratch data 

• Instance store volume root devices are created from AMI templates stored on S3 

• Instance store volumes cannot be detached/reattached

## EBS vs Instance Store
![](Attachments/Pasted%20image%2020230308225409.png)
![](Attachments/Pasted%20image%2020230308224841.png)

