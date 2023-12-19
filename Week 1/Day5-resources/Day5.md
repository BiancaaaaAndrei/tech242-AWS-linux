## Setting up Apache Web Server and Configuring Reverse Proxy
- A reverse proxy is a redirection mechanism that directs incoming traffic from the standard port 80 to a specified port. 
- This guide outlines the steps to add Apache Web Server to your system and configure a reverse proxy.

## Adding Apache Web Server

# Update your system
```
sudo apt update
```

# Install Apache Web Server
```
sudo apt install apache2
```

# Start Apache
```
sudo systemctl start apache2
```

# Enable Apache to start on boot
```
sudo systemctl enable apache2
```

# Check Apache status
```
sudo systemctl status apache2
```

## Reverse Proxy
# Ensure necessary modules are installed
```
sudo a2enmod proxy
sudo a2enmod proxy_http
```

# Open the Apache configuration file
```
sudo nano /etc/apache2/sites-available/000-default.conf
```

# Inside the configuration file, just above ErrorLog ${APACHE_LOG_DIR}/error.log, add:
ServerName yourdomain.com

```ProxyPass / http://localhost:5000/
ProxyPassReverse / http://localhost:5000/
```

!!! Make sure to replace yourdomain.com with your public IP and both instances of 5000 with the desired port.

# Save the configuration file

# Restart Apache to apply changes
```
sudo systemctl restart apache2
```

## Final script for User Data
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

echo "proxy setting up"
# Define variables
DOMAIN=$(curl ifconfig.me)
TARGET_IP=$(curl ifconfig.me)
TARGET_PORT="5000"

# Install Apache
sudo DEBIAN_FRONTEND=noninteractive apt install apache2 -y

# Enable necessary Apache modules
sudo a2enmod proxy
sudo a2enmod proxy_http
sudo a2enmod proxy_balancer
sudo a2enmod lbmethod_byrequests

# Create a virtual host configuration file
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
sudo a2ensite reverse-proxy

# Reload Apache to apply changes
sudo systemctl reload apache2
echo "done"
echo ""
```
## Final script for the AMI instance

```
#!/bin/bash

# cd into the right folder & run the app
cd tech242-jsonvoorhees-app/app/springapi
mvn spring-boot:start

echo "proxy setting up"
# Define variables
DOMAIN=$(curl ifconfig.me)
TARGET_IP=$(curl ifconfig.me)
TARGET_PORT="5000"

# Install Apache
sudo DEBIAN_FRONTEND=noninteractive apt install apache2 -y

# Enable necessary Apache modules
sudo a2enmod proxy
sudo a2enmod proxy_http
sudo a2enmod proxy_balancer
sudo a2enmod lbmethod_byrequests

# Create a virtual host configuration file
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
sudo a2ensite reverse-proxy

# Reload Apache to apply changes
sudo systemctl reload apache2
echo "done"
echo ""
```
