# Connecting to EC2 Instances: SSH, Alternative Methods and Troubleshooting

## Introduction to Server Access in the Cloud

As you venture into the cloud environment, connecting to your servers for maintenance or actions becomes crucial. In this README, we'll explore how to connect to Linux servers using SSH and various methods based on your operating system.

## SSH for Linux Servers

For Linux servers, SSH (Secure Shell) is the go-to utility for secure command-line access. Depending on your computer's operating system, here are the recommended approaches:

![SSH Overview](<../../../readme-images/EC2/SSh Overview/ssh summary table.png>)

1. **Mac and Linux:**
   - Use the SSH command-line utility.

2. **Windows (Version 10 and Above):**
   - SSH is available on Windows 10 and newer versions.

3. **Windows (Before Version 10):**
   - Utilize Putty, a versatile SSH client for Windows.

4. **Universal Method: EC2 Instance Connect:**
   - An innovative approach using your web browser.
   - Compatible with Mac, Linux, and all Windows versions.
   - Particularly works well with Amazon Linux 2 instances.

# SSH Troubleshooting

#### 1. There's a connection timeout

This is a security group issue. Any timeout (not just for SSH) is related to security groups or a firewall. Ensure your security group looks like this and correctly assigned to your EC2 instance.

#### 2. There's a connection refused

- This means the instance is reachable, but no SSH utility is running on the instance

- Try to restart the instance

- If it doesn't work, terminate the instance and create a new one. Make sure you're using Amazon Linux 3

#### 3. Permission denied (publickey,gssapi-keyex,gssapi-with-mic)

This means either two things:

- You are using the wrong security key or not using a security key. Please look at your EC2 instance configuration to make sure you have assigned the correct key to it.

- You are using the wrong user. Make sure you have started an Amazon Linux 2 EC2 instance, and make sure you're using the user ec2-user. This is something you specify when doing ec2-user@<public-ip> (ex: ec2-user@35.180.242.162) in your SSH command.

#### 4. I was able to connect yesterday, but today I can't

- This is probably because you have stopped your EC2 instance and then started it again today. When you do so, the public IP of your EC2 instance will change. Therefore, in your command, or Putty configuration, please make sure to edit and save the new public IP.

