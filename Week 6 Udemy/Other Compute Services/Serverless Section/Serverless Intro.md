# Serverless Computing Overview

## What is Serverless?

- Serverless is a paradigm where developers do not manage servers directly. They deploy code or functions, and the underlying infrastructure is abstracted.
- **Serverless Evolution:** Initially, it was Function as a Service (FaaS) pioneered by AWS Lambda. Now, it encompasses managed services like databases, messaging, and storage.
- **Managed, Not Absent Servers:** Serverless doesn't mean there are no servers; it means users don't manage, provision, or see the servers.

## Examples of Serverless Services in this Course

1. **Amazon S3 (Simple Storage Service):**
   - **Usage:** Used as a storage layer in the course.
   - **Serverless Aspect:** S3 can scale infinitely without users managing any servers.

2. **Amazon DynamoDB:**
   - **Usage:** Used for creating tables without provisioning servers.
   - **Serverless Aspect:** DynamoDB tables auto-scale based on load without users managing servers.

3. **AWS Fargate:**
   - **Usage:** Used for running Docker containers.
   - **Serverless Aspect:** Fargate automatically runs containers without the need to provision EC2 instances.

4. **AWS Lambda:**
   - **Usage:** Running functions in the cloud.
   - **Serverless Aspect:** Pioneering serverless service, where users deploy functions without managing the underlying infrastructure.


