# Elastic Network Interface (ENI)
#aws #cloud #compute #networking 

A basic network interface functionality provided by [AWS](Cloud%20Computing/AWS/AWS.md) to be attached to [EC2](Cloud%20Computing/AWS/Compute/EC2.md).

- Additional ENIs can be attached from subnets within the same AZ
- The primary network interface has a private IP and optionally a public IP
- You cannot attach ENIs from subnets in different AZs
- We can attach many ENIs to a singe instances.
- We can transferr the ENI from one instance to another in the same availability zone.



## Other Network interfaces

### Elastic Network Adapter (ENA)
High networking performance used for higher bandwidth.

### Elastic Fabric Adapter (EFA)
For high performance Computing ([HPC](HPC)) instances with tightly coupled application/instances.

## Their Differences

![](Attachments/Pasted%20image%2020230305204234.png)



## Types of IPs

![](Attachments/Pasted%20image%2020230305210806.png)
![](Attachments/Pasted%20image%2020230305210821.png)
