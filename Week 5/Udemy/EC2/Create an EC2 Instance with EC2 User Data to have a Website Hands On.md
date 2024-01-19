# Launching Your First EC2 Instance on AWS

## Welcome and Overview

In this README we are launching our first Amazon EC2 (Elastic Compute Cloud) instance running Amazon Linux. The process involves using the AWS Management Console to navigate various parameters and options to configure and launch an EC2 instance. Here's a step-by-step guide:

## Steps to Launch EC2 Instance

### 1. Navigate to EC2 Console
   - Access the AWS Management Console.
   - Go to the EC2 console.

### 2. Launch EC2 Instance
   - Click on "Instances" and then "Launch Instances."

### 3. Configure Instance Details
   - #### Add a name and tags for identification.
   - #### Choose an Amazon Machine Image (AMI); in this case, we use Amazon Linux 3 AMI.
   - #### Select the instance type (e.g., T2 micro, eligible for the AWS Free Tier).
   - #### Create a key pair for SSH access (choose .pem for modern systems, PPK for Windows 7/8):
![The Key Pair](<../../../readme-images/EC2/Create EC2 with user data/The Key Pair.png>)

### 4. Configure Security Group
   - #### Set up security group rules to allow SSH (port 22) and HTTP (port 80) traffic:
![Security Group](<../../../readme-images/EC2/Create EC2 with user data/security group.png>)

### 6. Configure Advanced Details
   - Skip or configure advanced options like user data, IAM instance profile, etc.
   - User data can include a script executed during the instance's first launch:
```
#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
```

### 7. Review and Launch
   - Verify the configuration details.
   - Launch the instance.

### 8. Access Web Server on EC2
   - #### Copy the public IPv4 address of the instance.
   - #### Access the web server using the IP with HTTP (not HTTPS):
![Web Result](<../../../readme-images/EC2/Create EC2 with user data/web result.png>)

### 9. Stop and Restart the Instance
   - Stop the instance to save costs when not in use.
   - Restart the instance when needed.

### 10. Terminate the Instance
   - Terminate the instance if no longer required.

## Important Notes

- **Public IPv4 Address Change:**
  - When stopping and restarting an instance, the public IPv4 address may change.
  - Always use HTTP in the URL when accessing the instance's web server.

- **Key Pair:**
  - The key pair is crucial for SSH access to the instance.
  - Choose .pem for modern systems and PPK for Windows 7/8.

- **User Data:**
  - User data allows the execution of a script during the instance's first launch.
  - A sample user data script is provided to set up a basic web server.

