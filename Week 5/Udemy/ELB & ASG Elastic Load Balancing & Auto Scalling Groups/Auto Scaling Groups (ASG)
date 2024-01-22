# Auto Scaling Groups (ASG) 

- [Auto Scaling Groups (ASG)](#auto-scaling-groups-asg)
  - [Introduction](#introduction)
  - [Key Concepts](#key-concepts)
- [Creating Auto Scaling Group and Load Balancer Integration](#creating-auto-scaling-group-and-load-balancer-integration)
  - [Introduction](#introduction-1)
  - [Steps to Create Auto Scaling Group](#steps-to-create-auto-scaling-group)
- [Auto Scaling Group - Scaling Strategies](#auto-scaling-group---scaling-strategies)
  - [Introduction](#introduction-2)
  - [Scaling Policies within Dynamic Scaling](#scaling-policies-within-dynamic-scaling)
  - [Benefits of Dynamic Scaling](#benefits-of-dynamic-scaling)

## Introduction

In this section, we'll explore Auto Scaling Groups (ASG) and understand their role in managing and maintaining the desired number of EC2 instances based on the changing load in the cloud environment.

## Key Concepts

1. **Why Use Auto Scaling Groups:**
   - Real-world website traffic can vary throughout the day.
   - ASG helps to automatically scale out (add instances) or scale in (remove instances) based on demand.
   - Ensures minimum and maximum instances are maintained.
   - Improves cost efficiency by dynamically adjusting capacity.

2. **Benefits of Auto Scaling Groups:**
   - **Scalability:** Easily handle changes in demand.
   - **Availability:** Maintain desired capacity and replace unhealthy instances.
   - **Cost Savings:** Optimize capacity to meet demand efficiently.

3. **Auto Scaling Group Components:**
   - **Minimum Size:** The minimum number of instances to be maintained.
   - **Desired Capacity:** The actual size of the group, usually set to the current number of instances.
   - **Maximum Size:** The maximum number of instances allowed.
![ASG Diagram](<../../../readme-images/ELB & ASG/ASG.jpeg>)

4. **Integration with Load Balancer:**
   - Auto Scaling Groups work hand in hand with Load Balancers.
   - As the group scales out, new instances are registered with the Load Balancer.
   - Traffic is distributed among instances by the Load Balancer.
![ASG with LB](<../../../readme-images/ELB & ASG/ASG with LB.jpeg>)

# Creating Auto Scaling Group and Load Balancer Integration

## Introduction

In this section, we'll explore the practical implementation of an Auto Scaling Group (ASG) and understand how it dynamically adjusts the number of EC2 instances based on demand. We'll also observe the integration of ASG with a Load Balancer for effective traffic distribution.

## Steps to Create Auto Scaling Group

1. **Terminating Existing Instances:**
   - Terminate existing instances to demonstrate the Auto Scaling Group's ability to manage and replace instances automatically.

2. **Creating a Launch Template:**
   - Navigate to Auto Scaling Groups and create a new ASG called tech242-bianca.
   - Create a new Launch Template named tech242-bianca-lt.
   - Define the launch template settings, including the Amazon Linux 2 AMI, instance type (e.g., t2.micro), security group, and user data script.

3. **Configuring ASG Details:**
   - Choose the VPC and subnets for launching instances > Choose all of them.
   - Specify the Load Balancer integration, selecting the existing Application Load Balancer (ALB) and target group.
   - Configure health checks and associate them with the Load Balancer.

4. **Scaling Configuration:**
   - Set the desired capacity to the number of instances you want (e.g., 2).
   - Define minimum and maximum capacities (e.g., 1 and 4).
   - Optionally configure scaling policies for advanced scenarios.

5. **Review and Create:**
   - Review the ASG configuration settings.
   - Create the ASG.

6. **Observing Auto Scaling:**
   - Monitor the ASG activity to observe the launch of new instances:
![Activity ASG](<../../../readme-images/ELB & ASG/activity asg.png>)
![Instance Management](<../../../readme-images/ELB & ASG/instance management.png>)
   - Verify that new instances are automatically registered with the Load Balancer:
![instances with lb](<../../../readme-images/ELB & ASG/instances with lb.png>)
   - Test the Load Balancer DNS to confirm traffic distribution among instances.

7. **Instance Termination Simulation:**
   - Terminate one instance manually.
   - Observe ASG's response by launching a new instance:
![Activity History](<../../../readme-images/ELB & ASG/Activity History.png>)

# Auto Scaling Group - Scaling Strategies

## Introduction

While manual adjustments to ASG capacity are possible, the real power lies in dynamic scaling strategies that respond to changing demands automatically. AWS provides different types of scaling policies within Dynamic Scaling.

## Scaling Policies within Dynamic Scaling

1. **Simple Scaling:**
   - Triggered by CloudWatch alarms.
   - Example: Add two units to capacity when CPU utilization exceeds 70% for five minutes. Remove one unit when CPU utilization is less than 30% for 10 minutes.

2. **Step Scaling:**
   - Also triggered by CloudWatch alarms.
   - Allows adding or removing different capacities based on metric thresholds.
   - Provides more granular control than Simple Scaling.

3. **Target Tracking Scaling:**
   - Defines a target value for a specific metric.
   - ASG adjusts capacity to maintain the target value.
   - Example: Set a target for average CPU utilization (e.g., 40%).

4. **Scheduled Scaling:**
   - Anticipates scaling changes based on known patterns.
   - Example: Increase minimum capacity to 10 instances every Friday at 5:00 PM.

5. **Predictive Scaling:**
   - Uses Machine Learning to predict future traffic.
   - Analyzes past patterns to forecast future load.
   - Automatically provisions EC2 instances in advance to match predicted periods.
   - Ideal for time-based patterns with predictable load changes.
![Predictive Scaling](<../../../readme-images/ELB & ASG/Predictive scalability.jpeg>)

## Benefits of Dynamic Scaling

- **Automation:** Dynamic scaling eliminates the need for manual adjustments, responding automatically to changing workloads.
  
- **Efficiency:** Ensures optimal resource utilization, reducing costs during low-demand periods and accommodating increased demand seamlessly.

- **Resilience:** Automatically adjusts capacity in response to failures or unhealthy instances, enhancing application availability.



