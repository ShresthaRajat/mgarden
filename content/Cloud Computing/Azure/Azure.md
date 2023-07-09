---
title: Azure
enableToc: true
tags: [Azure, Cloud, Microsoft, cloud]
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---

# Azure
#cloud #Azure #Microsoft 

## Azure Geographies:
-  US
-  Azure Government US
-  Canada
-  Brazil 
-  Mexico

58 Regions available across 140 Countries

### Pared Regions
Each region is pared with another region 300 miles away.
One region is updated at a time to ensure no outages
Services are relied on pared region for Disaster Recovery

### Region Types and Service Availability
![Pasted image 20230210163119](Attachments/Pasted%20image%2020230210163119.png)

### Special Regions
Has specialised regions to meet compliance or legal reasons

- US DoD Central
- US Gov Virginia
- US Gov Iowa
- China East
- China North

### AZ supported Regions
**Alternate** or **Other** will not have support for AZ.
The Regions with atleast 3 AZs are:
- Central US
- East US 2
- West US 2
- Went Europe
- France Central
- North Europe
- Southeast Asia


## Availability zone (AZ)
- A physical location made up of one or more data-center.
- A region will generally contain 3 AZs
- Data-centers within a region will be isolate from each other.
- For high availability it is common to run workloads on at least 3AZs

![Pasted image 20230210163519](Attachments/Pasted%20image%2020230210163519.png)

### Fault and Update Domain

**Fault Domain** is a logical grouping of hardware to avoid a single point of failure within an AZ

**Update Domain** is used when Azure needs to apply updates to the underlying hardware and software. (Azure make sure by using update domain to eliminate downtime)

**Availability Set** is a logical grouping that can be configured in Azure to ensure that the VMs are placed in different fault/update domains to avoid downtime.

![Pasted image 20230210164159](Attachments/Pasted%20image%2020230210164159.png)


---



## Computing Services
- Azure VM
- Azure Container Instances (Docker as a Service)
- Azure kubernetes Service (Kubernetes as a Service)
- Azure Service Fabric (Tier-1 Enterprise Container as a Service)
- Azure Functions
- Azure Batch


## Storage Services
- Azure Blob storage
- Azure Disk Storage (Similar to EBS)
- Azure File Storage (NFS, Similar to EFS)
- \*Azure Queue Storage (Messaging Queue)
- \*Azure Table Storage (Wide column NoSQL Database)
- Azure Data Box/Azure Databox Heavy (Rugged breifcase computer)
- Azure Archive Storage (Long term cold storage)
- Azure Data Lake Storage (centralized repository like [Snowflake](Snowflake))


## Database Services
- Azure Cosmos DB (NoSQL database)
- Azure SQL Database (MS SQL database)
- Azure Database for MySQL/PLSQL/MariaDB
- SQL Server on VMs (lift and shift existing on-prem sql server dbs)
- Azure Synapse Analytics (Azure SQL Data Warehouse)
- Azure Database Migration Service
- Azure Cache for Redis
- \*Azure Table Storage


## Application Integration Services
- Azure Notifications Hub (SNS)
- Azure API Apps (Essentially API Gateways)
- Azure Service Bus (Messaging as a service SES)
- Azure Stream Analytics (Serverless real-time analytics)
- Azure Logic apps
- Azure API Management (add in front of an existing APIs)
- \*Azure Queue service (SQS)


## Developer and Mobile Tools
- Azure Signal Service (Real-time Messaging)
- Azure App Service (PaaS like Heroku)
- Visual Studio (IDE code editor)
- Xamarin (Mobile app framework)


## Azure DevOps Services
Azure devops is basically a 
Azure Boards
Azure Pipelines
Azure Repos
Azure Test Plans (manual and exploratory testing tools like cyprus.io)
Azure Artifacts
Azure DevTest Labs


## Azure Resource Manager (ARM)

IaC  of Azure, Azure Resources Manager or ARM allows you to create Azure resources via Json templates. 

**Azure QuickStart** is a library of pre-made ARM templates provided by the community and partners to help you quickly launch new projects for a variety of stack scenarios


## Azure Virtual Networks

**vNet** is a logically isolated section of Azure Network where you launch your Azure resources. you choose a CIDR range to be used within the network.

**Subnet** is a logical partition of an IP network to breakup the IP-ranges within a vNet. The CIDRs range must be smaller than the vNets. There could be Public or Private Subnets.


## Cloud-Native Networking Services
- Azure DNS (like Route 53)
- Azure Virtual Network (vNet)
- Azure Load Balancer (OSI level 4 (Transport) Load Balancer)
- Azure Application Gateway (OSI Layer 7 HTTP load balancer, WAF applicable)
- Network Security Groups (NSGs) (virtual firewall at subnet level)

## Enterprise/Hybrid Networking Services
- Azure Frontdoor ()
- Azure Express Route (Connection between On-prem to cloud)
- Virtual WAN 
- Azure Connection (VPN connection)
- Virtual Network Gateway (A site to site VPN)

## Scale Sets
This allows you to group together identical virtual machines and automatically increase or decrease the amount of servers based on:
- change  in CPU, memory, disk and network performance
- On a predefined schedule

Similar to AWS EC2 auto scaling groups.

## IOT Services
- IoT central (device-cloud connection)
- IoT Hub (device-application connection)
- IoT Edge (edge computing)
- Windows 10 IOT Core Services


## Big Data and Analytics Services
- Azure Synapse Analytics (Enterprise data warehousing and BD analytics)
- HDInsight (Runs Open-source analytics software like Hadoop, Kafka, Spark)
- Azure Databricks (Apace Spark based analytic platform)
- Data Lake Analytics


## AI/ML Services
- **Azure Machine Learning Service**  
- Personalizer
- Translator
- Anomaly Detector
- Azure Bot Service
- Form Recognizer
- Computer Vision
- Language understanding
- QnA maker (QA bot)
- Text Analytics
- Content Moderator
- Face
- ink Recogniser (OCR)


## Serverless Services
Highly Available, Scaleable, and Cost-effective solution that could be **Event Driven Scaled**, **Abstract Servers**, and ** Bill in microseconds for cost effectiveness**.
- Azure Functions
- Blob storage
- Logic Apps (Like Lambda step function)
- Event Grid (pub/sub to trigger other services)


**Azure Portal** is a web based, unified console as an alternative to azure cli. There are also *Azure Preview Portal* to utilize new features.
`preview.portal.azure.com`

**Azure CLI**
Supported on Windows, Mac and Linux and can be used to manage Azure resources via CLI.

**PowerShell** is a task automation and configuration management framework. Can be used as a command-line shell and a scripting language like bash. It is built on top of .NET Common Language Runtime, it accepts and returns .Net objects.

**Azure PowerShell** are a set of cmdlets for managing Azure resources directly from PowerShell command Line

**Azure Cloud Shell** is and interactive, authenticated browser-accessible shell for managing azure resources via Bash or PowerShell.

**Visual Studio Code** is a free source-code editor. 

