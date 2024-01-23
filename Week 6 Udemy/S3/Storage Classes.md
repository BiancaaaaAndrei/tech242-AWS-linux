# S3 Storage Classes

## 1. Amazon S3 Standard - General Purpose
- Durability: 11 nines
- Availability: 99.99%
- Use Cases: Frequently accessed data, big data analytics, mobile and gaming applications, content distribution.
## 2. Amazon S3 Infrequent Access (S3 Standard-IA)
- Durability: 11 nines
- Availability: 99.9%
- Use Cases: Disaster recovery, backups.
## 3. Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA)
- Durability: 11 nines within a single Availability Zone (AZ)
- Availability: 99.5%
- Use Cases: Storing secondary copies of backups, data that can be recreated.
## 4. Glacier Storage Classes
### a. Amazon S3 Glacier Instant Retrieval
- Durability: 11 nines
- Availability: Milliseconds retrieval
- Minimum Storage Duration: 90 days
- Use Cases: Data accessed once a quarter.
### b. Amazon S3 Glacier Flexible Retrieval
- Durability: 11 nines
- Availability:
  - Expedited: 1-5 minutes
  - Standard: 3-5 hours
  - Bulk: 5-12 hours
- Minimum Storage Duration: 90 days
- Use Cases: Flexible retrieval needs, data accessed at different times.
### c. Amazon S3 Glacier Deep Archive
- Durability: 11 nines
- Availability:
    - Standard: 12 hours
    - Bulk: 48 hours
- Minimum Storage Duration: 180 days
- Use Cases: Long-term storage.
### 5. Amazon S3 Intelligent-Tiering
- Durability: 11 nines
- Automatic Tiers:
    - Frequent Access
    - Infrequent Access (objects not accessed for 30 days)
- Archive Instant Access (objects not accessed over 90 days)
- Optional Tiers:
    - Archive Access (configurable from 90 days to 700+ days)
    - Deep Archive Access (configurable for objects not accessed between 180 days to 700+ days)
- Fees: Monthly monitoring fee and auto-tiering fee, no retrieval charges.
- Remember that Amazon S3 Intelligent-Tiering automatically moves objects between access tiers based on usage patterns.


### Hands-On Storage Classes
This guide provides detailed information on creating and managing storage classes in Amazon Simple Storage Service (S3). The text below outlines the steps involved in setting up a new bucket, uploading objects, configuring storage classes, and automating transitions between storage classes.

### Setting Up a New Bucket

1. **Create a New Bucket:**
   - Bucket Name: \"s3-storage-classes-demos-2022\"
   - Choose any AWS region to create the bucket.

2. **Upload an Object:**
   - Upload a file, e.g., coffee.JPEG, into the newly created bucket.
   - Access the object's properties to explore storage class options.

### Storage Classes Overview

3. **Storage Class Options:**
   - Access object properties and navigate to the storage class section.
   - Explore various storage classes for AWS objects, choose the following for this exercise:
     - Standard-IA (Infrequently Accessed)

### Modifying Storage Classes

5. **Changing Storage Classes:**
   - Change the storage class of an object by:
     - Going to object properties.
     - Editing the storage class.
     - Choose a different storage class, e.g., One-Zone-IA, Glacier-Instant-Retrieval, or Intelligent-Tiering.
     - Save changes to apply the new storage class.

### Automation of Storage Class Transitions

6. **Lifecycle Rules:**
   - Navigate to the bucket's management section.
   - Create a lifecycle rule (e.g., \"DemoRule\").
![Alt text](<../../readme-images/S3/lc rule 1.png>)
   - Apply the rule to all objects in the bucket.
![Alt text](<../../readme-images/S3/lc rule 2.png>)
   - Configure transitions between storage classes based on time intervals (e.g., Standard-IA after 30 days, Intelligent-Tiering after 60 days, Glacier-Flexible-Retrieval after 180 days).
![Alt text](<../../readme-images/S3/lc rule 3.png>)
   - Review and manage transitions.

1. **Automation Benefits:**
   - Highlight the power of automating object movements between different storage classes.
   - Emphasize the flexibility and efficiency gained through the use of storage classes.

### Conclusion

8. **Summary:**
   - Storage classes in AWS S3 provide a versatile and powerful way to manage data storage based on access patterns and cost considerations.
   - Users can manually set storage classes for objects and automate transitions between classes using lifecycle rules.
   - Understanding and leveraging storage classes enable efficient data management in the AWS S3 environment.
