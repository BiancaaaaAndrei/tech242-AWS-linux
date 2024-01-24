- [Introduction to Databases](#introduction-to-databases)
- [Relational Databases](#relational-databases)
- [NoSQL Databases](#nosql-databases)
- [AWS Managed Databases](#aws-managed-databases)
- [Types of Databases](#types-of-databases)

# Introduction to Databases

- When storing data on disk in AWS, considerations arise regarding storage options like EBS drives, EBS volumes, EC2 Instance Store, or Amazon S3.
- For structured data storage and efficient querying, databases become essential, allowing the creation of indexes and structured relationships between datasets.
- Optimized for specific purposes, databases on AWS come with diverse features, shapes, and constraints, requiring an understanding of the suitable database for a given use case.

# Relational Databases

- Relational databases are common and traditional, involving linking tables similar to Excel spreadsheets.
- SQL language is used for queries and lookups.
- Relationships between tables, such as students and departments, are defined based on common identifiers.

![Relational](<../../readme-images/Databases/relational db.png>)

# NoSQL Databases

- NoSQL (non-relational) databases are modern and designed for specific purposes with a flexible schema.
- Offer flexibility, easy evolution of data models, scalability through horizontal scaling, high performance, and optimization for specific data models.
- Examples include: 
  - Key-value databases
  - Document databases
  - Graph databases
  - In-memory databases
  - Search databases.
- Data in NoSQL databases can be represented in JSON format, providing a common and flexible way to describe data:

![JSON](<../../readme-images/Databases/json format.jpeg>)

# AWS Managed Databases

- AWS provides managed databases with features such as 
  - Quick provisioning
  - High availability
  - Easy vertical and horizontal scaling
  - Automated backup and restore utilities
  - Integrated monitoring and alerting.
- AWS takes responsibility for patching the operating system of the underlying instance.
- Utilizing a managed database on AWS is recommended for its convenience and efficiency in many use cases.

# Types of Databases


