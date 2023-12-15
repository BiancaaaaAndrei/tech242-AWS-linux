## How to automate install of Java-Atlas app dependencies via User Data

This guide provides instructions on how to run an automated script via User Data.
- [How to automate install of Java-Atlas app dependencies via User Data](#how-to-automate-install-of-java-atlas-app-dependencies-via-user-data)
- [Step 1. Create a fresh Virtual Machine via AWS.](#step-1-create-a-fresh-virtual-machine-via-aws)
- [Step 2. Follow the standard procedure to create a VM:](#step-2-follow-the-standard-procedure-to-create-a-vm)
- [Step 3. Open Advanced Details:](#step-3-open-advanced-details)
- [Step 4: Look for the User Data section:](#step-4-look-for-the-user-data-section)
- [Step 4: Insert the following in the User Data:](#step-4-insert-the-following-in-the-user-data)
- [Step 7. Test the outcome](#step-7-test-the-outcome)

## Step 1. Create a fresh Virtual Machine via AWS.

## Step 2. Follow the standard procedure to create a VM:
[Create a new Virtual Machine](../../Day2-resources/create-vm.md)

## Step 3. Open Advanced Details:

![Advanced Details](<../../../readme-images/advanced details.png>)

## Step 4: Look for the User Data section:

![User Data](<../../../readme-images/user data.png>)

## Step 4: Insert the following in the User Data:

```
#!/bin/bash
 
# update
sudo apt update -y
 
# upgrade
sudo DEBIAN_FRONTEND=noninteractive apt upgrade -y
 
# install maven
sudo DEBIAN_FRONTEND=noninteractive apt install maven -y
 
# check maven is installed
mvn -version
 
# install JDK (java) 17
sudo DEBIAN_FRONTEND=noninteractive apt install openjdk-17-jdk -y
 
# check java is installed
java -version
 
# git clone
git clone https://github.com/BiancaaaaAndrei/tech242-jsonvoorhees-app.git
 
# cd into the right folder & run the app
cd tech242-jsonvoorhees-app/app/springapi
mvn spring-boot:start

```

## Step 7. Test the outcome
- Get the public IP from the fresh VM (can be found in AWS/EC2/Instances/find your new VM/press on its' ID)
- Insert the following in the Web Browser Address Bar in order for the automation to be tested:

```
publicIP:5000
```