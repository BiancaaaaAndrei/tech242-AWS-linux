# Amazon S3 Overview

## Introduction

Amazon S3 (Simple Storage Service) is a fundamental building block of AWS, offering infinitely scalable storage. It plays a crucial role in supporting many websites and AWS services. 

## Use Cases

Amazon S3 serves various use cases, thanks to its core storage functionality. Some common use cases include:
- Backup and storage of files, discs, and data.
- Disaster recovery by replicating data to another region.
- Archival of files for cost-effective long-term storage.
- Hybrid cloud storage to extend on-premises storage into the cloud.
- Hosting applications, media (videos, images), and static websites.
- Data lakes for storing and analyzing large volumes of data.
- Delivery of software updates.

Notable use cases:
- Nasdaq stores seven years of data in S3 Glacier for archival purposes.
- Sysco gains business insights by running analytics on data stored in Amazon S3.

## Key Concepts

1. **Buckets:**
   - Top-level directories in Amazon S3.
   - Must have globally unique names across all regions and AWS accounts.
   - Created at the region level.

2. **Objects:**
   - Files stored in buckets.
   - Identified by keys, which represent the full path of the file.
   - No explicit concept of directories; everything is a key.
   - Object keys are composed of a prefix and an object name.
   - Object values are the content of the file.
   - Max object size is 5 terabytes.

3. **Metadata and Tags:**
   - Objects can have metadata, key-value pairs providing information about the file.
   - Tags are Unicode key-value pairs (up to 10) useful for security and lifecycle management.
   - Objects can also have version IDs if versioning is enabled.

## Bucket Naming Convention

- Bucket names must:
  - Be unique globally across all AWS accounts and regions.
  - Have no uppercase or underscores.
  - Be between 3 and 63 characters long.
  - Not be an IP address.
  - Start with a lowercase letter or number.
  - Follow specific prefix restrictions.


# Working with Amazon S3 - Uploading Objects and Managing Buckets

## Creating a Bucket

- In the Amazon S3 console, start by creating a bucket.
- Choose a unique bucket name, following AWS naming conventions.
- Select a region for the bucket; buckets are region-specific.
- Verify that the bucket has been successfully created.

## Uploading Objects

1. Enter the newly created bucket.
2. Click on the "Upload" button.
3. Add files to upload; in this example, use a "coffee.jpg" file.
4. Confirm the destination bucket and click "Upload."
5. View the uploaded object in the bucket.

## Managing Objects in Buckets

- Explore the details of the uploaded object, including properties, size, and type.
- Open and view the object.
- Understand the difference between a public URL and a pre-signed URL. This is a public URL with no access permissions:
![Error URL](<../../readme-images/S3/error url access denied.png>)
- Create folders within the bucket, such as an "images" folder.
- Upload objects into specific folders within the bucket.
- Delete objects and folders as needed.