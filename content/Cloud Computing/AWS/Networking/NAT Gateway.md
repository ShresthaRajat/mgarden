# NAT Gateway
#aws #cloud #networking 

A NAT gateway is [AWS](Cloud%20Computing/AWS/AWS.md) managed service which will utilize Network Address Translation (NAT) service. You can use a NAT gateway so that instances in a private subnet can connect to services outside your VPC but external services cannot initiate a connection with those instances.

![](Attachments/Pasted%20image%2020230305183330.png)


## NAT Instance

A customer managed NAT service that can be used instead of a NAT gateway as well as a Bastion host to connect to an instance as well as provide the instance in the private subnet an access to the internet.
![](Attachments/Pasted%20image%2020230305183351.png)



## NAT Instance vs NAT Gateway
![](Attachments/Pasted%20image%2020230305183427.png)