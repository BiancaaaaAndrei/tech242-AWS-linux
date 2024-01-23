# Amazon S3 Replication Overview
- [Amazon S3 Replication Overview](#amazon-s3-replication-overview)
- [Cross-Region Replication (CRR):](#cross-region-replication-crr)
- [Same-Region Replication (SRR):](#same-region-replication-srr)
- [Key Points:](#key-points)
- [Amazon S3 Replication Practice](#amazon-s3-replication-practice)
  - [Create Origin Bucket:](#create-origin-bucket)
  - [Create Replica Bucket:](#create-replica-bucket)
  - [Upload File to Origin Bucket:](#upload-file-to-origin-bucket)
  - [Configure Replication Rule:](#configure-replication-rule)
  - [Enable Replication:](#enable-replication)
  - [Upload New File to Origin Bucket:](#upload-new-file-to-origin-bucket)
  - [Check Replication in Replica Bucket:](#check-replication-in-replica-bucket)


# Cross-Region Replication (CRR):
1. Enable Versioning:
   - Versioning must be enabled in both the source and destination buckets.

2. Regions:
   - Source and destination regions must be different for CRR.

3. Asynchronous Replication:
   - Replication occurs asynchronously, ensuring data consistency.

4. IAM Permissions:
   - Grant proper IAM permissions for S3 service to read and write to specified buckets.

5. Use Cases:
   - Compliance requirements.
   - Lower latency access to data in another region.
   - Replicating data across AWS accounts.

# Same-Region Replication (SRR):
1. Enable Versioning:
   - Versioning must be enabled in both the source and destination buckets.

2. Regions:
   - Source and destination regions are the same for SRR.

3. Asynchronous Replication:
   - Similar to CRR, replication is asynchronous.

4. IAM Permissions:
   - Grant proper IAM permissions for S3 service to read and write to specified buckets.

5. Use Cases:
   - Aggregating logs across multiple S3 buckets.
   - Live replication between production and test accounts.

# Key Points:
- Replication happens behind the scenes, with changes replicated from source to destination.
- IAM permissions are crucial for enabling S3 to perform replication.
- Use cases include compliance, data availability, and replica

# Amazon S3 Replication Practice

In this exercise, we set up replication between two S3 buckets – an origin bucket and a replica bucket. Here's a summary of the steps:

## Create Origin Bucket:

- **Bucket Name:** S3_Stephane_Bucket_Origin_V2
- **Region:** EU West 1
- Enable Versioning

## Create Replica Bucket:

- **Bucket Name:** S3_Stephane_Bucket_Replica_V2
- **Region:** Choose a region (e.g., US East 1)
- Enable Versioning

## Upload File to Origin Bucket:

- **File:** beach.jpeg

## Configure Replication Rule:

1. Go to the management section of the origin bucket.
2. Create a new replication rule.
   - **Rule Name:** Demo Replication Rule
   - Enable Rule
   - **Source Bucket:** Leave as is
   - **Rule Scope:** Apply to all objects in the bucket
   - **Destination:** Choose the replica bucket in the same account
   - **IAM Role:** Create a new role
3. Save the rule

## Enable Replication:

- Choose not to replicate existing objects for this exercise.

## Upload New File to Origin Bucket:

- **File:** coffee.jpeg

## Check Replication in Replica Bucket:

1. Refresh the replica bucket after a few seconds.
2. Verify that the coffee.jpeg file and its version are replicated.
3. Upload a new version of beach.jpeg to observe version replication.

This exercise demonstrates the basics of S3 bucket replication, focusing on cross-region replication. Replication ensures that changes made in the origin bucket are asynchronously copied to the replica bucket, providing redundancy, compliance, and disaster recovery capabilities.

