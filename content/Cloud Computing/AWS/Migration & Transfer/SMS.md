# AWS Server Migration Service (SMS)
#aws #cloud #cloud-migration 

It is a managed service from [[AWS]] to make migration of on premise service easy to be lifted and shifted to AWS.

## Server Migration

It can migrate VMware vSphere, Microsoft Hyper-V/SCVMM, and  Azure virtual machines to Amazon EC2.

The AWS SMS connector is installed in the Server, the data will be created in the AWS SMS which creates AMIs which can be used to spin up the copy of the servers in AWS.


## Application Migration

A fully automated way of migrating your server to AWS which configures a CloudFormation templates to spin up all of the required instances.

![](Attachments/Pasted%20image%2020230321145309.png)



You can also use SNS data