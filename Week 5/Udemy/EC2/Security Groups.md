# Introduction to Security Groups

Security groups act as firewalls, regulating inbound and outbound traffic for your EC2 instances. Let's explore their fundamental concepts.

## Key Points about Security Groups

1. **Fundamental Functionality:**
   - Security groups are essential for network security in AWS.
   - They control traffic both into and out of EC2 instances.
   - Security groups consist of allow rules, specifying allowed traffic.

2. **Rule References:**
   - Rules can reference IP addresses or other security groups.
   - Allow rules dictate inbound traffic (from outside to EC2) and outbound traffic (from EC2 to outside).

3. **Rule Structure:**
   - Each rule includes the type (e.g., TCP), protocol, port, and source IP range.
   - Example rule: Allow TCP traffic on port 22 (SSH) from IP range 0.0.0.0/0 (anywhere).

## Diagram: Security Group Rules

Let's visualize how security groups work in a diagram:

![SG Diagram](<../../../readme-images/EC2/Security Groups/SG Diagram.png>)
   - EC2 instance with an attached security group.
   - Inbound rules authorize specific IP addresses or security groups.
   - Outbound rules, by default, allow all traffic from the instance.

## Key Security Group Concepts

1. **Flexibility:**
   - Security groups can be attached to multiple instances.
   - An instance can have multiple security groups.

2. **Regional Lockdown:**
   - Security groups are specific to a region/VPC combination.
   - Switching regions requires creating new security groups.

3. **External Placement:**
   - Security groups operate outside EC2 instances.
   - Blocked traffic won't reach the EC2 instance.

4. **Best Practices:**
   - Consider maintaining a separate security group for SSH access.
   - If your application is inaccessible, it might be a security group issue.
   - Connection refused indicates the security group worked; check the application.

5. **Advanced Feature: Security Group Referencing:**
   - Security groups can reference each other.
   - Useful for allowing communication between instances without specifying IPs.
   - Commonly used with load balancers.

## Exam-Relevant Ports

Know the following ports for the exam:
   - SSH (Secure Shell): Port 22 log into a Linux instance.
   - FTP (File Transfer Protocol): Port 21.
   - SFTP (Secure File Transfer Protocol): Upload files with SSH.
   - HTTP (Hypertext Transfer Protocol): Port 80 access unsecured websites.
   - HTTPS (Hypertext Transfer Protocol Secure): Port 443 access secured websites.
   - RDP (Remote Desktop Protocol): Port 3389 log into a Windows instance.
