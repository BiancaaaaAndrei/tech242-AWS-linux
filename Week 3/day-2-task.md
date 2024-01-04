# Write a Bash script to add a scary cat image to the JSONVoorhees app's home page

## Pre-requisites
You will need an EC2 instance running the JSONVoorhees Java-Atlas app

## Step 1: Do it manually
- Find a scary cat image on the web (either jpeg, jpg, or png)
- Download it onto your VM
```
wget -O ~/downloads/cat.jpg https://thumbs.dreamstime.com/blog/2018/10/halloween-creatures-black-cat-28124-image128519233.jpg

```
- Upload it to S3 storage to your own bucket
```
aws s3 cp cat.jpg s3://tech242-bianca-first-bucket
```

- Set permissions to make your uploaded scary cat image publicly accessible
```
Follow the permissions steps from [S3 Introduction](s3.md)
```
- Modify the JSONVoorhees home page (at /web/home) to include the scary cat image saved & use Maven command(s) to see the changes take effect in your refreshed web browser tab
```
Go to cd home/ubuntu

Then cd /tech242-jsonvoorhees-app/app/springapi/src/main/resources/templates

sudo sed -i 's|<img src="/images/friday13th.jpg" alt="friday13thposter">|<img src="https://tech242-bianca-first-bucket.s3.eu-west-1.amazonaws.com/cat.jpg" alt="friday13thposter">|g' /tech242-jsonvoorhees-app/app/springapi/src/main/resources/templates/home.html

cd /tech242-jsonvoorhees-app/app/springapi use this command: sudo mvn package

```

NB! if the homepage is not running, try sudo mvn spring-boot:start
NB! be on this path: /tech242-jsonvoorhees-app/app/springapi/src/main/resources/templates whn accessing the sudo nano home.html

### Final result:

![Result](<../readme-images/result manual.png>)

## Step 2: Automate
### Task A: Create a Bash script called use-s3-image-on-homepage.sh to upload the scary cat image to S3, set permissions for public access, modify the app code to use to uploaded image, and run the app

- Deleted the cat.jpg from Step 1 on both downloads folder and bucket for a fresh start.
- Went back in the bash terminal and created a new sh file in root called use-s3-image-on-homepage.sh and pasted the following script:

```
#!/bin/bash

#Download the image
sudo wget https://thumbs.dreamstime.com/blog/2018/10/halloween-creatures-black-cat-28124-image128519233.jpg

#Change the img name
sudo mv halloween-creatures-black-cat-28124-image128519233.jpg cat.jpg

#Copy the cat.jpg to the bucket
aws s3 cp cat.jpg s3://tech242-bianca-first-bucket

#Configure the block access
aws s3api put-public-access-block --bucket tech242-bianca-first-bucket --public-access-block-configuration BlockPublicAcls=false,IgnorePublicAcls=false,BlockPublicPolicy=false,RestrictPublicBuckets=false
echo "Done!"
echo ""

#Enable object ownership for bucket
aws s3api put-bucket-ownership-controls \
 --bucket tech242-bianca-first-bucket \
 --ownership-controls '{
    "Rules": [
        {
            "ObjectOwnership": "BucketOwnerPreferred"
        }
    ]
 }'
echo "Done!"
echo ""

#Give public access to the object
aws s3api put-object-acl --bucket tech242-bianca-first-bucket --key cat.jpg --acl public-read

#Change the initial image on home to the cat.jpg
sudo sed -i 's|<img src="/images/friday13th.jpg" alt="friday13thposter">|<img src="https://tech242-bianca-first-bucket.s3.eu-west-1.amazonaws.com/cat.jpg" alt="friday13thposter">|g' /tech242-jsonvoorhees-app/app/springapi/src/main/resources/templates/home.html

cd /tech242-jsonvoorhees-app/app/springapi - use this if necessary

#Run Maven to see the changes
sudo mvn package

```

- sudo sed -i 's|<img src="/images/friday13th.jpg" alt="friday13thposter">|<img src="https://tech242-bianca-first-bucket.s3.eu-west-1.amazonaws.com/cat.jpg" alt="friday13thposter">|g' /tech242-jsonvoorhees-app/app/springapi/src/main/resources/templates/home.html - to change the initial image with the one that we want

- go back in the /tech242-jsonvoorhees-app/app/springapi: sudo mvn package - for the changes to be seen on the home page


### Task B: Create a Bash script called revert-to-normal-homepage.sh to reverse the changes to the app code, remove the uploaded image from S3 storage, and re-run the app

- Went back in the bash terminal and created a new sh file in root called revert-to-normal-homepage.sh and pasted the following script:

```
#!/bin/bash

# Revert changes to the app code
sudo sed -i 's|<img src="https://tech242-bianca-first-bucket.s3.eu-west-1.amazonaws.com/cat.jpg" alt="friday13thposter">|<img src="/images/friday13th.jpg" alt="friday13thposter">|g' /tech242-jsonvoorhees-app/app/springapi/src/main/resources/templates/home.html

# Remove the uploaded image from S3 storage
aws s3 rm s3://tech242-bianca-first-bucket/cat.jpg

# Remove the S3 bucket (use with caution)
aws s3 rb s3://tech242-bianca-first-bucket --force

# Re-run the app
cd /tech242-jsonvoorhees-app/app/springapi
sudo mvn package

```

### Final result:

![Reverse](<../readme-images/reserve result.png>)