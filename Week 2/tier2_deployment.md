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



