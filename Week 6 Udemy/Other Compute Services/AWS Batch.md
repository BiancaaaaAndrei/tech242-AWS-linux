# AWS Batch Overview

- **Purpose:** Fully managed batch processing service for running computing batch jobs at any scale.
- **Batch Job Definition:**
  - A job that starts and ends at a specific time.
  - Contrasts with continuous or streaming jobs that run indefinitely.
- **Dynamic Scaling:**
  - Dynamically launches EC2 instances or Spot Instances based on the batch job load.
- **Batch Job Definition:**
  - Defined by a Docker image and a task definition, similar to ECS.
- **Cost Optimization:**
  - Automatically provisions the right amount of compute resources for batch jobs.
  - Focuses on cost optimization and minimizes infrastructure management.

## Batch Job Processing Flow

1. **User Action:**
   - Users submit images to Amazon S3.
2. **Trigger:**
   - Image uploads trigger a batch job in AWS Batch.
3. **Batch Job Execution:**
   - AWS Batch automatically manages an ECS cluster of EC2 instances or Spot Instances.
   - Ensures the right number of instances to handle the batch job queue.
   - Instances run Docker images, performing image processing jobs.
4. **Result:**
   - Processed objects are inserted into another Amazon S3 bucket.

![Batch Simplified](<../../readme-images/other compute services/Batch Simplified.jpeg>)

## Differences with Lambda

![Batch vs Lambda](<../../readme-images/other compute services/Batch vs Lambda.jpeg>)

- **Batch Processing:**
  - When the exam scenario involves running time-bound batch jobs efficiently, think of AWS Batch.

