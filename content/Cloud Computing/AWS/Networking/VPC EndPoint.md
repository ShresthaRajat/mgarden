# VPC Endpoint
#aws #cloud #networking 

[VPC endpoint](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-endpoints.html) enables creation of a private connection between [VPC](Cloud%20Computing/AWS/Networking/VPC.md) to supported [AWS](Cloud%20Computing/AWS/AWS.md) services and VPC endpoint services powered by PrivateLink using its private IP address. Traffic between VPC and AWS service does not leave the Amazon network.

## Interface Endpoints

[**Interface endpoint**](https://docs.aws.amazon.com/vpc/latest/userguide/vpce-interface.html) is an elastic network interface (ENI) (powered by PrivateLink) with a private IP address from the IP address range of user’s subnet that serves as an entry point for traffic destined to a supported service. It enables you to privately access services by using private IP addresses.

![](Attachments/Pasted%20image%2020230310230842.png)


## Gateway Endpoint

[**Gateway endpoint**](https://docs.aws.amazon.com/vpc/latest/userguide/vpce-gateway.html) is a gateway that you specify as a target for a route in your route table for traffic destined to a supported AWS service. Currently supports [S3](Cloud%20Computing/AWS/Storage/S3.md) and [DynamoDB](Cloud%20Computing/AWS/Databases/DynamoDB.md) services only.

Also see [S3 Gateway Endpoint](Cloud%20Computing/AWS/Storage/S3.md#S3%20Gateway%20Endpoint) on how an [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instance can access a [S3](Cloud%20Computing/AWS/Storage/S3.md) bucket through the private routes. 
 ![](Attachments/Pasted%20image%2020230310230906.png)


## Interface Endpoint vs Gateway Endpoint

![](Attachments/Pasted%20image%2020230310233940.png)