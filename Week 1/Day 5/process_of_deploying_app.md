# Process of deploying an app

Brief project description.

## I. Manual Deployment

### Script: Created the draft of the automation process in the prev-app.sh file
The code will update and upgrade relevant packages, install Maven, JDK 17 and Git, clone the relevant repo and run the application.
``` 
#!/bin/bash

# update

# upgrade

# install maven

# check maven is installed

# install JDK (java) 17

# check java is installed

# git clone

# cd into the right folder & run the app
```

## Step 2: 
Manually verified each step of the process and made necessary adjustments to the script. Specifically, modifications were made to accommodate cases where user input was required during the installation of Maven or Java. To eliminate the need for user input, additional instructions were incorporated into the code.

Instead of:
```
sudo apt install maven -y
```

Use this:
```
sudo DEBIAN_FRONTEND=noninteractive apt install maven -y
```

## Step 3
- Created a repo on GitHub under the name of "tech242-jsonvoorhees-app". Cloned the repo into my local machine and then added the jsonvoorhees-java-atlas-app in it, making sure that the repo is not on the same path with the .ssh file due to credentials privacy. 
- Pushed the updated repo back to GitHub.

## Step 4
Updated the prov-app.sh draft with the correct commands for each process:
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

## II Automated deloyment with User Data

## Step 1
Created a new Virtual Machine following the standard procedure. The only diference was that, in the "Advanced settings," it became necessary to paste our functional automation script into the User Data box.

## Step 2
When the status of our new machine is "running" then we are ready to copy the public IP and paste it in the address bar followed by :5000, like this: 

```
publicip:5000
```

## III Automated deployment with AMI

## Step 1
Created a new VM or used our automated Virtual Machine with User Data. 

## Step 2

![Create AMI](<../../readme-images/create ami.png>)

## Step 3
Give a concrete name for the instance and make sure that every istance name WILL ALWAYS end with "-ami", such as:

![Name AMI](<../../readme-images/Name ami.png>)

## Step 4
Create or use an existent security group

## Step 5

Make sure that the Tag is "Name" and the Value is the same as the instance name!

![Tag and Value](<../../readme-images/tag ami.png>)


