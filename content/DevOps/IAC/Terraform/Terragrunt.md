---
tags: [cloud, IaC, terraform, DRY]
title: Terragrunt
date created: Monday, July 10th 2023, 12:40:08 am
date modified: Monday, July 10th 2023, 12:40:42 am
---
# Terragrunt
#cloud #IaC #terraform #DRY

A thin wrapper created around [Terraform](DevOps/IAC/Terraform/Terraform.md) that helps on keeping the cloud configuration IaC [DRY](DRY).  It is built by Gruntworks to extend the utility of terraform.

I helps on:
- Executing multiple, complex terraform command at once
- Keeping your backend configuration DRY
- Keeping Terraform CLI arguments DRY
- Create custom hooks for terraform