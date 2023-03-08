# Control Tower
#aws #cloud #organization 

Is an extension to [AWS Organization](Cloud%20Computing/AWS/Organizations/AWS%20Organization.md) provided by [AWS](Cloud%20Computing/AWS/AWS.md), that lets you create a landing zone (a well-architected multi-account baseline) 

Guardrails are used to governance and compliance:

**Preventive Guardrails** are base on SCPs and disallow API acitons

**Detective Guardrails** are implemented using AWS Config rules and Lambda functions and monitor and govern compliance

The root user can escalate the guardrails.
