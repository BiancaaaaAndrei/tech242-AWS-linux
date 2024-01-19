# Generating IAM Credentials Report and Using Access Advisor

## Introduction

In this section, we'll explore two essential security tools in AWS Identity and Access Management (IAM): IAM Credentials Report and IAM Access Advisor. These tools provide valuable insights into user credentials and service permissions, enhancing the overall security posture.

## IAM Credentials Report

1. #### To generate a Credentials Report, navigate to the left-hand side of the AWS Management Console, click on "Credential report," and then select "Download credential report."
![Credential Report Section](<../../../readme-images/iam/demo security tools.png>)
 ##### The report, in CSV format, contains information about all users in the account, including creation details, password status, MFA activation, access keys, and their last usage.
2. #### Analyze the report to identify users who might require attention from a security standpoint, such as those not changing passwords or using MFA.

## IAM Access Advisor

1. #### Access Advisor operates at the user level and provides details on service permissions and access times.
2. #### To access IAM Access Advisor, go to the user details, click on the user (e.g., "bianca"), and then select "Access Advisor."
3. #### The tool displays a list of services accessed by the user and the corresponding timestamps:
    ![Accessed services by the users](<../../../readme-images/iam/accessed services by the users.png>)
4. #### Use Access Advisor to evaluate if the user has the correct permissions. It helps in optimizing permissions based on the principle of least privilege.
5. #### Drill down into specific services to understand which permissions were granted and by whom.

## Conclusion

IAM Credentials Report and IAM Access Advisor are powerful tools for monitoring and optimizing security in AWS IAM. Regularly reviewing these reports helps maintain a secure AWS environment by ensuring users have appropriate permissions and credentials.

