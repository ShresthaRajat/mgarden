---
tags: [aws, cloud]
title: Service Control Policies
aliases: [Service Control Policies]
linter-yaml-title-alias: Service Control Policies
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# Service Control Policies
#aws #cloud 

Service control policies (SCPs) is a feature by [AWS](Cloud%20Computing/AWS/AWS.md) providing **a type of organization policy that you can use to manage permissions in your [AWS Organization](Cloud%20Computing/AWS/Organizations/AWS%20Organization.md). SCPs offer central control over the maximum available permissions for all accounts in your organization.

![Pasted image 20230225014157](Attachments/Pasted%20image%2020230225014157.png)
Explicit deny overrides any allows later levels
![Pasted image 20230225014220](Attachments/Pasted%20image%2020230225014220.png)



**Topics**
-   [Testing effects of SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html#scp-warning-testing-effect)
-   [Maximum size of SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html#scp-size-limit)
-   [Inheritance of SCPs in the OU hierarchy](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html#scp-about-inheritance)
-   [SCP effects on permissions](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html#scp-effects-on-permissions)
-   [Using access data to improve SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html#data-from-iam)
-   [Tasks and entities not restricted by SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html#not-restricted-by-scp)
-   [Creating, updating, and deleting service control policies](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_create.html)
-   [Attaching and detaching service control policies](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_attach.html)
-   [Strategies for using SCPs](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_strategies.html)
-   [SCP syntax](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_syntax.html)
-   [Example service control policies](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps_examples.html)