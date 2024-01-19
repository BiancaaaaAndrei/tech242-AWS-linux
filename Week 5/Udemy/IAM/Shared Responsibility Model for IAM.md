# Shared Responsibility Model in AWS

## Introduction

Understanding the Shared Responsibility Model is crucial for the AWS Certified Cloud Practitioner (CCP) exam. This model delineates responsibilities between AWS and the customer, ensuring clarity on who is accountable for various aspects of security and management.

## Shared Responsibility Model Overview

1. **AWS Responsibilities:**
   - Infrastructure Management: AWS is responsible for managing and securing its global infrastructure.
   - Network Security: AWS ensures the security of its global network.
   - Service Configuration and Vulnerability Analysis: AWS manages the configuration and conducts vulnerability analysis for the services they offer.
   - Compliance: AWS is responsible for ensuring compliance with standards and regulations.

2. **Customer Responsibilities (IAM Focus):**
   - **User, Group, Role, and Policy Management:**
     - Customers are responsible for creating and managing their own IAM users, groups, roles, and policies.
     - Manage permissions and policies using IAM tools.

   - **MFA (Multi-Factor Authentication):**
     - Customers are responsible for enabling MFA on all accounts and enforcing this security measure.

   - **Key Rotation:**
     - Customers need to ensure that keys are rotated frequently for increased security.

   - **Permission Analysis:**
     - Analyze access patterns and review permissions in AWS accounts to ensure they align with security requirements.
