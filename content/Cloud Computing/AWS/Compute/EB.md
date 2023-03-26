# AWS Elastic Beanstalk (EB)
#aws #cloud 


A PaaS solution from [AWS](Cloud%20Computing/AWS/AWS.md) to make deployment of web apps easier by providing a fully managed environment. It makes deployment of the application a lot easier just like [Heroku](Heroku).

It can launch all of the required resources for the Operating the Application on AWS by provisioning resources like [EC2](Cloud%20Computing/AWS/Compute/EC2.md), [ASG](Cloud%20Computing/AWS/Compute/ASG.md), [ELB](Cloud%20Computing/AWS/Compute/ELB.md), [SQS](Cloud%20Computing/AWS/Application%20Integration/SQS.md) etc. by storing the code to [S3](Cloud%20Computing/AWS/Storage/S3.md) and creating them within your chosen [VPC](Cloud%20Computing/AWS/Networking/VPC.md).

![](Attachments/Pasted%20image%2020230326145552.png)


![](Attachments/Pasted%20image%2020230326151234.png)
## Layers

### Applications
contains environment and environment versions. This can contain multiple versions. 
![](Attachments/Pasted%20image%2020230326150050.png)

### Environment
Versions of application that are deployed, where the resources are configured and provisioned by Elastic Beanstalk.
![](Attachments/Pasted%20image%2020230326150123.png)



## Deployment

There are many deployment strategies with their own pros and cons.
![](Attachments/Pasted%20image%2020230326151321.png)

![](Attachments/Pasted%20image%2020230326151437.png)

![](Attachments/Pasted%20image%2020230326151449.png)

![](Attachments/Pasted%20image%2020230326151504.png)

![](Attachments/Pasted%20image%2020230326151518.png)

![](Attachments/Pasted%20image%2020230326151539.png)