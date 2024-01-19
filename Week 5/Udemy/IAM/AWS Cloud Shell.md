# Using Cloud Shell for AWS Commands

## Overview

This README provides information on an alternative method for issuing commands against AWS using Cloud Shell, a terminal in the AWS cloud. Cloud Shell offers unique features and conveniences for managing your AWS resources.

## Cloud Shell Availability

The Cloud Shell icon is located in the top right corner of your screen:
![AWS Icon ](<../../../readme-images/iam/aws icon.png>)

## Getting Started

1. Launch Cloud Shell.
2. Verify that Cloud Shell is available in your region.
3. Issue AWS commands directly within Cloud Shell, e.g., `aws --version`.

## Key Features of Cloud Shell

### 1. API Calls and Default Region

- Cloud Shell mirrors API calls using the credentials of your current AWS account:
![AWS Cli Commmand](<../../../readme-images/iam/aws cli.png>)

- The default region for Cloud Shell API calls is your current logged-in region.

### 2. File Management

- Cloud Shell provides a repository for file management.
- Created files persist, even after restarting.
   ```
   echo "tests" > demo.txt
   ```
- To download a file from AWS CLI, just find the path of the document you want to download ("pwd") and then go to "Actions":
![download file from aws cli](<../../../readme-images/iam/download fle from aws cli.png>)
- And put the name of the file you want to download:
- ![File to download aws cli](<../../../readme-images/iam/file to download aws cli.png>)

