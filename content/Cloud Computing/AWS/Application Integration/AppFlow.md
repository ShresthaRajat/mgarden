# Amazon AppFlow
#aws #cloud

A fully managed service from [AWS](Cloud%20Computing/AWS/AWS.md) that allows you to integrate other SaaS services (Salesforce, Slack) with AWS services like [S3](Cloud%20Computing/AWS/Storage/S3.md), [Redshift](Cloud%20Computing/AWS/Databases/Redshift.md), [Snowflake](Snowflake), etc securely.

## Characteristics

• Can run up to 100 GB of data per flow
• Performs data transformations like mapping, merging, masking, filtering, and validation as part of the flow
• Leverages AWS [PrivateLink](PrivateLink) for secure transfer of data using private endpoints
• Encryption through AWS [KMS](Cloud%20Computing/AWS/Security%20&%20Identity/KMS.md) and fine-grained permissions can be applied  sing AWS IAM policies

![](Attachments/Pasted%20image%2020230325221254.png)


## Use cases:

• Synchronizing data from multiple sources for analytics
• Data enrichment – e.g. pull data from SaaS applications, add metadata and feed back to the SaaS application
• Event-based workflows – automatically trigger processes in one app based on data from another
• Transfer opportunity data from Salesforce to populate real-time dashboards
• Automate data backups from SaaS applications to AWS services such as Amazon S3
• Analyze Slack events using business intelligence tools