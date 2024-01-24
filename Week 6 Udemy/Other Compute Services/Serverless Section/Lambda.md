# AWS Lambda - Reactive Service

Lambda is a serverless computing service where developers deploy functions without managing underlying servers.

- **Key Attributes:**
  - **Event-Driven:** Functions run on demand in response to events or when needed.
  - **Scalability:** Scaling is automated by the Lambda service.
  - **Short-Lived Executions:** Functions are limited by time, designed for shorter executions.

## Benefits of AWS Lambda

1. **Easy Pricing:**
   - Pay per request and compute time.
   - Generous free tier.

2. **Integration:**
   - Fully integrated with AWS services.
   - Event-driven model triggers functions based on events = reactive service!

3. **Language Support:**
   - Supports various programming languages.

4. **Common Use Cases:**
   - **Serverless Thumbnail Creation:**
     - S3 triggers Lambda on image upload.
     - Lambda creates thumbnail, updates metadata in DynamoDB.
     - Fully event-driven and serverless.

![Thumbnail Creation Serverless](<../../../readme-images/other compute services/thumbnail.jpeg>)

   - **Serverless CRON Job:**
     - CloudWatch Events or EventBridge triggers Lambda function.
     - Runs scripts on a schedule without provisioning servers.

![CRON Job](<../../../readme-images/other compute services/cron.jpeg>)

## Pricing

- **Per Call Pricing:**
  - First one million invocations free.
  - $0.20 per 1 million requests thereafter.
- **Duration Pricing:**
  - Free tier includes 400,000 gigabyte seconds.
  - Beyond free tier: $1 for 600,000 gigabyte seconds.
