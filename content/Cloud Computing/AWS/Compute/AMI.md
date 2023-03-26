# Application Mirror image (AMI)
#aws #cloud #compute #packer 

[AWS](Cloud%20Computing/AWS/AWS.md) Provides a tool to recreate [EC2](Cloud%20Computing/AWS/Compute/EC2.md) instances and install dependencies, applications, software and security updates, and configure customization quickly. 

We can use [Packer](DevOps/IAC/Packer/Packer.md) to create AMIs as well.

![](Attachments/Pasted%20image%2020230305203555.png)



This can also be done by the help of [User data](User%20data) scripts, Which uses scripts to run commands and do these tools.

Also automation and configuration tools could be utilized to perform some of the similar function of the AMIs.

- AWS [CloudFormation](Cloud%20Computing/AWS/Application%20Integration/CloudFormation.md)
• AWS OpsWorks
• AWS Systems Manager
• AWS [Codepipeline](DevOps/CICD/AWS%20Codepipeline), [CodeDeploy](CodeDeploy) etc.
• Chef and Puppet
• Jenkins


