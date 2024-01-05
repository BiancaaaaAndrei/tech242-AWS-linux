## How to manually install Java-Atlas app dependencies:

## Step 1: Create a file
```
nano prov-app.sh
```

## Step 2: Create the draft of the process by commenting out each step before implementing it:


    2  sudo apt update -y
    3  sudo apt upgrade -y
    4  sudo apt install maven -y
    6  mvn -version
    7  sudo apt install openjdk-17-jdk -y
   12  java -version
   13  sudo DEBIAN_FRONTEND=noninteractive apt install openjdk-17-jdk -y
   14  sudo DEBIAN_FRONTEND=noninteractive apt install maven -y
   15  scp -i ~/.ssh/tech242.pem ~/Desktop/test.txt ubuntu@public-key:~
16. $ scp -i ~/.ssh/tech242.pem -r ~/Desktop/test ubuntu@34.245.11.198:~


  37  nano prov-app.sh
   38  ls
   39  cd tech242-jsonvoorhees-app
   40  ls
   41  cd app
   42  ls
   43  cd springapi/
   44  mvn spring-boot: run

ubuntu@ip-172-31-55-249:~$ cd tech242-jsonvoorhees-app/app/springapi
ubuntu@ip-172-31-55-249:~/tech242-jsonvoorhees-app/app/springapi$ mvn spring-boot:start


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
git clone git@github.com:BiancaaaaAndrei/tech242-jsonvoorhees-app.git

# cd into the right folder & run the app
cd tech242-jsonvoorhees-app/app/springapi
mvn spring-boot:start




