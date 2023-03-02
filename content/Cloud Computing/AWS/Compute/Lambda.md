# Lambda
#aws #cloud #serverless #compute #development 


Run code without provisioning or managing servers in [AWS](Cloud%20Computing/AWS/AWS.md).

Lambda executes your code only when needed and scales automatically to a few to a 1000 lambda functions concurrently in seconds.

Pay only for the times the lambda function is invoked.

Lambda is **Cheap**, **Serverless**, and **Scales Automatically**.

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
![Pasted image 20220724095845](Cloud%20Computing/AWS/Compute/Pasted%20image%2020220724095845.png)
2. Contact Email Form
![Pasted image 20220724095857](Cloud%20Computing/AWS/Compute/Pasted%20image%2020220724095857.png)


## Triggers
TO invoke a lambda it can be accomplished via the AWS SDK or from other AWS Services.

It can also be configured with 3rd party partner sources.


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

You can set timeout to be a mazimu of 15 minutes.

Memory can be set between 128MB to a mazimum of 2008MB at an increment of 64MB.


## Cold Starts
A negative trade-off on using server-less functions. At first when the lambda function has not been triggered and is on an turned off state, It will require some time to start the server. 

This can cause delays in the User Experience.

Can be addressed through Pre Warning.

![Pasted image 20220724100910](Cloud%20Computing/AWS/Compute/Pasted%20image%2020220724100910.png)