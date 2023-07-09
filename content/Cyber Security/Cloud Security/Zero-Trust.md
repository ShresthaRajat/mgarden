---
tags: [cyber-security, cloud-security]
title: Zero Trust Policy
aliases: [Zero Trust Policy]
linter-yaml-title-alias: Zero Trust Policy
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:42 am
---
# Zero Trust Policy
#cyber-security #cloud-security 

The Zero Trust framework describes a strict approach to cybersecurity in which every individual or device that attempt to access a private network, whether they are located inside or outside of that network, must be identified and authorized. Unlike other security models, which automatically trust individuals and devices that are already within the corporate network, zero trust advocates trusting no one at any time. The model was first described by John Kindervag, then a principal analyst at Forrester Research, in 2010.

## Principles of Zero Trust

Zero Trust can best be described by the axiom “don’t trust, always verify.”

It acknowledges that traditional IT security models that seek to protect networks from outside threats but that inherently trust individuals or devices already within the network, are flawed. The reason is because that trust could be misplaced: there may be insider threats within the network in the form of an employee who wants to compromise corporate data, or a device that has been compromised by an outside attack, or a set of user security credentials that has been stolen by a bad actor outside of the organization.

Zero Trust proposes that by inherently trusting all users or devices within a network, traditional IT security models leave open the possibility that unchecked bad actors could roam freely within the corporate network, accessing more corporate data along the way, and raising the potential scale and severity of a cyberattack.

## Zero Trust strategies

By comparison, the argument with Zero Trust is that organizations should assume their network has already been compromised and implement strategies or technologies to minimize further risk. Several of those strategies include:

### Segregation of Duties (SoD) (Guiding Principals)

This principle describes the idea that no one individual or device should have full access to all of an organization’s critical IT sources. If that were to happen, then a hacker who gains control of that individual or device’s security credentials would have unfettered access to everything in the corporate network.

Examples of too broad access include network firewalls and virtual private networks (VPNs). They isolate and limit access to technology resources and services but once you gain entry, you are trusted by default. 

Another important dimension of SoD is that no individual should have multiple roles especially in the critical parts of the software publishing pipeline. For example, no developer should have access from test to production or be able to self-elevate privileges without proper oversight.

### Least privilege access

In practice, the segregation of duties is achieved by giving each user a role with least privilege access, meaning that every user or device within the network can access only the most essential resources they need, and nothing else. The benefit is that if that user’s credentials or device is compromised by an outside attack, a hacker would only have access to that device’s environment, and nothing more than that, which reduces the potential security risk.

### Microsegmentation

Similarly, the Zero Trust model favors microsegmentation, which involves splitting up the corporate IT environment into security zones and requiring separate authorization in order to access each of those zones. This practice limits the chance that a hacker could “jump” from one part of the network to another in order to access and compromise more sensitive data.

### Multifactor authentication

This principle requires more than one method of authentication to verify user credentials. For example, rather than relying on a password alone, multifactor authentication might require that a user also input a secret code that has been sent to an email address or a mobile phone number that only the user should have access to.

### Just-in-time access

[Just-in-time access](https://www.ssh.com/academy/iam/just-in-time) is built around the idea that no user or machine identity should have permanent, always-on access to a critical resource. Instead, the identity is verified each time a connection is established but the authorization to access a resource disappears automatically after establishing the connection. This ensures that the identity requesting access goes through the required security controls every time.

### Auditing and tracking

A proper audit trail of activities ensures that there's always an up-to-date log of every connection along with a verified identity. Moreover, many Zero Trust solutions offer session recordings for knowing exactly what actions were taken in a session. This is very useful for forensics and for reporting in [Security Information and Event Management (SIEM)](https://www.ssh.com/academy/ssh/security-orchestration/siem) systems.

### Zero Trust technologies

A number of technology solutions have been created to address aspects of the Zero Trust framework, including but not limited to:

-   [Cloud-IAM](Cyber%20Security/Cloud%20Security/Cloud-IAM.md)
    
-   [Privileged access management (PAM)](https://www.ssh.com/iam/pam)
    
-   Multifactor authentication
    
-   Encryption software
    

SSH.COM has developed a comprehensive set of Zero Trust solutions to mitigate the risk of managing digital keys, privileged passwords and other secrets (like API tokens or certificates) by greatly reducing their numbers in IT infrastructures. Learn more about the [SSH.COM's Zero Trust and Just-in-time (JIT) solutions here](https://www.ssh.com/ssh-zero-trust-access-key-and-secrets-management).