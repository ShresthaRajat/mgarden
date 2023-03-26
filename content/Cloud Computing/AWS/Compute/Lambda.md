# Lambda
#aws #cloud #serverless #compute #development 


Run code without provisioning or managing servers in [AWS](Cloud%20Computing/AWS/AWS.md). Lambda executes your code only when needed and scales automatically to a few to a 1000 lambda functions concurrently in seconds. Pay only for the times the lambda function is invoked. Lambda is **Cheap**, **Serverless**, and **Scales Automatically**. Lambda can also be integrated into a [VPC](Cloud%20Computing/AWS/Networking/VPC.md) for a private subnet. 

7 runtime languages are supported:

1. Ruby
2. Python
3. Java
4. Go
5. Powershell
6. Nodejs
7. C#


## Use Cases:
Lambda is used to glue different services together so the use cases are endless.
Example of use cases are:
1. Processing Thumbnails
![Pasted image 20220724095845](Attachments/Pasted%20image%2020220724095845.png)
2. Contact Email Form
![Pasted image 20220724095857](Attachments/Pasted%20image%2020220724095857.png)


## Triggers/Invocations
To invoke a lambda it can be accomplished via the AWS SDK or from other AWS Services. It can also be configured with 3rd party partner sources. There are 3 types of invocations, they are:

**Synchronous**
• Invocations that comes from CLI, SDK, API Gateway
• Result returned immediately after the request
• Error handling happens client side (retries, exponential backoff etc.)

**Asynchronous**
• Gets invoked by  [S3](Cloud%20Computing/AWS/Storage/S3.md), [SNS](Cloud%20Computing/AWS/Application%20Integration/SNS.md), [Cloudwatch-Events](Cloud%20Computing/AWS/Monitoring/CloudWatch.md#Cloudwatch-Events) etc.
• Lambda retries up to 3 times if it fails (it supports error handling sort of)
• Processing must be idempotent (due to retries).

**Event Source Mapping**
• Used wit stream based services ([SQS](Cloud%20Computing/AWS/Application%20Integration/SQS.md), [Kinesis Data Stream](Kinesis#Kinesis%20Data%20Stream), [DynamoDB Streams](Cloud%20Computing/AWS/Databases/DynamoDB.md#DynamoDB%20Streams))
• Lambda does the polling (polls the source)
• Records are processed in order (except for [Standard Queues](SQS#Standard%20Queues))


## Concurrency
A lambda Function can handle a certain number of requests to it. If the limit is reached it will fail. and can result in the error: <span style="color:red">“Rate exceeded”</span>  and 429  <span style="color:red">“TooManyRequestsException”</span>. 

If the above error occurs, verify if you see throttling messages in Amazon CloudWatch Logs but no corresponding data points in the Lambda Throttles metrics. If there are no Lambda Throttles metrics, the throttling is happening on API calls in your Lambda function code

For asynchronous invocations Lambda retries up to 3 times then goes to a Dead Letter Queue which can be SNS topic or SQS queue.

![](Attachments/Pasted%20image%2020230325200432.png)

To resolve throttling is to configure reserved concurrency or to use exponential backoff in code.


## Lambda Versions

`MyFunction:$LATEST` is the version that you work on, then you can create versions which will look something like this: `MyFunction:1` or `MyFunction:2` the versions could not be edited while the latest one could be edited. Each version will have its own ARN and they could be used in different environments. 

![](Attachments/Pasted%20image%2020230325201153.png)


## Lambda Aliases
An alias will be used to point the [Lambda Versions](#Lambda%20Versions) which helps in easing deployments.

![](Attachments/Pasted%20image%2020230325201850.png)

## Pricing
The 1st million requests per month are free.
There-after $0.20 per additional 1 million requests

400,000 GB seconds free per month
Thereafter $0.0000166667 for every GB second

eg. 128MB RAM X 30Mins pm X 200ms runtime per invokation = $5.83


## Defaults and limits
Can only have 1000 Lambda running concurrently, Ask AWS support for Limit Increase.

/tmp directory can contain upto 500MB

By default Lambda run in No VPC. You can set them to by in your own VPC but your lambda will lose internet access.

You can set timeout to be a maximum of 15 minutes.

Memory can be set between 128MB to a maximum of 2008MB at an increment of 64MB.


## Cold Starts
A negative trade-off on using server-less functions. At first when the lambda function has not been triggered and is on an turned off state, It will require some time to start the server. 

This can cause delays in the User Experience.

Can be addressed through Pre Warning.

![Pasted image 20220724100910](Attachments/Pasted%20image%2020220724100910.png)