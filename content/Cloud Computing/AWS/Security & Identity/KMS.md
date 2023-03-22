# KMS
#cloud #aws #security 

[AWS](Cloud%20Computing/AWS/AWS.md) Key Management Service (AWS KMS) lets you create, manage, and control cryptographic keys across your applications and more than 100 AWS services. These keys could be used for [Encryption](Cyber%20Security/Cryptography/Encryption.md) as well as a form of [Authorization](Cyber%20Security/Cloud%20Security/Authorization.md) of the users/services. It can manage both Symmetric and Asymmetric Keys

The KMS keys are protected by hardware Security modules (HSMs).


![Pasted image 20230103145238](Attachments/Pasted%20image%2020230103145238.png)


## KMS Keys 

They were previously known as Customer Master Keys (CMKs) and are the primary resources in AWS KMS. It contains the main key to encrypt and decrypt the data.

- By default AWS KMS will create the key materal for a KMS key
- You can also import your own key
- A CMK can encrypt data up to 4KB in size
- You can generate, encrypt and decrypt Data Encryption Keys (DEKs)


## Alternative Key Stores
**External Key Store**
- Keys can be stored externally to meet regulatory requirements
- A key can be created in an AWS KMS external key store (XKS)
- Keys are generated and stored in an external key manager
- When using XKS, key never leaves HSM
-
**Custom Key Store**
- Can create KMS keys in AWS [[CloudHSM]] custom key store
- All keys are generated and stored in [CloudHSM](CloudHSM) self managed cluster
 - Not available for Asymmetric keys
 - Cryptoigraphic operations are done on AWS [CloudHSM](Cloud%20Computing/AWS/Security%20&%20Identity/CloudHSM.md) cluster that you own


## AWS Managed KMS Keys
These keys are created, managed and used on your behalf of AWS.
You cannot manage them manually as well as cannot be used in custom cryptographic operations directly. 

## Data Encryption Keys
- Data keys are encryption keys that you can use to encrypt
data, including large amounts of data and other data
encryption keys
- You can use AWS KMS customer master keys (CMKs) to
generate, encrypt, and decrypt data keys
- AWS KMS does not store, manage, or track your data keys,
or perform cryptographic operations with data keys
- You must use and manage data keys outside of AWS KMS
![](Attachments/Pasted%20image%2020230322000828.png)


## Key Rotation
![](Attachments/Pasted%20image%2020230322001054.png)
