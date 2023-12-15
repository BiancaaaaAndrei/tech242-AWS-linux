This script essentially sets up a development environment by installing Maven, Java, and cloning a Git repository. Additionally, it configures an Apache reverse proxy to forward requests from a specified domain to a target IP and port. 

## Step 1 
Use the following script as a base:
```
#!/bin/bash

# Update package information
sudo apt update -y

# Upgrade installed packages
sudo DEBIAN_FRONTEND=noninteractive apt upgrade -y

# Install Maven
sudo DEBIAN_FRONTEND=noninteractive apt install maven -y

# Check if Maven is installed
mvn -version

# Install JDK (Java) 17
sudo DEBIAN_FRONTEND=noninteractive apt install openjdk-17-jdk -y

# Check if Java is installed
java -version

# Git clone the repository
git clone https://github.com/BiancaaaaAndrei/tech242-jsonvoorhees-app.git

# Change directory to the application folder
cd tech242-jsonvoorhees-app/app/springapi

# Start the Spring Boot application using Maven
mvn spring-boot:start

``` 

## Step 2
Muanually test the following:

# Define variables for Apache reverse proxy configuration
```
DOMAIN=$(curl ifconfig.me)
TARGET_IP=$(curl ifconfig.me)
TARGET_PORT="5000"
```

# Install Apache
``` 
sudo DEBIAN_FRONTEND=noninteractive apt install apache2 -y
``` 

# Enable necessary Apache modules for proxying
``` 
sudo a2enmod proxy
sudo a2enmod proxy_http
sudo a2enmod proxy_balancer
sudo a2enmod lbmethod_byrequests
``` 

# Create a virtual host configuration file for reverse proxy
sudo tee /etc/apache2/sites-available/reverse-proxy.conf > /dev/null <<EOL
<VirtualHost *:80>
    ServerName $DOMAIN

    ProxyPreserveHost On
    ProxyPass / http://$TARGET_IP:$TARGET_PORT/
    ProxyPassReverse / http://$TARGET_IP:$TARGET_PORT/

    ErrorLog \${APACHE_LOG_DIR}/error.log
    CustomLog \${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
EOL

# Enable the virtual host
``` 
sudo a2ensite reverse-proxy
``` 

# Reload Apache to apply changes
``` 
sudo systemctl reload apache2
``` 

## Step 3
Combine both scripts and then write down the commands:
```
cat automation.sh
chmod u+x automation.sh
./automation.sh

```

