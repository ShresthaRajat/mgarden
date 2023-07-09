---
tags: [aws, cloud, cloud-migration]
title: AWS Server Migration Service (SMS)
aliases: [AWS Server Migration Service (SMS)]
linter-yaml-title-alias: AWS Server Migration Service (SMS)
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# AWS Server Migration Service (SMS)
#aws #cloud #cloud-migration 

It is a managed service from [AWS](Cloud%20Computing/AWS/AWS.md) to make migration of on premise service easy to be lifted and shifted to AWS.

## Server Migration

It can migrate VMware vSphere, Microsoft Hyper-V/SCVMM, and   Azure virtual machines ([VM](Cloud%20Computing/Azure/VM.md)) to Amazon [EC2](Cloud%20Computing/AWS/Compute/EC2.md).

The AWS SMS connector is installed in the Server, the data will be created in the AWS SMS which creates [AMI](Cloud%20Computing/AWS/Compute/AMI.md)s which can be used to spin up the copy of the servers in AWS.


## Application Migration

A fully automated way of migrating your server to AWS which configures a CloudFormation templates to spin up all of the required instances.

![](Attachments/Pasted%20image%2020230321145309.png)



You can also use SNS data