## Step 1. Update the package repository:
```
sudo apt update
```

## Step 2. Install MySQL server:
```
sudo apt install mysql-server
```

## Step 3. Check status MySQL
```
sudo service mysql status
```
![SQL Status](<../readme-images/project/mysql status.png>)

## Step 4. Download SQL from repo
Made a separate repo on GitHub for my database and my code. At that time was the best approach to be more effective with the task.
```
git clone https://github.com/BiancaaaaAndrei/tech242-2-tier-deploy-with-world-api-database.git
```

## Step 5. Connect to the database
```
sudo mysql -h localhost -P 3306 -u root -p
```
- -h localhost: Specifies the host where the MySQL server is running. In this case, it's set to localhost, indicating that the MySQL server is on the same machine.
- -P 3306: Specifies the port number on which the MySQL server is listening. The default MySQL port is 3306, so this part of the command is specifying the standard port.
- -u root: Specifies the MySQL user to connect as. In this case, it's set to the root user.
- -p: This option prompts you for the password after executing the command. It's a security measure to prevent unauthorized access. 


## Step 6. Show the database
```
source tech242-2-tier-deploy-with-world-api-database/world.sql
```

```
SHOW DATABASES;
```

```
SHOW TABLES;
```

## Step 7. Open the MySQL configuration file for editing:
```
sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf
```


## Step 8. Allow connections
Find the line that starts with bind-address and set it to allow connections from any address, so change the numbers to 0.0.0.0. 

Then save it and exit the file. On command like put the following:
```
sudo sed -i 's/^bind-address\s*=\s*127\.0\.0\.1/bind-address = 0.0.0.0/' /etc/mysql/mysql.conf.d/mysqld.cnf
```

## Step 9. Restart the MySQL service to apply the changes:
```
sudo service mysql restart

```

## Step 10. Ensure that the MySQL user root can connect from any host. Log in to MySQL:
```
sudo mysql -u root -p
```

The password is root.

## Step 11. Create a new user or alter it's password. Both should be root!

Create user: ```CREATE USER 'root'@'%' IDENTIFIED BY 'root';```
Alter password: ```ALTER USER 'root'@'%' IDENTIFIED BY 'root';```

## Step 12. Grant all privileges:
```GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' WITH GRANT OPTION;```
```FLUSH PRIVILEGES;```
```EXIT;```

## Step 13. Create another Virtual Machine

## Step 13. 
```sudo apt-get update```
```sudo apt-get install mysql-client```

## Step 14. Connect it to the Database VM 
```mysql -h <hostname_or_ip> -u <username> -p```

## Step 15. Make sure it's connected
```SHOW DATABASES;```

## Clone repo
```git clone https://github.com/BiancaaaaAndrei/tech242-2-tier-deploy-with-world-api.git```

## Navigate to the Application Directory:
```cd tech242-2-tier-deploy-with-world-api/WorldProject```


## Set the environment variables:
```
export DB_HOST=3.253.53.2
export DB_USER=root
export DB_PASS=root
```

## Verify that the environment variables are set correctly:
```
echo $DB_HOST
echo $DB_USER
echo $DB_PASS
```

## If you are using sudo to run your Maven command, use the -E flag to preserve the environment variables:

```sudo apt-get update```
```sudo DEBIAN_FRONTEND=noninteractive apt-get install maven -y ```
```sudo -E mvn clean install``` (failure in loading the application context during the testing phase):

- I did the following to solve it:
    - Check Test Class and Configuration: Look into the CountryLaguageTests test class and make sure that the configuration is correct. Ensure that it is annotated with @SpringBootTest and that any required configurations are set up properly.

- Changed the DB_Host to: 
```export DB_HOST=jdbc:mysql://3.253.53.2:3306/world```
- Then made sure it's the correct variable: 
- ```printenv DB_USER```
- This keeps the variables too: 
  ```sudo -E mvn package spring-boot:start``` (now this works)

## Reversed Proxy:

```
#!/bin/bash
# Nav back to root
cd /
 
# Install Apache2
sudo DEBIAN_FRONTEND=noninteractive apt install apache2 -y
 
# Enable relevant apache proxy modules
sudo a2enmod proxy
sudo a2enmod proxy_http
 
# Restart Apache
sudo systemctl restart apache2
 
# Edit config file if not configured
if grep -q 'ProxyPass / http://localhost:5000/' /etc/apache2/sites-available/000-default.conf; then
    # The string exists, so nothing to do
    echo "Reverse proxy already configured."
else
    # reverse proxy not configured yet
    echo "Reverse proxy NOT configured."
    sudo sed -i '/DocumentRoot \/var\/www\/html/ a\ProxyPreserveHost On\nProxyPass \/ http:\/\/localhost:5000\/\nProxyPassReverse \/ http:\/\/localhost:5000\/\n' /etc/apache2/sites-available/000-default.conf
fi
 
# Restart Apache
sudo systemctl reload apache2

```










