# AWS ECS, Fargate, and ECR 

## AWS ECS (Elastic Container Service)

- **What is it?** A service to run Docker containers on AWS.
- **How does it work?** Users provision EC2 instances in advance, and ECS manages container placement on these instances.
- **Integration:** Works with an application balancer for web applications.

![ECS Service](<../../../readme-images/other compute services/ecs.jpeg>)

## AWS Fargate

- **What is it?** Another way to run Docker containers on AWS.
- **How does it work?** No need to provision infrastructure; AWS runs containers based on specified CPU and RAM requirements.
- **Simplicity:** Serverless offering, easier to use compared to ECS.

![Fargate](<../../../readme-images/other compute services/fargate.jpeg>)

## AWS ECR (Elastic Container Registry)

- **What is it?** A private Docker registry on AWS to store container images.
- **How does it work?** Images stored in ECR are used to run containers on ECS or Fargate.

![ECR](<../../../readme-images/other compute services/ecr.jpeg>)

## ECS vs. Fargate vs. ECR

- **ECS:** Users manage EC2 instances, suitable for those wanting more control.
- **Fargate:** Serverless, no need to manage EC2 instances, simpler user experience.
- **ECR:** Stores Docker images securely for ECS and Fargate.
