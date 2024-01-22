# Scalability, High Availability, and Elasticity Readme

## Introduction

This readme covers the concepts of Scalability, High Availability, and Elasticity in the context of AWS, focusing on Elastic Load Balancing and Auto Scaling Groups. These concepts play a crucial role in optimizing the performance and resilience of applications in the cloud.

## Scalability

Scalability refers to the ability of a system to handle increased loads by either making the hardware stronger (vertical scaling) or adding more instances/nodes (horizontal scaling). 

### Vertical Scalability
- **Example:** Upgrading a junior operator to a senior operator in a call center.
- **AWS Equivalent:** Increasing the size of an EC2 instance, e.g., moving from t2.micro to t2.large.

### Horizontal Scalability
- **Example:** Adding more operators to a call center to handle increased call volume.
- **AWS Equivalent:** Increasing the number of instances using Amazon EC2 and Auto Scaling Groups.

## High Availability

High Availability involves running an application in at least two availability zones on AWS to ensure system reliability and minimize downtime.

- **Example:** Running a call center in both New York and San Francisco to survive disasters or outages in one location.
- **AWS Implementation:** Deploying instances across multiple availability zones using Auto Scaling Groups and Load Balancers.

## Elasticity

Elasticity is a cloud-native concept where a system can automatically scale based on demand, optimizing costs by adjusting resources dynamically.

