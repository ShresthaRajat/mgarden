# CloudFront
#aws #cloud #edge #CDN

A CDN service provided by [AWS](Cloud%20Computing/AWS/AWS.md). 

A CDN is a distributed network of servers which delivers web pages and contents to users based on their geographical location, the origin of the webpage.

![](Attachments/Pasted%20image%2020230305151823.png)

## Core Components

![](Attachments/Pasted%20image%2020230312212212.png)

### Origin
The location where the original files are located. eg an [S3](Cloud%20Computing/AWS/Storage/S3.md) Bucket, [EC2](Cloud%20Computing/AWS/Compute/EC2.md), [ELB](Cloud%20Computing/AWS/Compute/ELB.md), etc.

### Edge location
The location where the the web content will be cached. 

### CloudFront Distributions

A Distribution is a collection of Edge locations. You can set the origin eg. EC2, S3, ELB, Route53. It will have one or more Origins

- Speed up distribution of static and dynamic content, for example, .html, .css, .php, and graphics files. Distribute media files using HTTP or HTTPS. Add, update, or delete objects, and submit data from web forms and also for live streaming to stream an event in real time.
- It replicates copies based on your Price class

There are 2 types of Distributions
1. Web (For websites)
2. RTMP (For streaming media)
![](Attachments/Pasted%20image%2020230312212418.png)


## Mechanism and Behaviours

**Regional Edge Cache** sits between [Edge location](#Edge%20location) and [Origin](#Origin). They are limited in number (12) and has a higher cache bandwidth.

• You can define a maximum Time To Live (TTL) and a default TTL
• TTL is defined at the behavior level
• This can be used to define different TTLs for different file types (e.g. png vs jpg)
• After expiration, CloudFront checks the origin for any new requests (check the file is the latest version) 
• Headers can be used to control the cache:
	• *Cache-Control max-age=(seconds)* - specify how long before CloudFront gets the object again from the origin server
	• *Expires* – specify an expiration date and time

A typical caching setup will look like:
![](Attachments/Pasted%20image%2020230312212643.png)

A typical traffic from users accessing an imge will look like:
![](Attachments/Pasted%20image%2020230312213047.png)

### Path Pattern

You can configure Cloudfront to get different files from different origins.
![](Attachments/Pasted%20image%2020230312213320.png)

### Request Headers:
• You can configure CloudFront to forward headers in the viewer request to the origin
• CloudFront can then cache multiple versions of an object based on the values in one or more request headers
• Controlled in a behavior to do one of the following:
	• Forward all headers to your origin (objects are not cached)
	• Forward a whitelist of headers that you specify
	• Forward only the default headers (doesn’t cache objects based on values in request headers)


## Lambda@Edge

We use these functions to override the behaviour of request and responces
![Pasted image 20220723225149](Attachments/Pasted%20image%2020220723225149.png)

 A common use case will be using it to authenticate users before they can access secured web content which needs to be authorised via cognito or similar case

• Run Node.js and Python Lambda functions to customize the content CloudFront delivers
• Executes functions closer to the viewer
• Can be run at the following points
• After CloudFront receives a request from a viewer (viewer request)
• Before CloudFront forwards the request to the origin (origin request)
• After CloudFront receives the response from the origin (origin response)
• Before CloudFront forwards the response to the viewer (viewer response)


## CloudFront-Protection
By default a Distribution allows everyone to have access.

### Signed URLs
  

The signed URL **allows the user to download or stream the content**. This step is automatic; the user usually doesn't have to do anything additional to access the content. For example, if a user is accessing your content in a web browser, your application returns the signed URL to the browser. Also see [S3 Presigned URLs](Cloud%20Computing/AWS/Storage/S3.md#S3%20Presigned%20URLs) which gives user temporary access to a file in the bucket.

In order to use Signed URLs or Signed Cookies you need to have an [Original Identity Access (OAI)](#Original%20Identity%20Access%20(OAI)).
To controll the access of content by users 

![](Attachments/Pasted%20image%2020230312213555.png)

### Signed Cookies
• Similar to Signed URLs
• Use signed cookies when you don’t want to change URLs
• Can also be used when you want to provide access to multiple restricted files (Signed URLs are for individual files)


### Original Identity Access (OAI)
A virtual user identity that will be users to give your CloudFront Distribution permission to fetch a private object.

![](Attachments/Pasted%20image%2020230312214745.png)


## Cloudfront SSL/TLS

#TODO 
- [ ] Write this
![](Attachments/Pasted%20image%2020230312220625.png)

#TODO 
- [ ] Write this
## Cloudfront SNI

![](Attachments/Pasted%20image%2020230312220733.png)