# IAM Creating a Role

## Introduction

In this hands-on practice, we will explore the creation of IAM Roles. IAM Roles allow us to grant permissions to AWS entities for performing specific tasks within the AWS environment.

## Creating a Role

1. Navigate to the left-hand side of the AWS Management Console and click on "Roles."
2. You may see pre-existing roles for your account; however, we will create a new role.
![Current Roles](<../../../readme-images/iam/current roles.png>)
1. Choose the role type; for this hands-on, we are focusing on a "role for an AWS service."
2. Select the AWS service to which the role will apply (e.g., EC2 for this demonstration).
3. Click "Next" to proceed.

## Attaching Policies

1. With the role created for an EC2 instance, we need to attach a policy.
2. Choose a policy; for example, attach the "IAM read-only access" policy.
![Add permissions](<../../../readme-images/iam/add permissions for the role.png>)
1. Click "Next" to proceed.

## Role Configuration

1. Enter a role name (e.g., DemoRoleForEC2).
2. Specify trusted entities; in this case, it can be assumed by the EC2 service.
3. Verify the attached permissions.
4. Click "Create role" to complete the process.
