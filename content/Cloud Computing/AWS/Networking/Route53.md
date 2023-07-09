---
tags: [aws, cloud, dns, networking]
---
# Route53
#aws #cloud #dns #networking 

A DNS solution by [AWS](Cloud%20Computing/AWS/AWS.md).
Route53 is a [DNS](Networking/DNS.md) similar to Godaddy or Namecheap.

• You can migrate from another DNS provider and can import records
• You can migrate a hosted zone to another AWS account
• You can migrate from Route 53 to another registrar
• You can also associate a Route 53 hosted zone with a VPC in another account to Authorize association with VPC in the second account. or  Create an association in the second account

For example:
![Pasted image 20220719161710](Attachments/Pasted%20image%2020220719161710.png)


## Public Hosted Zones
Route53 can create [DNS](Networking/DNS.md) records for domains that the public can access through the internet. Like if you have a domain `example.com` registered in your account that you want to point to a s3 bucket, you can create a a record in the zone to point it to the resources so the world can access it.

![](Attachments/Pasted%20image%2020230312203334.png)

## Private Hosted Zones
However you can use any domain you like within the account which the public cannot access. This can be used to create easy to remember domains for your aws resources. ie. you can create a `dev.local` zone in route 53 and point subdomains `database.dev.local` to a database, `elb.dev.local` to an elb etc. Basically you can customize dns names for resources within AWS [VPC](Cloud%20Computing/AWS/Networking/VPC.md). 
![](Attachments/Pasted%20image%2020230312203619.png)



## Record Sets:

We create the customs domains using Record sets.

## Alias Record
AWS has its own special alias Record which extends DNS Functionality. It will route AWS resources easily.

## Routing Policies
There are 7 different types of Routing policies:
![Pasted image 20220720094427](Attachments/Pasted%20image%2020220720094427.png)


### 1. Simple Routing Policy
Its the most basic routing policy in Route53
It is also the default Routing policy
1 record and provide multiple IP addresses.
When multiple values are specified the Route53 will return all

This is the default routing policy. Use this only when you have exactly one resource such as one EC2 web server. This policy can contain multiple values but it returns one resource. This policy is not recommend for production sites.

![Pasted image 20220720094522](Attachments/Pasted%20image%2020220720094522.png)
![](Attachments/Pasted%20image%2020230312205630.png)

### 2. Weighted
This routing policy lets you split up traffic based on different 'weights' assigned to the routes allowing user to send a certain percentage of overall traffic apart from that directed to a different server.
It’s based on a numer2ical value ranging from 0 to 255. If you specify a value of 0 for all regions then it’s routed equally.

![Pasted image 20220720101226](Attachments/Pasted%20image%2020220720101226.png)
![Pasted image 20220720101237](Attachments/Pasted%20image%2020220720101237.png)
![](Attachments/Pasted%20image%2020230312205644.png)


### 3. Latency
When you have multiple resources in multiple regions, this policy routes the user not to the closest resource necessarily but the resource who responds the fastest or lowest latency.
![Pasted image 20220720101348](Attachments/Pasted%20image%2020220720101348.png)

![Pasted image 20220720101321](Attachments/Pasted%20image%2020220720101321.png)
![](Attachments/Pasted%20image%2020230312205658.png)


### 4. Failover
Allows creating two records for the same name. This starts like simple policy but with a health check. If that single web server is unhealthy then you can point elsewhere. That next pointer can be another web server or possibly an error.html page hosted in AWS S3.
![Pasted image 20220720101408](Attachments/Pasted%20image%2020220720101408.png)
![Pasted image 20220720101903](Attachments/Pasted%20image%2020220720101903.png)
![](Attachments/Pasted%20image%2020230312205852.png)


### 5. Geolocation
Use this when you want to serve your site based on the location of the client or user. ie. different servers for different users from regions. Like how all users from North American subcontinent to servers in one american servers and traffic from Asia to one of the servers in Asia.
![Pasted image 20220720101949](Attachments/Pasted%20image%2020220720101949.png)
![Pasted image 20220720094744](Attachments/Pasted%20image%2020220720094744.png)
![](Attachments/Pasted%20image%2020230312205905.png)


### 6. Geoproximity
Geoproximity routing lets Amazon Route 53 route traffic to your resources based on the geographic location of your users and your resources. You can also optionally choose to route more traffic or less to a given resource by specifying a value, known as a _bias_. A bias expands or shrinks the size of the geographic region from which traffic is routed to a resource.

The effect of changing the bias for your resources depends on a number of factors, including the following:

-   The number of resources that you have.
    
-   How close the resources are to one another.
    
-   The number of users that you have near the border area between geographic regions. For example, suppose you have resources in the AWS Regions US East (Northern Virginia) and US West (Oregon) and you have a lot of users in Dallas, Austin, and San Antonio, Texas, USA. Those cities are roughly equidistant between your resources, so a small change in bias could result in a large swing in traffic from resources in one AWS Region to the other.

![Pasted image 20220720094814](Attachments/Pasted%20image%2020220720094814.png)

![Pasted image 20220720094827](Attachments/Pasted%20image%2020220720094827.png)
![Pasted image 20220720094850](Attachments/Pasted%20image%2020220720094850.png)



### 7. Multivalue
This one lets your return multiple values for each of your resources. The client or user browser randomly chooses one. Optionally you can add health checks. If any value becomes unhealthy then the client chooses another value to resolve. This is not an alternative solution to load balancing, it’s an enhancement. This is similar to the [#1 Simple Routing Policy](#1%20Simple%20Routing%20Policy) routing except .

![Pasted image 20220720102628](Attachments/Pasted%20image%2020220720102628.png)
![](Attachments/Pasted%20image%2020230312210004.png)


## Health Checks

Checks health every 30s by default. Can be reduced to every 10s.
A health check can initiate a failover if the status is returned to unhealthy.
A CloudWatch Alarm can be created to alert you about the health of the route.
Health check can monitor other health checks to create a chain of reactions.
Can create up to 50 health checks for AWS endpoints that are within or linked to the same AWS Account.


## Traffic Flow:
A visual editor which lets you create routing configurations for your resources using existing routing types.


## Route 53 Resolver

Amazon Route 53 Resolver responds recursively to DNS queries from AWS resources for public records, Amazon VPC-specific DNS names, and Amazon Route 53 private hosted zones, and is available by default in all VPCs.

A Route 53 Resolver forwarding rule is configured to forward queries to internal.example.com in the on-premises data center. The query is forwarded to an outbound endpoint. The outbound endpoint forwards the query to the on-premises DNS resolver through a private connection between AWS and the data center.

**Outbound Endpoints**
![](Attachments/Pasted%20image%2020230312212050.png)

**Inbound Endpoints**
![](Attachments/Pasted%20image%2020230312212116.png)