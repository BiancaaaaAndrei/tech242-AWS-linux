## Step 1. Create the VPC

### Go into the EC2 in AWS and in the search bar, look for VPC and choose the first option:

![VPC Creation](../readme-images/today!/vpc.png)

### Choose "Create VPC"

![VPC](<../readme-images/today!/Screenshot 2023-12-22 113633.png>)

### We have to provide appropiate name for our VPC and CIDR has to be on manual:

![VPC Creation](<../readme-images/today!/create vpc.png>)

### VPC succesfully created

![VPC Created](<../readme-images/today!/when created .png>)


## Step 2. Create 2 subnets: public and private

### First connect it to the correct VPC:

![Subnet](<../readme-images/today!/Screenshot 2023-12-22 114152.png>)

### Create first subnet:
![Subnet](../readme-images/today!/subnet.png)

### Create second subnet:
![Subnet](<../readme-images/today!/second subnet.png>)


## Step 3. Internet Gateway

### Create a new internet gateway and provide appropriate name to it.

## Step 4. Attach an Internet Gateway to the VPC

![Alt text](<../readme-images/today!/internet gateway as a tag.png>)


## Step 5. Create the Public IP 


## Step 6. Public route table

### Create new route:

![Alt text](../readme-images/today!/rt.png)

## Step 7. Associate the route with subnet

### When you successfully created the route:

![Associate](<../readme-images/today!/associate subnet.png>)

### Go down and press "Subnet associations"

![Alt text](<../readme-images/today!/edit rounted for s6.png>)

### Select the subnet, in our case the public subnet:

![Alt text](<../readme-images/today!/rt sunet public.png>)


## Step 8. Add Internet Gateway to the route

![Destination anywhere](<../readme-images/today!/destination can be to anywhere s6.png>)

## Step 9. Check that the VPC setup was set according to our expectations

![Check](<../readme-images/today!/checking a.png>)
![Check](../readme-images/today!/checkb.png)

## Step 10. Create the Database VM

![Security Group](<../readme-images/today!/create security group for ami instance.png>)

1. SSH from My IP
2. MYSQL/Aurora, 0.0.0.0/0 (Security Group)
   
## Step 11. Create the API VM

1. SSH from My IP
2. HTTP from Anywhere

- Needs the User Data. The user data I have used for this example:

```

#!/bin/bash
 
DATABASE_IP= 
 
echo "Setup environment variables for app..."
echo "Step 1: DB_HOST..."
export DB_HOST=jdbc:mysql://$DATABASE_IP:3306/world
echo "Step 1: Done!"
# Security warning: Should not be hard coding database credentials
echo "Step 2: DB_USER..."
export DB_USER=root
echo "Step 2: Done!"
echo "Step 3: DB_PASS..."
export DB_PASS=root
echo "Step 3: Done!"
echo "Done!"
echo ""
 
echo "Run app in background..."
cd repo/WorldProject
# No need to do mvn package with AMI
#sudo -E mvn package
sudo -E mvn spring-boot:start

```