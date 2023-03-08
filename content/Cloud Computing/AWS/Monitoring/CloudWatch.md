# Cloudwatch
#aws #cloud  #monitoring #logs 

monitoring solution for all of the various AWS resources by [AWS](Cloud%20Computing/AWS/AWS.md).

![Pasted image 20220724014551](Attachments/Pasted%20image%2020220724014551.png)


## Cloudwatch-Logs
, store, and access your log files.


A Log Group is a collection of logs. Log files must belong to a log group.

A log in Log Group is called a Log Stream

By default, logs are kept indefinitely and never expire

MostAWS services are integrated with CloudWatch Logs.
Logging of services sometimes need to be turned on or requires the IAM Permissions to write to CloudWatch Logs.

## CloudWatch-Metrics
Represents a tie-ordered set of data points.

CloudWatch comes with many predefined metrics eg.

EC2 Per-Instance Metrics
such as CPU Utilization/ DiskReadOps, NetworkIn

### Custom Metrics
Using AWS CLI or SDK we can create and publish custom metrics. (Like Memory Utilization, Disk Usage which usually requires a cloudwatch agent).

High resolution metrics can be enabled instead of standard metrics. A high definition metrics lets you track a metric under 1 minute down to 1 second. 


## Cloudwatch-Events

Trigger an event based on condition or on schedule.


## Cloudwatch-Alarms
Triggers a notification based on a metric which breach a defined threshold. 


## Cloudwatch-Dashboards
Create custom dashboards from CloudWatch metrics.


## Cloudwatch-Availability



![Pasted image 20220724015847](Attachments/Pasted%20image%2020220724015847.png)
