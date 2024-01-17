# IAM (Identity and Access Management) Introduction

## IAM: Users and Groups

- Root account created by default shouldn't be USED or SHARED
- Users = people in the organisation, and can be grouped!
- Groups only contain users, not other groups!
- Users don't have to belong to a group, and user can belong to multiple groups

Why create users and groups? Allow them to use our AWS accounts and to allow them, we need permissions.

## IAM: Permissions

##### Users or Groups can be assigned JSON documents called POLICIES
- This is just describing what a user is allowed to do or what a group and all the users within that group are allowed to do.

### Example:

![Alt text](<../../../readme-images/iam/WhatsApp Image 2024-01-17 at 14.02.44.jpeg>)

So in this example, we  allow people to:
- use the EC2 to service 
- use the elastic load balancing service 
- to use CloudWatch

#### We are allowing our users to use some services in AWS, so these policies will help us define permissions of our users.

- In AWS, you don't allow everyone to do everything that would be catastrophic, because a new user could basically launch so many services and they will cost you a lot of money or would be valid for security:
  - So you apply a principle called the least privilege principle which don't give more permissions than a user needs.
  - If a user just needs access to three services, just create a permission for that user.

## Using the IAM service to create users in AWS
- [IAM Create Users in AWS](Create-Users.md)

## IAM Policies
- [IAM Policies Inheritance and Structure](Policies-Inheritance.md)