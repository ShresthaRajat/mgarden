# AWS CLI
#aws #cli

A [CLI](CLI) tool by [AWS](AWS/AWS.md) to controll aws resources via command line. It requires user credentials to perform actions to the account in which the credentials are valid and authorized to perform equivalent console based actions.

Lets users interact with AWS form a command line.
The CLI is installed via a Python Script.


# AWS SDK
#aws #sdk

A set of tools and libraries that you can use to create applcation sfor a specific software package

The AWS SDK is a set of API libraries that let you Integrate AWS services into your applications. The SDK is available on the following languages:

1. C++
2. Go
3. Java
4. JavaScript
5. .NET
6. NodeJS
7. PHP
8. Python (boto3)
9. Ruby



## Programmatic Access - Access Key and Secret

To access the AWS CLI and SDK, this is required for authenticating the making from which the user is trying to apply those commands and access the AWS resources.

the credentials get stored in a plain-text file. `~/.aws/credentials`

whenever possible use roles instead of AWS credentials for the programmatic access.

Programmatic access must be enabled for the user to use the [#AWS CLI](#AWS%20CLI) or [#AWS SDK](#AWS%20SDK)



