# Amazon API Gateway: Quick Overview

A fully managed service that enables the creation of serverless HTTP APIs. It acts as a bridge between clients and serverless functions, facilitating data operations.

## Architecture

![API Gateway](<../../readme-images/other compute services/api gateway.jpeg>)

- **Clients:** They interact with the API Gateway.
- **API Gateway:** It proxies requests to Lambda functions for data operations.
- **Lambda Functions:** These execute operations.
- **DynamoDB:** A serverless NoSQL database for data operations.

## Features
   - Effortlessly create, publish, maintain, monitor, and secure APIs.
   - Operates without servers, scales on demand.
   - Enables standard HTTP and real-time streaming through WebSocket APIs.
   - Supports API key usage, user authentication for secure interactions.
   - Controls the rate of API invocation to manage usage.
   - Provides insights into API usage for effective monitoring.

## Exam Use Case

- **Building APIs:**
  - When asked to create a serverless API, think of combining API Gateway with Lambda.

