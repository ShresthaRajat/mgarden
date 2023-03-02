# Elastic Load balancer (ELB)
#aws #cloud #vpc #networking #loadbalancer

Loadbalancer service provided by [AWS](AWS/AWS.md)

Elastic Load Balancing supports the following types of load balancers: **Application Load Balancers, Network Load Balancers, and Classic Load Balancers**.

## Common Features

Let’s start by taking a look at what is common for all three types of load balancers. 

Obviously, all AWS load balancers distribute incoming requests to a number of targets, which can be either EC2 instances or Docker containers. They all implement health checks, which are used to detect unhealthy instances. They are all highly available and elastic (in AWS parlance: They scale up and down within a few minutes according to workload). 

TLS termination is a feature available for all three as well, and they can all be either internet-facing or internal. Finally, ELB, ALB, and NLB all export useful metrics to CloudWatch and can log pertinent information to CloudWatch Logs.

![Pasted image 20220723213315](AWS/--%20Compute%20--/Pasted%20image%2020220723213315.png)


# Classic Load Balancer (CLB)

Widely known as CLB it was the original Elastic Load Balancer, as this was its name when it was first introduced in 2009 and was the only type of load balancer available. It can be thought of as an Nginx or HAProxy instance if that makes it easier for you to understand.

ELB works at both layer 4 (TCP) and 7 (HTTP) but not on the same time. It is the only load balancer that works in EC2-Classic, in case you have a very old AWS account. Also, it’s the only load balancer that supports application-defined sticky session cookies; in contrast, ALB uses its own cookies, and you have no control over that.

At layer 7, ELB can terminate TLS traffic. It can also re-encrypt the traffic to the targets as long as they provide an SSL certificate (a self-signed certificate is fine, BTW). This provides end-to-end encryption, which is a usual requirement in many compliance programs. Optionally, ELB can be configured to verify the TLS certificate provided by the target for extra security.

ELB has quite a few limitations. For example, it isn’t compatible with EKS containers running on Fargate. Also, it can’t forward traffic on more than one port per instance, and it doesn’t support forwarding to IP addresses—it can only forward to explicit EC2 instances or containers in ECS or EKS. Finally, ELB doesn’t support websockets; however, you may be able to work around this limitation by using layer 4.

To run an ELB in the us-east-1 region, it will cost you $0.025 per ELB-hour + $0.008 per GB of traffic.

AWS discourages the use of ELB in favor of its newer load balancers. Admittedly, there are very few scenarios where the use of an ELB would be preferable; typically, these are cases where you simply don’t have a choice. For example, your workload might still run on [EC2-Classic](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-classic-platform.html), or you need the load balancer to use your own sticky session cookies, in which cases ELB would be the only option available to you.



## Application Load Balancer (ALB)

It works only on layer 7 (HTTP) of the [OSI](OSI). It has a wide range of routing rules for incoming requests based on host name, path, query string parameter, HTTP method, HTTP headers, source IP, or port number. In contrast, ELB only allows routing based on port number. Also, contrary to ELB, ALB can route requests to many ports on a single target. Plus, ALB can route requests to Lambda functions.

It has a feature called Request Routing which allows you to add routing rules to your application.

A very useful feature of ALB is that it can be configured to return a fixed response or a redirection. So you don’t need a server to perform such basic tasks because it is all embedded in the ALB itself. Also very importantly, ALB supports HTTP/2 and websockets.

ALB further supports [Server Name Indication (SNI)](https://www.cloudflare.com/learning/ssl/what-is-sni/), which allows it to serve many domain names. (In contrast, ELB can serve only one domain name). There is a limit, however, to the number of certificates you can attach to an ALB, [namely 25 certificates](https://aws.amazon.com/blogs/aws/new-application-load-balancer-sni/) plus the default certificate.

An interesting feature of ALB is that it supports user authentication via a variety of methods, including OIDC, SAML, LDAP, Microsoft AD, and well-known social identity providers such as Facebook and Google. This can help you off-load the user authentication part of your application to the load balancer. 

ALB pricing is a bit more complicated than ELB. For the us-east-1 region, it would cost you $0.0225 per ALB + $0.008 per LCU-hour. The definition of an LCU can be found [here](https://aws.amazon.com/elasticloadbalancing/pricing/). All in all, pricing is roughly equivalent to ELB.

ALBs are typically used for web applications. If you have a microservices architecture, ALB can be used as an internal load balancer in front of EC2 instances or Docker containers that implement a given service. You can also use them in front of an application implementing a REST API, although [AWS API Gateway](https://aws.amazon.com/api-gateway/) would generally be a better choice here.

## Network Load Balancer

NLB works on the layer 4 of the [OSI model](OSI%20model) only and can handle both TCP and UDP, as well as TCP connections encrypted with TLS. Its main feature is that it has a very high performance. Also, it uses static IP addresses and can be assigned Elastic IPs—not possible with ALB and ELB.

NLB natively preserves the source IP address in TCP/UDP packets; in contrast, ALB and ELB can be configured to add additional HTTP headers with forwarding information, and those have to be parsed properly by your application.

NLB pricing for the us-east-1 region is $0.0225 per NLB-hour + $0.006 per LCU-hour. The definition of an LCU for NLB is quite similar to that for ALB, and more information can be found [here](https://aws.amazon.com/elasticloadbalancing/pricing/). All in all, pricing is roughly equivalent to ELB and ALB.

NLBs would be used for anything that ALBs don’t cover. A typical use case would be a near real-time data streaming service (video, stock quotes, etc.) Another typical case is that you would need to use an NLB if your application uses non-HTTP protocols.

## Sticky Session

A method to bind a user's session to a specific EC2 session.
can only be applied to CLB or ALBs

It ensures that all requests from that session are sent to the same instance. It is Typically utilized with a Classic Load Balancer

## X-Forwarded-For (XFF) Header

If you need the IPv4 address of a user, check this header.

This header is a common method for identifying the originating IP addresses of clients connecting to a web server through an HTTP proxy or a load balancer.

![Pasted image 20220723214311](AWS/--%20Compute%20--/Pasted%20image%2020220723214311.png)

## ELB - Health Checks

![Pasted image 20220723214425](AWS/--%20Compute%20--/Pasted%20image%2020220723214425.png)


## Cross-Zone Load Balancing
![Pasted image 20220723214447](AWS/--%20Compute%20--/Pasted%20image%2020220723214447.png)


## ALB - Request Routing

Apply riles to incomming request and then forward or redirect traffic

- Host header
- HTTP header
- Source IP
- HTTP header method
- Path
- Query string
![Pasted image 20220723214622](AWS/--%20Compute%20--/Pasted%20image%2020220723214622.png)



![Pasted image 20220723214636](AWS/--%20Compute%20--/Pasted%20image%2020220723214636.png)