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