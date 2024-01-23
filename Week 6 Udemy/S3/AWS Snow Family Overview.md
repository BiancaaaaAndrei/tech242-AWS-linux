# AWS Snow Family Overview

- [AWS Snow Family Overview](#aws-snow-family-overview)
  - [Data Migration Use Case](#data-migration-use-case)
  - [Diagram](#diagram)
    - [Data Migration Devices](#data-migration-devices)
      - [Data Migration Process](#data-migration-process)
  - [Edge Computing](#edge-computing)
    - [Edge Computing Devices](#edge-computing-devices)
  - [AWS OpsHub](#aws-opshub)


## Data Migration Use Case

- **Challenges of Network Transfer:**
  - Network transfer of large data can be time-consuming, expensive, bandwidth-limited, and unstable.

- **Snow Family Offline Devices:**
  - Snow Family devices offer an offline solution for data migration.
  
- **Data Transfer Time Example:**
  - Example: Transferring 100 terabytes over a one-gigabit per second network line takes 12 days, therefore, it is better to use an AWS Snow Family device!609

## Diagram

![Snow Family Diagram](<../../readme-images/S3/snow family.jpeg>)

### Data Migration Devices

![Types](<../../readme-images/S3/types snowfamily.jpeg>)

1. **Snowball Edge (for data transfers):**
   - Large device for moving terabytes or petabytes of data.
   - Two flavors: Storage Optimized (80TB) and Compute Optimized (42TB/28TB).
   - Suitable for large data cloud migration, decommissioning data centers, or disaster recovery.

2. **Snowcone:**
   - Small, portable, rugged device for environments with a small amount of data.
   - Two flavors: HDD Storage (8TB) and SSD Storage (14TB).
   - Suitable for edge computing, storage, and data transfer.

3. **Snowmobile:**
   - Truck-sized device for transferring exabytes of data.
   - Each Snowmobile has 100 petabytes of capacity.
   - High-security measures, including GPS and 24/7 video surveillance.

#### Data Migration Process

- **How It Works:**
  - Request the device from the AWS console for delivery.
  - Install the Snowball client or use AWS OpsHub on servers.
  - Connect the Snowball to servers and copy files.
  - Ship back the device to AWS via postal services.
  - Data is loaded onto an S3 bucket, and the device is wiped securely.

## Edge Computing

- **Definition:**
  - Edge computing involves processing data at edge locations where internet connectivity is limited or unavailable.

- **Devices for Edge Computing:**
  - Snowcone and Snowball Edge are used for edge computing.
  - Snowcone is small and portable, while Snowball Edge offers more compute and storage options.

### Edge Computing Devices

1. **Snowcone:**
   - Small, portable device with 8TB HDD or 14TB SSD storage.
   - Suitable for edge computing, storage, and data transfer.
   - Can be used in space-constrained environments.

2. **Snowball Edge Compute Optimized:**
   - Compute-optimized device with up to 104 vCPUs, 416GB RAM, and optional GPU.
   - Suitable for pre-processing data, machine learning at the edge, and transcoding media streams.

3. **Snowball Edge Storage Optimized:**
   - Storage-optimized device with 40 vCPUs, 80GB RAM, and 80TB storage.
   - Suitable for storage clustering and data transfer.

## AWS OpsHub

- **OpsHub Software:**
  - AWS OpsHub provides a graphical interface for managing Snow Family devices.
  - Unlocking and configuring single or cluster devices.
  - Transferring files, launching and managing EC2 instances, monitoring device metrics.

- **Summary:**
  - AWS Snow Family offers versatile solutions for data migration and edge computing.
  - Devices cater to different use cases and provide offline options for secure data transfer and processing.

