---
tags: [aws, cloud, encryption]
title: Cloud HSM
aliases: [Cloud HSM]
linter-yaml-title-alias: Cloud HSM
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# Cloud HSM
#aws #cloud #encryption 

Another service in [AWS](Cloud%20Computing/AWS/AWS.md) which allows management of [Encryption](Cyber%20Security/Cryptography/Encryption.md) keys. It is a cloud based hardware security module (HSM). Create and use your own encryption keys on AWS Cloud. Manage keys using FIPS 140-2 Level 3 validated HSMs. It runs in your [VPC](Cloud%20Computing/AWS/Networking/VPC.md).

[KMS](Cloud%20Computing/AWS/Security%20&%20Identity/KMS.md) Cloud be configured to use HSM cluster as custom key store.

It is a managed service and automatically scales.

Retains control of your encryption keys. you control access and is not accessible to anyone else including AWS.

## Cloud HSM vs AWS KMS

![](Attachments/Pasted%20image%2020230322001712.png)