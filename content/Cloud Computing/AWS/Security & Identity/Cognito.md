---
tags: [aws, cloud, security]
title: Amazon Cognito
aliases: [Amazon Cognito]
linter-yaml-title-alias: Amazon Cognito
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# Amazon Cognito
#aws #cloud #security 

Decentralised way of managing [Authentication](Cyber%20Security/Cloud%20Security/Authentication.md) by [AWS](Cloud%20Computing/AWS/AWS.md).

There are two types of pools: [Cognito Identity Pools](#Cognito%20Identity%20Pools) as well as [Cognito User Pools](#Cognito%20User%20Pools)



## Web Identity Federation and IpD

### Web Identity Federation
To exchange identity and security information between an [#Identity Provider IdP](#Identity%20Provider%20IdP) and application.

### Identity Provider (IdP)
a trusted provider of your user identity that lets you use authenticate to access other services. Identity Providers could be: Google, Facebook, GitHub, etc

types:
	1. Security Assertion Markup Language (SAML)
	2. OpenID Connect (OIDC) OAuth (Used by Google, Facebook, Github, etc)

## Cognito User Pools
User directory with authentication to [#Identity Provider IdP](#Identity%20Provider%20IdP) to grant access to your app to manage actions for web and mobile apps such as:
	1. Sign-up
	2. Sign-in
	3. Account recovery
	4. Account Confirmation
![](Attachments/Pasted%20image%2020230307002301.png)

Allows users to sign in directly to the user pool or using Web Identity Federation.

Uses AWS Cognito as the identity broker between AWS and the identity provider.

Successfully authentication generates a JSON Web Token (JWTs).

User Pools can be thought of as the account used to access the system (ie. email address and password)

*  Choose password requirements
* Apply MFA
* Restrict whether users are allows to signup on their own or need admin verification.
* Analytics with Pinpoint for user campaigns.
* Trigger custom log via Lambdas after actions such as signup

## Cognito Identity Pools

**Identity Pools** provide temporary AWS credentials to access services eg. S3 DynamoDB. Identity Pools can be thought of as the actual mechanism authorising access to the AWS resources.

![](Attachments/Pasted%20image%2020230307002550.png)



## Cognito Sync

Sync user data and preferences across devices with one line of code.

Cognito uses push synchronisation  to push updates and synchronise data. Uses [SNS](Cloud%20Computing/AWS/Application%20Integration/SNS.md) to send notifications to all user devices when data in the cloud changes.

![Pasted image 20220719153956](Attachments/Pasted%20image%2020220719153956.png)

