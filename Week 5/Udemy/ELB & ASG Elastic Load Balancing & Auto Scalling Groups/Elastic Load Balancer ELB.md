# Elastic Load Balancing (ELB)

- [Elastic Load Balancing (ELB)](#elastic-load-balancing-elb)
  - [Overview](#overview)
  - [Key Concepts](#key-concepts)
    - [Load Balancer](#load-balancer)
    - [Backend EC2 Instances](#backend-ec2-instances)
    - [Elastic Load Balancing (ELB)](#elastic-load-balancing-elb-1)
  - [Use Cases](#use-cases)
  - [Types of Load Balancers](#types-of-load-balancers)
- [Launching Load Balancer and EC2 Instances - Practice Summary](#launching-load-balancer-and-ec2-instances---practice-summary)
  - [Steps Taken](#steps-taken)

## Overview
ELB is a managed service that distributes incoming application or network traffic across multiple targets, such as EC2 instances, enhancing the availability and fault tolerance of applications.

## Key Concepts

### Load Balancer

- A server managed by AWS that forwards internet traffic to multiple servers downstream (backend EC2 instances).

### Backend EC2 Instances

- EC2 instances behind the load balancer that handle the actual workload.

### Elastic Load Balancing (ELB)

- Managed by AWS.
- Guarantees availability, upgrades, maintenance, and high availability.
- Configurable for load balancing behavior.

## Use Cases

- Spread load across multiple downstream instances.
- Expose a single point of access (DNS hostname).
- Seamlessly handle failures of downstream instances.
- Provide SSL termination for HTTPS.
- Use across multiple availability zones for high availability.

## Types of Load Balancers

![Types of ELB](<../../../readme-images/ELB & ASG/Types of ELB.jpeg>)


# Launching Load Balancer and EC2 Instances - Practice Summary

Launching EC2 instances and creating an Application Load Balancer (ALB) to distribute traffic across these instances. The focus is on understanding the steps involved in launching instances, configuring a load balancer, and verifying load balancing functionality.

## Steps Taken

1. **Launching EC2 Instances:**
   - Launched two EC2 instances using Amazon Linux 2 on t2.micro.
   - Used EC2 user data to set up instances:
    ```
    #!/bin/bash
    yum update -y
    yum install -y httpd
    systemctl start httpd
    systemctl enable httpd
    echo "<h1>Hello World from $(hostname -f)</h1>" >/var/www/html/index.html
    ```
   - Assigned existing security group (Launch Wizard 1) allowing HTTP and SSH traffic.

2. **Testing EC2 Instances:**
   - Accessed both instances individually via their IPv4 addresses.
   - Verified the "hello world" response from each instance.

3. **Creating an Application Load Balancer (ALB):**
   - Created an ALB named "tech242-bianca-second-vm-lb"
   - Deployed the ALB in all available availability zones.
   - Configured a new security group (tech242-bianca-second-vm-sg-lb) allowing HTTP traffic.
   - Created a target group (tech242-bianca-tg-alb) for instances, defining HTTP on port 80.
   - Registered both EC2 instances with the target group.

4. **Verifying Load Balancer Functionality:**
   - Checked ALB status, ensuring it transitioned to the "active" state.
   - Accessed the ALB's DNS name in a browser.
   - Observed load balancing in action by refreshing the page multiple times.
   - Monitored the target group to see changes in target health based on instance status:
  ![LB Status](<../../../readme-images/ELB & ASG/lb target status.png>)
   - Demonstrated automatic routing of traffic to healthy instances.