---
tags: [aws, cloud, databases]
title: Amazon Quantum Ledger Database
aliases: [Amazon Quantum Ledger Database]
linter-yaml-title-alias: Amazon Quantum Ledger Database
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# Amazon Quantum Ledger Database
#aws #cloud #databases 

Amazon QLDB is a fully managed ledger database that provides a transparent, immutable, and cryptographically verifiable transaction log in [AWS](Cloud%20Computing/AWS/AWS.md).

- Amazon QLDB has a built-in immutable journal that stores an accurate and sequenced entry of every data change
- The journal is append-only, meaning that data can only be added to a journal, and it cannot be overwritten or deleted
- Amazon QLDB uses cryptography to create a concise summary of your change history
- Generated using a cryptographic hash function (SHA-256)
- Serverless and offers automatic scalability