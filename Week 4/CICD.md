# DevOps CICD Basics

## What is CI (Continuous Integration)?
- CI stands for Continuous Integration.
- Developers regularly merge code changes into a central repository.
- Goal: Detect and fix integration issues early in development.

## What is CD (Continuous Delivery/Deployment)?
- CD stands for Continuous Delivery or Continuous Deployment.
- Continuous Delivery ensures reliable and rapid delivery of code changes.
- Continuous Deployment automatically deploys code changes to production after passing tests.

## Difference between CD and CDE
- CD:
  - CD is primarily concerned with the methodology and practices involved in delivering code changes reliably and efficiently.
  - It embodies the principles of automation, testing, and structured release processes.

- CDE:
  - CDE expands the scope to include the entire ecosystem of tools, infrastructure, and components that work together to facilitate continuous deployment.
  - It aims to create an environment where the CD process operates seamlessly, allowing for frequent and reliable deployment of software changes.
  
The takeaway: In simple terms, CD is the cooking process, and CDE is having the right kitchen setup to make that process easy and successful.

- CICD Diagram:
![Diagram](../readme-images/diagram.png)

## What is Jenkins?
- An open-source automation server.
- Jenkins is a tool that helps automate tasks like building and deploying code changes.

## Advantages and Disadvantages of Jenkins

### Advantages

1. **Open Source:** Jenkins is open source, allowing easy setup on AWS instances.
2. **Time-Saving:** Automates repetitive tasks, saving time in the development lifecycle.
3. **Customization:** Offers powerful plugins for additional functionality.
4. **Cross-Platform Compatibility:** Supports Windows, macOS, and Linux.
5. **Large Community:** Benefits from a large and supportive community.

### Disadvantages

1. **Setup and Configuration:** Initial setup on AWS instances may require effort.
2. **Learning Curve:** Users may need time to become proficient.
3. **Limited Security Features:** Jenkins might lack some advanced security features.

## What alternatives are there for Jenkins?
- **Popular alternatives include:**
  - GitLab CI/CD: Integrated with GitLab, providing a complete DevOps platform.
  - Travis CI: Cloud-based CI/CD service with straightforward setup.
  - CircleCI: Cloud-based CI/CD platform with a focus on speed.

In the class discussion, various alternative tools to Jenkins were mentioned, including GitLab CI, Circle CI, Artifactory, Bamboo, and JetBrains TeamCity.

## Stages of Jenkins
- Jenkins typically involves stages such as:
  - Checkout: Fetching source code from the version control system.
  - Build: Compiling code and generating executable artifacts.
  - Test: Running automated tests to ensure code quality.
  - Deploy: Deploying the application to testing or production environments.

## Why build a pipeline? Business value?
- A pipeline helps deploy code consistently and quickly.
- It makes sure the code is good quality.
- Saves time, helps catch issues early, and gets features to users faster.

## Popular Tools for CI/CD Pipelines

The class highlighted Azure DevOps and GitHub Actions as popular tools for CI/CD pipelines. Azure DevOps is emphasized for its compatibility with private repositories, while GitHub Actions is a free and open-source option, particularly suitable for public repositories.

## GitHub Actions

GitHub Actions, as a free tool, was discussed, emphasizing its integration with GitHub and its use for CI/CD pipelines.

## Why Automate the CI/CD Pipeline

Automating the CI/CD pipeline provides several benefits, including:

1. **Time Efficiency:** Reduces time spent on repetitive tasks.
2. **Cost Effectiveness:** Saves money by streamlining processes.
3. **Code Quality:** Ensures code quality through robust testing.
4. **Error Reduction:** Minimizes errors through automated testing.
5. **Fast Feedback Cycle:** Enables quick feedback for continuous improvement.

## Business Value of DevOps

The business value of DevOps lies in its ability to:

1. **Identify Areas for Improvement:** Fast feedback cycles help identify and address improvement areas.
2. **Ensure Reliability:** Continuous testing and deployment lead to reliable applications.
3. **Create Business Value:** Deploying code to end-users quickly creates tangible business value.

## Jenkins Components

Jenkins consists of:

1. **Master Node:** Coordinates jobs and runs on a dedicated virtual machine.
2. **Agent Nodes:** Execute jobs and can be on-demand virtual machines.
3. **Plugins:** Enhance Jenkins functionality.

## CICD Pipeline Jobs

The CICD pipeline consists of three jobs:

1. **Job 1 - Test Code:** Tests code in the dev branch.
2. **Job 2 - Merge to Main:** Merges code to the main branch if Job 1 is successful.
3. **Job 3 - Deploy to AWS:** Deploys updated code to an EC2 instance if Job 2 is successful.

## Deploying to AWS with Jenkins

To deploy code to AWS with Jenkins:

1. Jenkins needs AWS credentials.
2. Jenkins requires an SSH key for GitHub authentication.
3. The EC2 instance must be running.
4. The Jenkins pipeline should include scripts for deploying code to the EC2 instance.

- Jenkins Diagram:
![Diagram](<../readme-images/jenkins diagram.png>)

## Conclusion

This README provides an overview of the CICD pipeline, alternative tools, and key concepts discussed in the class. It serves as a reference for setting up Jenkins, understanding pipeline jobs, and deploying code to AWS.


