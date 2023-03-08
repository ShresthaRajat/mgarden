# Organizaing Terragrunt
#terraform #IaC 

Organizing [Terragrunt](DevOps/IAC/Terraform/Terragrunt.md) enables us to write Dry code which could be easily be repeated to spin off multiple similar environments. For example if a company wants an app to have three separate environments in 9 different regions of the world with the same structure, using an effective terragrunt foldering stradegy can help to make this task easier as You will just have to create a common component for all of the components then spin the components of different environments in a region and just duplicate the region as a whole for example in this folder structure:
![Pasted image 20230117160643](Attachments/Pasted%20image%2020230117160643.png)
This will create a single environment within a single region which could easily be tweaked to create other evironments by just copying the level of folder and renaming/configuring the variables.