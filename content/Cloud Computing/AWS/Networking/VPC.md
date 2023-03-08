# VPC (Virtual Private Cloud)
#aws #cloud #vpc #networking


Amazon Virtual Private Cloud (VPC) is a commercial cloud computing service that provides users a virtual private cloud, by “provisioning a logically isolated section of [AWS](Cloud%20Computing/AWS/AWS.md) Cloud”.

[VPC FAQ](https://aws.amazon.com/vpc/faqs/)

- A VPC is like a digital data centre.
- All VPC traffic can be logged via Flowlogs.
- In an Amazon VPC, an EC2 instance retains it’s private IP address when the instance is stopped.
- A VPC consists of following components:

![Pasted image 20220714145840](Attachments/Pasted%20image%2020220714145840.png)

Key Features and Limitations:

- VPCs are Region Specific and they do not span across regions
- You can create 5 VPCs per region
- Every region comes with a default VPC
- You can have 200 subnets per VPC
- You can use IPv4 CIDR Blocks and in addition to a IPv6 CIDR blocks
- It costs nothing
- Some things like NAT Gateway, VPC Endpoints, VPN Gateway and Customer Gateway are not free
- DNS host names are disabled by default.


## Subnets


## Routing Tables

Main route table is implicitly associated with subnets that haven’t been  explicitly associated with a route table

![](Attachments/Pasted%20image%2020230305153126.png)
![](Attachments/Pasted%20image%2020230305153512.png)

## VPC Peering

VPC peering can be used when a VPC needs to communicate with another VPC over a direct network route using private IP addresses.

VPC Peering is supported across multiple accounts.
VPC peering allows direct network connection via a private ip address. Instances behave as if they were on the same private network.
Peering uses a star Configuration if you were to connect multiple different VPC i.e. a VPC will need to be in the middle of every other VPCs. (No Transitive peering)
The following peering configurations are invalid:

-   Overlapping CIDR blocks
-   Transitive peering
-   Edge to edge routing through a gateway or private connection

[More info on invalid peering configurations](https://docs.aws.amazon.com/AmazonVPC/latest/PeeringGuide/invalid-peering-configurations.html)

VPC peering is only supported in a star configuration.

Transitive peering / edge-to-edge routing is not supported. i.e. if you have VPC A <-> VPC B <-> VPC C, VPC A can communicate with VPC B, and VPC B with C, but A cannot directly communicate with C unless a direct connection is made between A and C.

[More info on VPC peering](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-peering.html)

**You must update both sides of the route tables for VPC peering to work**


## Route Tables
Route tables are used to determine where the network traffic is directed. Each subnet in VPC must be associated with a route table. 
A subnet can only be associated with one route table at a time.
A route table can be used to associate multiple subnets.
Each record in the route table is called a route.

In VPCs, even though we have these different subnets, we need to allow traffic to flow through them. We do this with Route Tables. **A Route Table is just a list of CIDR blocks (IP ranges) that our traffic can leave and come from.** By default, newly created Route Tables will have the CIDR of our VPC defined. This means that traffic from anywhere within our VPC is allowed.

In addition to a list of IP ranges that our Route Table connect traffic between, it also has **Subnet Associations**. Simply put, these are "which subnets use this route table."



## Internet Gateway

Creating a VPC also creates a route table, but doesn’t create a subnet or internet gateway by default.

For a VPC route table point to an internet gateway, you must first attach the internet gateway to the VPC.

**You can attach only one internet gateway to a VPC at a time**; if youre getting an error when trying to attach an Internet Gateway to a VPC, it could be that an Internet Gateway is already attached to the VPC.

Before deleting an IGW, you must first detach it from the VPC it’s attached to.

[More info on VPC Internet Gateways](https://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Internet_Gateway.html)


## Direct Connect

A solution for establishing dedicated network connections from on-premises locations to AWS.

Very fast network with Lower bandwidth of 50M-500M or Higher Bandwidth 1GB or 10GB.

Helps reduce network costs and increase bandwidth throughput
Provides a more consistent network experience than internet based connections. (reliable and secure)

## VPC Endpoints

VPC endpoints allow you to privately connect your VPC to other AWS services, and VPC endpoint services.

Eliminates the need for [#Internet Gateway](#Internet%20Gateway), NAT device, VPN connection or even AWS Direct Connect connections.

Instances in the VPC do not require public IP address to communicate with service resources.

Traffic between your VPC and other services does not leave the AWS network.

Horizontally scaled, redundant, and highly available.

Allows secure communication between instances and services without adding availability risks or bandwidth constraints on your traffic.

![Pasted image 20220715002212](Attachments/Pasted%20image%2020220715002212.png)
### Interface endpoints

![Pasted image 20220715002052](Attachments/Pasted%20image%2020220715002052.png)


### Gateway Endpoint

A gateway endpoint is a target for specific route in your route table. 
Only support [DynamoDB](Cloud%20Computing/AWS/Databases/DynamoDB.md) and [S3](Cloud%20Computing/AWS/Storage/S3.md)

Gateway endpoints are free



## VPC Flow Logs

captures IP traffic information flow of Network Interfaces withhin VPC.
can be created for:
	- VPC
	- Subnets
	- Network Interface

All data is stored in Amazon Cloudwatch logs
Can be viewed in detail in Cloudwatch logs,
Cannot do much than delete it.
Cannot be tagged like other resources
can be delivered to S3 or cloudwatch logs
some instance traffic can not be monitored

![Pasted image 20220715002555](Attachments/Pasted%20image%2020220715002555.png)

![Pasted image 20220715002614](Attachments/Pasted%20image%2020220715002614.png)

## VPC Virtual Private Gateway

An Amazon VPC VPN connection links your data-center (or network) to your Amazon VPC virtual private cloud (VPC). A customer gateway is the anchor on your side of that connection. It can be a physical or software appliance. The anchor on the AWS side of the VPN connection is called a virtual private gateway.

[More info](https://docs.aws.amazon.com/vpc/latest/adminguide/Introduction.html)



### CIDR - Classless Inter-domain Routing


• CIDR block size can be between /16 and /28
• The CIDR block must not overlap with any existing CIDR block
that's associated with the VPC
• You cannot increase or decrease the size of an existing CIDR block
• The first four and last IP address are not available for use

-   10.0.0.0: Network address.
-   10.0.0.1: Reserved by AWS for the VPC router.
-   10.0.0.2: Reserved by AWS for DNS.
-   10.0.0.3: Reserved by AWS for future use.
-   10.0.0.255: Network broadcast address. We do not support broadcast in a VPC, therefore we reserve this address.

Network masks:
![](Attachments/Pasted%20image%2020230305152101.png)
-   /16 - supports up to 65,536 IP addresses. Best for large networks.
-   /24 - supports up to 256 IP addresses. Best for smaller networks.
-   /27 - supports up to 32 IP addresses
-   /28 - supports up to 16 IP addresses
-   /32 - an absolute ip address - matches exactly one

It’s possible to split a CIDR block into two subnets:

-   one subnet can use CIDR block 10.0.0.0/25 (for addresses 10.0.0.0 - 10.0.0.127)
-   and then the other subnet can use the CIDR block 10.0.0.128/ 25 (for addresses 10.0.0.128 - 10.0.0.255)

The allowed CIDR block size in a VPC is between a /16 and /28 netmask.

To enable ping, you need to allow ICMP traffic.

In order to ensure providioned EC2 instances have a public IP address, enable “Auto-Assign Public IP” for the subnet.

0.0.0.0/0 is also known as default 
It represents all possible IP addresses


## Network Access Control List (NACL)

NACLs acts as a virtual firewall at a subnet level.

VPCs automatically get a default NACL
Subnets are associated with NACLs. Subnets can only belong to single NACL.
Each NACL contains a set of rules that can allow or deny traffic in and out of the subnet. 
Stateless
A default NACL denies all traffic 

![Pasted image 20220715002905](Attachments/Pasted%20image%2020220715002905.png)
![Pasted image 20220715002945](Attachments/Pasted%20image%2020220715002945.png)


## Security Groups
A virtual firewall at an instance level.
Security groups are associated with EC2 instances.
Each security Group contains a set of rules that filter traffic coming into in or out of Ec2 instances. 
Multiple Instances across multiple subnets can belong to a Security Group.

There are no deny rules. All inbound traffic are denied as default unless there is a rule specifically allows it. All outbound traffic is allowed by default.

these are stateful
changes take effect immediately.

![Pasted image 20220715003259](Attachments/Pasted%20image%2020220715003259.png)


#### Limits

can have upto 10,000 SGs in a single region. (Default is 2,500)
can have 60 inbound and 60 outbound rules per SG
16 SG per ENI (default is 5)

![Pasted image 20220715003440](Attachments/Pasted%20image%2020220715003440.png)


## Network address translation (NAT)

NAT is a method of remapping one IP address space to another.
In a private network NAT can help gain outbound access to the internet by using a NAT gateway which will remap the Private IPs.

If there are two networks which have conflicting network addresses, NAT can be used to make the addresses more agreeable

### NAT Instances vs NAT Gateways
![Pasted image 20220715003856](Attachments/Pasted%20image%2020220715003856.png)


![Pasted image 20220715004501](Attachments/Pasted%20image%2020220715004501.png)

