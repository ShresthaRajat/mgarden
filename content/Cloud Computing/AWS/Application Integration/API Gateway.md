---
tags: [aws, cloud, api]
---
# Amazon API Gateway
#aws #cloud #api

Amazon API Gateway is a fully managed service in [AWS](Cloud%20Computing/AWS/AWS.md) that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. An API gateway is an intermediary that sits between your backend services and your clients. An example of a client might be the front-end of your application in the form of a web page, internal services that need to interact with your application, or third-party client websites.

![](Attachments/Pasted%20image%2020230325222053.png)


![](Attachments/Pasted%20image%2020230325222119.png)


![](Attachments/Pasted%20image%2020230325222150.png)


## Integration
An API gateway can be implemented with:

• For a [Lambda](Cloud%20Computing/AWS/Compute/Lambda.md) function, you can have the Lambda proxy integration, or the Lambda custom integration
• For an HTTP endpoint, you can have the HTTP proxy integration or the HTTP custom integration
• For an AWS service action, you have the AWS integration of the non-proxy type only

## Caching

- You can add caching to API calls by provisioning an Amazon API Gateway cache and specifying its size in gigabytes
- Caching allows you to cache the endpoint's response
- Caching can reduce number of calls to the backend and improve latency of requests to the API
![](Attachments/Pasted%20image%2020230325222626.png)


## Throttling
![](Attachments/Pasted%20image%2020230325222702.png)


## Usage Plans and API Keys


![](Attachments/Pasted%20image%2020230325222735.png)