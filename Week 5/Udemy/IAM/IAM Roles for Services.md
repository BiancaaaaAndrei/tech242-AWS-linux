# IAM Roles in AWS

## Introduction

IAM Roles act like users but are designed for use by AWS services rather than physical individuals. The primary purpose is to assign permissions to AWS services so they can execute actions on our account.

## Example Use Case

For instance, when creating an EC2 Instance, it may need to perform actions on AWS. To grant the necessary permissions to the EC2 Instance, an IAM Role is created. The EC2 Instance and IAM Role together form a unified entity. When the EC2 Instance attempts to access information from AWS, it uses the associated IAM Role. Successful access depends on the permissions assigned to the IAM Role.

## Common Roles

Common roles include EC2 Instance roles, Lambda Function Roles, CloudFormation roles, and others that perform actions against AWS. Each role serves a specific purpose in managing AWS resources.

## Creating a Role
[Step-by-Step to create a role](<IAM Creating a Role.md>)

