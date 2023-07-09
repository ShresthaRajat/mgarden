---
tags: [aws, cloud, auditing, logs, monitoring]
title: CloudTrail
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# CloudTrail
#aws #cloud #auditing #logs #monitoring 

Logs API calls between [AWS](Cloud%20Computing/AWS/AWS.md) services. when you need to know who to blame.

enables governance, complience, operational auditing and risk auditing of aws account.


used to monitor API calls and actions made by a user.

Ehere Source IP address
When EventTile
Who User, UserAgent
What Region, Resource, Action


CloudTrail is already logging by default and will collect logs for last 90 days via Event History.

If you need more than 90 days you need to create a Trail

Trails are output to S3 and do not have GUI like Event History. You can use Amazon Athena to analyze these Event Histories. 


- A Trail can be set to log all regions
- A Trail can be set to across all accounts in an Organization
- You can Encrypt your Logs using Server Side Encryption via (SSE-KMS)
- We can ensure the Integrity of our logs to see if they have been tampered we need to turn on Log File Validation.

## CloudTrail to CloudWatch

CloudTrail can be set to deliver events to a CloudWatch Logs.


## Management vs Data Events
There are two types of events in cloid trail.
![Pasted image 20220724020553](Attachments/Pasted%20image%2020220724020553.png)

## Use Cases

CloudTrail logs API activity for auditing. All management events are logged and retained for 90 days. **Trail** logs any events to [S3](Cloud%20Computing/AWS/Storage/S3.md) for indefinite retention and can be within Region or all Regions  CloudWatch Events can triggered based on API calls in CloudTrail. Events can be streamed to CloudWatch Logs which could be streamed and Metric filter could be used to perform any actions.




![](Attachments/Pasted%20image%2020230325011008.png)


![Pasted image 20220724020844](Attachments/Pasted%20image%2020220724020844.png)