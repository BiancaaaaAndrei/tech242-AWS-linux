# EFS (Elastic File System)

## Introduction

This readme provides information on EFS (Elastic File System), a network file system that can be attached to EC2 instances. EFS is designed to offer shared network file storage, allowing it to be mounted on hundreds of EC2 instances simultaneously.

## Key Features and Benefits

- **Shared Network File System:** EFS can be mounted onto hundreds of EC2 instances, making it a shared network file system.
- **Multi-AZ Support:** EFS works across multiple availability zones, enabling instances in different AZs to attach the same EFS volume:
![EFS File System](<../../../readme-images/ec2 image builder/efs filesystem.png>)

- **Highly Available and Scalable:** EFS is highly available and scalable to meet the demands of applications.
- **Pay-Per-Use Pricing:** While EFS is relatively more expensive than gp2 EBS volumes, you only pay for the storage you use, making it cost-effective for dynamic workloads.

## Use Cases

EFS is suitable for scenarios where shared file storage is required across multiple EC2 instances. Common use cases include:

- **Shared Application Data:** Ideal for applications that require shared access to files across instances.
- **Collaborative Workloads:** Suitable for collaborative workloads where multiple instances need access to the same files.

## Comparison with EBS and EFS

### EBS 

- EBS volumes are attached to one EC2 instance at a time.
- Bound to specific availability zones.
- **Can be moved between availability zones using snapshots, but it's a copy, not an in-sync replica.**
![EBS](<../../../readme-images/ec2 image builder/ebs.jpeg>)

### EFS 

- EFS is a network file system, allowing everything mounted to it to share the same files.
- Instances in different availability zones can simultaneously mount the same EFS volume.
- **EFS supports a storage class called EFS Infrequent Access (EFS-IA) for cost-optimized storage of less frequently accessed files.**
![EFS](<../../../readme-images/ec2 image builder/efs.jpeg>)

## EFS Infrequent Access (EFS-IA)

- **Cost-Optimized Storage:** EFS-IA offers up to 92% lower cost for storing data compared to EFS standard.
- **Automatic File Movement:** EFS automatically moves files to EFS-IA based on access patterns and lifecycle policies.
- **Transparent to Applications:** Applications do not need to be aware of the storage class; EFS handles the optimizations transparently.

![EFS Infrequent Access (EFS-IA)](<../../../readme-images/ec2 image builder/EFS Infrequent Access (EFS-IA).jpeg>)
