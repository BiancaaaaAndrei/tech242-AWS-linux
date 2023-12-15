## How to automate install of Java-Atlas app dependencies using Bash script

This guide provides instructions on how to use a Bash script to automate the installation of dependencies for the Java-Atlas app. The script will help streamline the setup process, ensuring that all required dependencies are installed with minimal manual intervention.

- [How to automate install of Java-Atlas app dependencies using Bash script](#how-to-automate-install-of-java-atlas-app-dependencies-using-bash-script)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Step 1. Clone the Java-Atlas app repository:](#step-1-clone-the-java-atlas-app-repository)
- [Step 2. Create the path to SpringApi folder:](#step-2-create-the-path-to-springapi-folder)
- [Step 3. Start the program by using Maven:](#step-3-start-the-program-by-using-maven)
- [Final script:](#final-script)
- [Step 4. Fresh VM](#step-4-fresh-vm)
- [Step 5. Log in Bash with the new VM](#step-5-log-in-bash-with-the-new-vm)
- [Step 6. Create a new automation.sh file and copy and paste the script from Step 3!](#step-6-create-a-new-automationsh-file-and-copy-and-paste-the-script-from-step-3)
- [Step 7. Test the outcome](#step-7-test-the-outcome)


## Prerequisites

Created an automation.sh file to create the process. As usual, add the following commnads before jumping to step 1:

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
```

## Usage

## Step 1. Clone the Java-Atlas app repository:

    ```
    git clone https://github.com/BiancaaaaAndrei/tech242-jsonvoorhees-app.git
    ```

    If succesful, add the following to the automation.sh file:

    ```
    # git clone
    git clone https://github.com/BiancaaaaAndrei/tech242-jsonvoorhees-app.git

    ```

    Make sure that you copy the HTTPS url code from GitHub in order to succesfuly clone without issues! An issue occured at the beginning of the task because I have used the wrong url (SSH):

    ![Git Issue](<../../../readme-images/ussue git.png>)

## Step 2. Create the path to SpringApi folder:

    ```
       cd tech242-jsonvoorhees-app/app/springapi 
    ```

## Step 3. Start the program by using Maven:

    ```
    mvn spring-boot:start
    ```


## Final script:

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

## Step 4. Fresh VM
- Created a new Virtual Machine on AWS following the standard procedure: [create a new virtual machine](../../Day2-resources/create-vm.md). 

## Step 5. Log in Bash with the new VM

## Step 6. Create a new automation.sh file and copy and paste the script from Step 3!

## Step 7. Test the outcome
- Get the public IP from the fresh VM (can be found in AWS/EC2/Instances/find your new VM/press on its' ID)
- Insert the following in the Web Browser Address Bar in order for the automation to be tested:

```
publicIP:5000
```