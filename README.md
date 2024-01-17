# Cloud Computing week by week material

- [Cloud Computing week by week material](#cloud-computing-week-by-week-material)
- [Week 1](#week-1)
  - [Intro into Cloud \& AWS](#intro-into-cloud--aws)
  - [First Virtual Machine \& Linux Intro](#first-virtual-machine--linux-intro)
  - [Linux permissions, managing processes, environment variable, making/running scripts](#linux-permissions-managing-processes-environment-variable-makingrunning-scripts)
  - [Deploying an application](#deploying-an-application)
  - [Setting up Apache Web Server and Configuring Reverse Proxy](#setting-up-apache-web-server-and-configuring-reverse-proxy)
  - [AMI](#ami)
- [Week 2](#week-2)
  - [JsonVoorheese Automated Script with Reverse Proxy](#jsonvoorheese-automated-script-with-reverse-proxy)
  - [Tier 2 Individual Project](#tier-2-individual-project)
  - [AWS VPC](#aws-vpc)
- [Week 3](#week-3)
  - [Introduction to AWS S3](#introduction-to-aws-s3)
  - [Task: Write a Bash script to add a scary cat image to the JSONVoorhees app's home page](#task-write-a-bash-script-to-add-a-scary-cat-image-to-the-jsonvoorhees-apps-home-page)
    - [Monitoring and alert management in AWS \& Auto-scalling groups](#monitoring-and-alert-management-in-aws--auto-scalling-groups)
    - [Alert Management](#alert-management)
- [Week 4](#week-4)
    - [Setup the SSH to push to GitHub](#setup-the-ssh-to-push-to-github)
    - [CICD Research](#cicd-research)
    - [Jenkins basics and tasks](#jenkins-basics-and-tasks)
- [Week 5 - Udemy Courses and Tasks](#week-5---udemy-courses-and-tasks)
    - [Horizontal scalling of EC2 Instances using Auto-Scaling Group with an Application Load Balancer](#horizontal-scalling-of-ec2-instances-using-auto-scaling-group-with-an-application-load-balancer)
    - [IAM](#iam)


# Week 1
## Intro into Cloud & AWS

- What is cloud computing?
     - Cloud computing is a technology that lets you access and use computing resources over the internet, like storage and processing power, without needing physical hardware. 
     - It provides flexibility, scalability, and cost-efficiency, revolutionizing how individuals and businesses manage and deploy digital services.
     - For a more detailed explanation, please go to [Cloud Basics](<Week 1/Day1-resources/cloud-more-info.md>)
- What is AWS?
     - AWS, or Amazon Web Services, is a popular cloud computing platform provided by Amazon. 
     - A set of online services and tools that can be used to build and run applications without having to invest in physical servers.
     - For a more detailed explanation, please go to [AWS Basics](<Week 1/Day1-resources/aws-basics.md>)

## First Virtual Machine & Linux Intro

- [Creating the first virtual machine](<Week 1/Day2-resources/how-to-create-vm.md>)
- [Research into managing file ownership](<Week 1/Day2-resources/file-ownership.md>)

## Linux permissions, managing processes, environment variable, making/running scripts

- [LINUX basics](<Week 1/Day2-resources/LINUXcommands.md>)
    - Linux permissions dictate the level of access and control users, groups, and others have over files and directories. 
    - Each permission set includes read, write, and execute capabilities, enabling precise control over file interactions and executions.


- [Managing Processes](<Week 1/Day3-resources/Processes.md>)
    - Managing processes in Linux involves controlling the execution of programs, monitoring system resources, and prioritizing tasks. 
    - Linux provides commands and utilities to start, stop, and monitor processes, allowing users to efficiently allocate system resources and maintain system stability.

- [Environment Variables](<Week 1/Day3-resources/Environment_Variables.md>)
    - Environment variables in Linux are dynamic values that affect the behavior of processes and programs. 
    - They store configuration information, such as system paths and settings, influencing how applications operate and interact with the system environment.

- [Running Scripts](<Week 1/Day3-resources/Creating_RunningScript.md>)
    - Creating and running scripts in Linux involves writing executable text files containing a series of commands or programming instructions. 

- [How to manually install dependencies in Lunux and creating a script](<Week 1/Day4-resources/manually-install-dependencies-linux.md>)

## Deploying an application
- [The processes of deploying an application](<Day 5/process_of_deploying.md/process_of_deploying_main.md>)
    - Deploying an application involves the systematic set of tasks to make software accessible and operational. From preparing the environment to ensuring seamless execution, deployment encompasses steps like code integration, configuration, and, often, automation. This process ensures a smooth transition from development to production, enabling users to interact with the application reliably.

## Setting up Apache Web Server and Configuring Reverse Proxy
- [Setting up Apache Web Server and Configuring Reverse Proxy Script and Steps](<Week 1/Day5-resources/Day5.md>)
- [Reversed Proxy Version 2](<Week 2/second_method_reversed_proxy.md>)

## AMI
- [Create an AMI](<Week 1/Day5-resources/create_ami.md>)
- [AMI example script for the WorldProject](<Week 2/ami.md>)


# Week 2

## JsonVoorheese Automated Script with Reverse Proxy
- [JsonVoorheese Script](<Week 2/app_code_automation_script.md>)
  
## Tier 2 Individual Project
- [Step by step on how I automated the app code virtual machine](<Week 2/tier2_deployment.md>)
- [Database Automated Script](<Week 2/DB_automation_script.md>)

## AWS VPC
- [Introduction to AWS VPC's](<Week 2/AWS VPC's.md>)
- [Steps to set up a VPC](<Week 2/Steps_VPC.md>)


# Week 3

## Introduction to AWS S3
- [Basics of AWS S3 and steps](<Week 3/s3.md>)

## Task: Write a Bash script to add a scary cat image to the JSONVoorhees app's home page
- [Full explanation of the exercise requirements + full working scripts](<Week 3/day-2-task.md>)

### Monitoring and alert management in AWS & Auto-scalling groups
- [Monitoring & Alert Management](<Week 3/day 5-monitoring-alert-manag.md>)
- [Auto-scalling groups](<Week 3/day-5-autoscalling-groups.md>)

### Alert Management
[How to create a CPU alert](<Week 4/create-alarm.md>)


# Week 4

### Setup the SSH to push to GitHub
[Ssh-Github](<Week 4/ssh-github.md>)

### CICD Research
[CICD](<Week 4/CICD.md>)

### Jenkins basics and tasks
[Jenkins](<Week 4/Jenkins-task.md>)


# Week 5 - Udemy Courses and Tasks

### Horizontal scalling of EC2 Instances using Auto-Scaling Group with an Application Load Balancer
[Udemy](<Week 5/Udemy Horizontal Scaling Task/udemy_horizontal-scalling_task.md>)

### IAM 
- [IAM Users and Groups](<Week 5/Udemy/IAM/Users-and-Groups.md>)
- [IAM Create Users in AWS](<Week 5/Udemy/IAM/Create-Users.md>)
- [IAM Policies Inheritance and Structure](<Week 5/Udemy/IAM/Policies-Inheritance.md>)


NB! Redundancy - having copies of the data in mutiple places!
