# Terragrunt
#cloud #IaC #terraform #DRY

A thin wrapper created around [Terraform](DevOps/IAC/Terraform/Terraform.md) that helps on keeping the cloud configuration IaC [DRY](DRY).  It is built by Gruntworks to extend the utility of terraform.

I helps on:
- Executing multiple, complex terraform command at once
- Keeping your backend configuration DRY
- Keeping Terraform CLI arguments DRY
- Create custom hooks for terraform