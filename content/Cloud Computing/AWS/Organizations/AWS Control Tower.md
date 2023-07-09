---
tags: [aws, cloud, organization]
title: Control Tower
aliases: [Control Tower]
linter-yaml-title-alias: Control Tower
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:43 am
---
# Control Tower
#aws #cloud #organization 

Is an extension to [AWS Organization](Cloud%20Computing/AWS/Organizations/AWS%20Organization.md) provided by [AWS](Cloud%20Computing/AWS/AWS.md), that lets you create a landing zone (a well-architected multi-account baseline) 

Guardrails are used to governance and compliance:

**Preventive Guardrails** are base on SCPs and disallow API acitons

**Detective Guardrails** are implemented using AWS Config rules and Lambda functions and monitor and govern compliance

The root user can escalate the guardrails.
