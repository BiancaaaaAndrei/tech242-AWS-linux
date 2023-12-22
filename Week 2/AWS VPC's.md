## Introduction
- AWS Virtual Private Cloud (VPC) is a web service that enables you to launch Amazon Web Services (AWS) resources in a logically isolated section of the AWS Cloud. It provides a virtual network dedicated to your AWS account, offering enhanced security, fine-grained control over your network settings, and the ability to customize the network architecture based on your specific requirements.

- This README provides essential information for understanding and working with AWS VPCs.

## Key Concepts
### CIDR Block: 
- When you create a VPC, you specify a private IPv4 address range using CIDR notation. This address range is divided into subnets.

### Subnets: 
- Subnets are segments of a VPC's IP address range in which you can launch AWS resources. You can place subnets in different availability zones for fault tolerance and high availability.

### Internet Gateway: 
- An Internet Gateway (IGW) is a horizontally scaled, redundant, and highly available VPC component that allows communication between instances in your VPC and the internet.

### Route Tables: 
- A route table contains a set of rules, called routes, that are used to determine where network traffic is directed. Each subnet in your VPC must be associated with a route table, which controls the routing for the subnet.

### Security Groups and Network ACLs: 
- Security groups act as a virtual firewall for your instances to control inbound and outbound traffic. Network Access Control Lists (ACLs) operate at the subnet level and act as a firewall for controlling traffic in and out of one or more subnets.

### VPC Peering: 
- VPC peering enables you to connect one VPC with another via a direct network route, allowing resources in different VPCs to communicate with each other.


## How to Create a VPC
[Steps on how to set up the VPC System](Steps_VPC.md)
