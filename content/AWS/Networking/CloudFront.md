# CloudFront
#aws #cloud #edge #CDN

A CDN service provided by [AWS](AWS/AWS.md).

A CDN is a distributed network of servers which delivers web pages and contents to users based on their geographical location, the origin of the webpage.

## Core Components

### Origin

The location where the original files are located. eg an S3 Bucket, EC2, 


### Edge location

The location where the the web content will be cached.


## CloudFront Distributions

A Distribution is a collection of Edge locations. You can set the origin eg. EC2, S3, ELB, Route53.

It replicates copies based on your Price class

There are 2 types of Distributions
1. Web (For websites)
2. RTMP (For streaming media)


#### Settings:
Behaveour




## Cloudfront-Lambda@Edge

We use these functions to overrice the behaviour of request and responces
![Pasted image 20220723225149](AWS/--%20Networking%20--/Pasted%20image%2020220723225149.png)

 A common use case will be using it to authenticate users before they can access secured web content which needs to be authorised via cognito or similar case

## CloudFront-Protection

By default a Distribution allows everyone to have access

### Original Identity Access (OAI)
A virtual user identity that will be users to give your CloudFront Distribution permission to fetch a private object

In order to use Signed URLs or Signed Cookies you need to have an OAI

#### Signed URLs 



![Pasted image 20220723230258](AWS/--%20Networking%20--/Pasted%20image%2020220723230258.png)