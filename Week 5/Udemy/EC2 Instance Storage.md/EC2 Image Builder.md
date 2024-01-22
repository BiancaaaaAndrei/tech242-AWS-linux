# EC2 Image Builder

## Introduction

- **Purpose:** Used to automate the creation of Virtual Machines, or container images.
- That means that you're gonna be able with EC2 Image Builder to automate the creation, maintain, validate, and test AMIs for EC2 instances.


## Diagram

- #### So we have the EC2 Image Builder service
![EC2 Image Builder](<../../../readme-images/ec2 image builder/EC2 Image builder.png>)

- #### Automatically when it's running, is going to create an EC2 Instance called the **Builder EC2 Instance**. That EC2 Instance is going to build components and customize the software. For example, install Java, update the CLI, update the software system, maybe install firewalls, whatever you define to happen on that EC2 Instance, maybe install your application.
![Instance Builder](<../../../readme-images/ec2 image builder/builder.png>)

- #### Once this is done, then an AMI is going to be created out of that EC2 Instance, but all of this is obviously automated. 
![New AMI](<../../../readme-images/ec2 image builder/new ami.png>)

- #### Then the AMI is created, but we want to validate it. So EC2 Image Builder will automatically create a test EC2 Instance from that AMI and going to run a bunch of tests that you are defining in advance. And if you don't wanna run any tests obviously you can just skip that test, but the test can be asking
  - #### Is the AMI working?
  - #### Is it secure?
  - #### Is my application running correctly?
![Test Instance](<../../../readme-images/ec2 image builder/test.png>)

- #### Once the AMI is tested, then the AMI is going to be distributed, so while EC2 Image Builder is a regional service it is possible for you to take that AMI and distribute it to multiple regions, therefore, allowing your application and your workflow to be truly global.
![AMI Distribution](<../../../readme-images/ec2 image builder/amidistributed.png>)

- #### Next, EC2 Image Builder can be run on a schedule:
  - So you can define a weekly schedule, or you can say you can run whenever packages are updated, or you can run it manually. 
  - It is a free service - only going to pay for the underlying resources. **What does that mean?** Means that if you create an EC2 Instance during this process, an EC2 Image Builder will create these EC2 Instances, then you're going to pay for these EC2 Instances. And when the AMI is created and distributed you're going to pay for the storage of that AMI wherever it has been created, and wherever it has been distributed.