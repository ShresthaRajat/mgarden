---
tags: [aws, cloud, security, rbac]
---
# IAM
#aws #cloud #security #rbac

Identity based management solution by [AWS](Cloud%20Computing/AWS/AWS.md)

IAM allows management of access of users and resources


## **Users** 
- End users who access AWS resources via the console or the API

## Groups 
- Group of users with shared permission levels which will be common for all of the users.

## **Roles**  

Associate permissions to a Role and then assign this to an [**Users**](Cloud%20Computing/AWS/Security%20&%20Identity/IAM.md#**Users**)or **[Groups](#Groups)**.

**IAM Policies** - 

![Pasted image 20220715093815](Attachments/Pasted%20image%2020220715093815.png)


## IAM Policies
JSON documents granting permissions for a specific user, group, or role to access the services. Policies are attached to **IAM Identities**.
![Pasted image 20220715094058](Attachments/Pasted%20image%2020220715094058.png)

## Managed vs Customer vs Inline policies

### Managed Policies 
default policies defined and given by AWS which is designed to support common use cases.
these cannot be edited.
These are indicated by an orange box.

### Customer Managed Policies
Custom policies created by users which is editable.

### Inline Policies
A policy which is directly attached to a user or a resource.




## IAM - Password Policy

In IAM you can set a Password Policy to set the minimum requirements of a password and rotate passwords so users have to update their password after X days


## IAM - Access Keys

Access keys allow user to interact with AWS services programmatically via the AWS CLI or the SDK

Per user can have 2 access keys.

## IAM - MFA

Can be turned on per user
The user has to turn on MFA themselves.
Administrator cannot enforce users to have MFA

The Administrator cannot create a policy requiring MFA to access certain resources.

![Pasted image 20220719151854](Attachments/Pasted%20image%2020220719151854.png)