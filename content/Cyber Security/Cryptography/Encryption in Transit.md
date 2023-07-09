---
tags: [cyber-security, security, encryption]
---
# Encryption in transit
#cyber-security #security #encryption 

[Encryption](Cyber%20Security/Cryptography/Encryption.md)  of data in transit is the data moving from one location to another, such as across the internet or through a private network. Secure transfer can be handled by several different layers. It could be done by encrypting the data at the application layer before sending it over a network. HTTPS is an example of encryption in transit. [TLS](TLS) and [SSL](SSL) are the main protocols. While [TLS](TLS) is now depricated.

Encrypting data in transit protects it from outside observers and provides a mechanism to transmit data while limiting the risk of exposure.

![](Attachments/Pasted%20image%2020230321163205.png)


## Encryption for data in use

A common use case for encryption of data in use involves securing data in nonpersistent storage, such as RAM or CPU caches. This can be achieved through technologies that create an enclave (think of this as a secured lockbox) that protects the data and keeps data encrypted while the CPU processes the data.