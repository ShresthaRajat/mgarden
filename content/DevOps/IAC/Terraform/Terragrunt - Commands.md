---
tags: [terraform, IaC]
title: Terragrunt Commands
aliases: [Terragrunt Commands]
linter-yaml-title-alias: Terragrunt Commands
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:42 am
---
# Terragrunt Commands
#terraform #IaC 

you can use the following commands in console for [Terragrunt](DevOps/IAC/Terraform/Terragrunt.md):

To debug the plan process:

```bash
terragrunt plan --terragrunt-log-level debug --terragrunt-debug
```


To print the secret in terraform output use:
```bash
terragrunt output notsosecret
```