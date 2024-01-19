# Introduction to Amazon EC2 (Elastic Compute Cloud)

## Overview

EC2, short for Elastic Compute Cloud, is a key offering that allows users to rent virtual machines, known as EC2 instances, providing Infrastructure as a Service (IaaS) on AWS.

## Components of EC2

1. **EC2 Instances:**
   - Virtual machines that can be rented on AWS.
   - Options for choosing the operating system (Linux, Windows, Mac OS), compute power (CPU), random access memory (RAM), and storage.

2. **EBS Volumes:**
   - Virtual drives for storing data.
   - Options for attaching storage through the network (EBS) or hardware-attached instance store.

3. **Elastic Load Balancer:**
   - Distributes load across multiple machines to ensure optimal performance.

4. **Auto-Scaling Group (ASG):**
   - Allows for scaling services by dynamically adjusting the number of EC2 instances based on demand.

5. **Security Group:**
   - Manages firewall rules for EC2 instances.

6. **EC2 User Data:**
   - Bootstrap script to configure instances at the first launch, automating boot tasks.

## Bootstrapping with EC2 User Data

- Bootstrapping involves launching commands when the EC2 instance starts.
- EC2 User Data script runs once during the initial boot to automate tasks such as installing updates, software, or downloading files.

## EC2 Instance Types

- #### A variety of instance types are available, offering different combinations of vCPUs, memory, storage, and network performance:
![EC2 Types](<../../../readme-images/EC2/EC2 Basics/ec2 types.png>)

## AWS Free Tier

- The t2.micro instance is part of the AWS Free Tier, allowing up to 750 hours per month at no cost.
