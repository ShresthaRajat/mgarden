---
tags: [aws, cloud, cloud-migration]
title: Migration & Transfer
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# Migration & Transfer
#aws #cloud #cloud-migration 

Migrating to [AWS](Cloud%20Computing/AWS/AWS.md) could be done with seven common migration strategies (7 Rs) for moving applications to the AWS Cloud. These strategies are refactor, replatform, repurchase, rehost, relocate, retain, and retire. For more information, see the [7 Rs](https://docs.aws.amazon.com/prescriptive-guidance/latest/migration-retiring-applications/apg-gloss.html#gloss-mig-7rs-terms) in the glossary.

![](Attachments/Pasted%20image%2020230304231648.png)
1. Refactor
2. Replatform
3. Repurchase
4. Rehost
5. Relocate
6. Retain
7. Retire

Most popular migration strategies: 
**Rehost** – OS/App moved to another host system
	• AWS recommend the AWS Application Migration Service (AWS MGN) for lift & shift
	• Can also use AWS SMS and AWS VM Import / Export

**Replatform** – Ex. database to RDS; server to Elastic Beanstalk
	• AWS Database Migration Service (AWS DMS) and Schema 	Conversion Tool (SCT)
	• Migrate to EB using custom AMI, or code-level migration
	• Moderate development and migration effort

**Refactor** – Re-architect to a cloud-native serverless architecture
	• Leverage serverless services and event-driven architecture patterns
	• Migrate servers to serverless functions or containers
	• Migrate databases to managed DBs or serverless NoSQL DBs
	• Migrate file stores to object stores or elastic file systems
	• Decouple with queues, notification services, and orchestration tools
	• May involve a large amount of development and migration effort as well as expense

## Tools:

![](Attachments/Pasted%20image%2020230304230726.png)