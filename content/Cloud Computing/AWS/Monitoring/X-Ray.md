# AWS X-Ray
#aws #cloud #monitoring 

A service from [AWS](Cloud%20Computing/AWS/AWS.md) to visualize the components of your application, identify performance bottlenecks, and troubleshoot requests that resulted in an error which will be handy on debugging serverless application. AWS services send trace data to X-Ray, and X-Ray processes the data to generate a service map and searchable trace summaries like the following.

![](Attachments/Pasted%20image%2020230325012856.png)


• X-Ray can be used with applications running on [EC2](Cloud%20Computing/AWS/Compute/EC2.md), [ECS](Cloud%20Computing/AWS/Compute/ECS.md), [Lambda](Cloud%20Computing/AWS/Compute/Lambda.md), and [Elastic Beanstalk](Elastic%20Beanstalk)
• You must integrate the X-Ray SDK with your application and install the X-Ray agent
• The AWS X-Ray agent is a software application that gathers raw segment data and relays it to the AWS X-Ray service
• The agent works in conjunction with the AWS X-Ray SDKs so that data sent by the SDKs can reach the X-Ray service
• The X-Ray SDK captures metadata for requests made to MySQL and PostgreSQL databases and Amazon [DynamoDB](Cloud%20Computing/AWS/Databases/DynamoDB.md)
• It also captures metadata for requests made to Amazon SQS and Amazon SNS