# IAM Access Analyzer for Amazon S3

- **Purpose:**
  - IAM Access Analyzer for Amazon S3 is a monitoring feature designed to ensure that only intended individuals have access to your S3 buckets.

- **Monitoring Scope:**
  - Analyzes various access control configurations, including:
    - Bucket Policies
    - S3 ACLs (Access Control Lists)
    - S3 Access Point Policies
  
![Alt text](<../../readme-images/S3/iam for s3.jpeg>)

- **Identification of Access Levels:**
  - Surfaces information on:
    - Buckets that are publicly accessible
    - Buckets shared with other AWS accounts

#### Functionality

- **Review and Action:**
  - Enables users to review the analysis results and determine whether access configurations align with expectations.

- **Security Assessment:**
  - Facilitates identification of security issues, such as unintentional bucket sharing, allowing users to take appropriate action.

#### Powered by IAM Access Analyzer

- **Resource Discovery:**
  - IAM Access Analyzer identifies resources in your AWS account that are shared with other entities.

