# EC2 Instance Store Readme

## Overview

This readme provides information on leveraging EC2 Instance Store for achieving higher disk performance on your EC2 Instances. While attaching a network drive is a common practice, EC2 Instance Store offers a higher level of performance by utilizing a hardware disk directly attached to the physical server hosting the EC2 Instance.

## Introduction to EC2 Instance Store

EC2 Instances are virtual machines connected to real hardware servers. Some of these servers have disk space attached directly to them via a physical connection. This attached storage is referred to as the EC2 Instance Store.

### Advantages of EC2 Instance Store

- **Better I/O Performance:** EC2 Instance Store provides improved input/output performance.
- **Higher Throughput:** It ensures good throughput for data operations, making it suitable for applications with demanding performance requirements.

### Considerations

- **Ephemeral Storage:** Data stored on EC2 Instance Store is ephemeral, meaning it is lost if the associated EC2 Instance is stopped or terminated. It is not a durable, long-term storage solution.

## Use Cases

EC2 Instance Store is ideal for scenarios where extremely high disk performance is crucial but with the understanding that data stored is temporary and may be lost in certain circumstances. Common use cases include:

- **Buffer and Cache:** Use EC2 Instance Store for buffering, caching, or storing temporary content.
- **Short-Term Data Storage:** Suitable for temporary data storage needs.

### Long-Term Storage Consideration

For long-term storage requirements, consider using services like Amazon Elastic Block Store (EBS), which provides persistent and durable storage.

## Responsibility for Data Backup

It's crucial to note that if you decide to use an EC2 Instance Store, the responsibility for data backup and replication lies entirely with you. In the event of a server failure, there is a risk of data loss as the hardware attached to the EC2 Instance is affected.
