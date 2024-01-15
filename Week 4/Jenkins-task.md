# Create our first jobs on Jenkins

#### Change directory into the .ssh folder
```
cd .ssh
```

#### Generate an SSH key
```
ssh-keygen -t rsa -b 4096 -C "biancaaandrei@yahoo.com"
```
#### Enter file in which to save the key (/c/Users/bianc/.ssh/id_rsa) and write down the ssh file name: 

```
bianca-jenkins-2-github-jsonvh
```

#### Push enter for the passphrase

#### Go on GitHub and add the deploy key in the tech242-jsonvoorhees-app repo:
Go on the tech242-jsonvoorhees-app repo> settings > deploy Keys > add deploy key > put the details > allow access

#### Go and log into Jenkins

#### When logged in, we now have to create our first job:
- On the left side, click on the "Add Item"
- Give it a clear and concise name and choose the "Freestyle Project"

![Alt text](<../readme-images/Jenkins Steps/jenkins create job 1.png>)

#### Configure
- Follow the template:
  
![Configure](<../readme-images/Jenkins Steps/configure 1.png>)

![Alt text](<../readme-images/Jenkins Steps/configure 2.png>)

![Alt text](<../readme-images/Jenkins Steps/configure 4.png>)

#### Go on the Dashboard
- When you highlight on your fresh create job, there will be an arrow next to it. Press on the "Build Now"
![Alt text](<../readme-images/Jenkins Steps/step 3 run now jenkins.png>)
- When the Job has been completed, this is the outcome we want:
![Outcome dashboard](<../readme-images/Jenkins Steps/step 3 outcome.png>)

#### Verify the Console Output
- Press on your job
- You'll be transfered into a new page
- Click on the link presented under the "Build History" for more info regarding the Console Output:
![Alt text](<../readme-images/Jenkins Steps/step 4 seeing result click on the job.png>)
- Then Click on the "Console Output"

### Add another job to our current one:
- If we have more independent jobs but somethimes we want to combine them, then:
    - Go into your preffered job
    - Click on "Configure"
    - Add the second job by clicking on the "Add post-build action" and choose the "Build other projects"
![Alt text](<../readme-images/Jenkins Steps/step 5 this is useful to run second job within first job.png>)
    - Then try to follow the previous 3 steps that were building the jobs and verifying them/fixing any issues

## Now after we tested Jenkins, we are creating our first job for the pipeline.
#### Give it a clear and concise name:
![Create](<../readme-images/Jsonvh jobs/step1 create new pj.png>)

#### Configure the following:
- ##### Tick on Discard Old Builds and add 3
![Discard Old Builds](<../readme-images/Jsonvh jobs/2.png>)

- ##### Add the Github Project and paste the HTTPS link of our repo
![Add https Git Link](<../readme-images/Jsonvh jobs/2b.png>)

- ##### Now move on and go in the "Source Code Management" and choose Git

- ##### Go copy the SSH repo link from our repo
![Alt text](<../readme-images/Jsonvh jobs/3.png>)

- ##### And paste it here. As you can see, there is an error because we didn't provide the private SSH key to Jerkins
![Alt text](<../readme-images/Jsonvh jobs/4 bad.png>)

- ##### In the "Kind" section, choose the SSH Username with private key.Make sure that the username matches with the SSH file name!
![Alt text](<../readme-images/Jsonvh jobs/4 goo.png>)

- ##### Provide the full key! This means from the first - to the last -
![Alt text](<../readme-images/Jsonvh jobs/4 good2.png>)

- ##### Now the correct result:
![Alt text](<../readme-images/Jsonvh jobs/4 correct one now.png>)

- ##### Move on into the "Build Steps" and choose the Maven version presented bellow and name the goal as "package test"
![Alt text](<../readme-images/Jsonvh jobs/5.png>)

- ##### Before we click save, we need to click on the "Advanced" settings and provide the full path of our pom.xml file from the GitHub repo:
![Alt text](<../readme-images/Jsonvh jobs/5b.png>)

- ##### Now check if you missed anything. If not, proceed to click on Save


#### Results:
- ##### Initially we had an error:
![Alt text](<../readme-images/Jsonvh jobs/1 issue.png>)

- ##### We fixed it by:
![Alt text](<../readme-images/Jsonvh jobs/1 issue solution.png>)

- ##### When this was fixed, another problem began: there was an issue with the instace size as t2 micro wasn't ideal initially

- #### Therefore we changed the size to t2 medium and now the "Build Now" has completed.

## How to get a notification from Github to Jenkins

- ##### Change branch to dev
![change branch](<../readme-images/Jsonvh jobs/cahnge branch to dev.png>)

- ##### Make it listen by going into the "Build triggers" and choose the Github hook trigger
![listen](<../readme-images/Jsonvh jobs/make it listen.png>)

- ##### Add Webhook on github
![add wekhook](<../readme-images/Jsonvh jobs/add webhook on github.png>)

- ##### Copy the IP Address and Port from browser for Jerkins server

- ##### Go back on webhook screen and paste it: http://34.254.6.118:8080/ and add github-webhook/ and leave the rest of the settings as they are
![outcome](<../readme-images/Jsonvh jobs/webhook outcome.png>)

## Create the second job on Jenkins:
#### Requirements:
1. Name Job 2: similar to bianca-java-atlas-job2-ci-merge
2. If the tests pass on Job 1, Job 2 should run (and the code should merge from dev to main branch)
3. Recommended: Try to get Jenkins plugin to do merge, rather than use commands in the execute shell

#### Step 2:
##### Configure Settings:
![old builds](<../readme-images/Jsonvh jobs/discard old builds.png>)

![Alt text](<../readme-images/Jsonvh jobs/git project tick.png>)

![Alt text](<../readme-images/Jsonvh jobs/scm git.png>)

![branches to build](<../readme-images/Jsonvh jobs/branches to build.png>)

![Alt text](<../readme-images/Jsonvh jobs/merge before build.png>)

![Alt text](<../readme-images/Jsonvh jobs/git publisher.png>)

##### After we check that Job 2 runs, wego into our Job 1 > Configure > Post-build actions > Projects to build > put the name of Job 2 > Tick the "Trigger only if build is stable"
![step 7](<../readme-images/Jsonvh jobs/after testing if it runs, we do step 7.png>)

##### Then run Job 1 to make sure there's no issues

## Create third job
##### Copy the updated & tested code from Jenkins to the AWS EC2 instance with scp or rsync commands:
1. ##### First I created the EC2 Instance from the jsonvh app reverse proxy AMI with it's new security group (HTTP from Anywhere, ssh from Anywhere) and use the following user data:
```
#!/bin/bash
cd /repo/springapi
mvn spring-boot:start
```

2. ##### Go on Jenkins and connect Job 3 with the .pem file, also ssh into the EC2 instance:
![The pem file](<../readme-images/Jsonvh jobs/job 3/step 2.png>)
![Alt text](<../readme-images/Jsonvh jobs/job 3/step 2 build.png>)
```
uname -a
ssh -o StrictHostKeyChecking=no ubuntu@ec2-54-155-152-80.eu-west-1.compute.amazonaws.com

```

3. ##### Run the Job 3 and see if it works
4. ##### Add Job 3 in the Build Other Projects Section in Job 2 configurations
5. ##### Go back into the Job 3 configurations: Copy code from Jenkins to the AWS EC2 instance with scp; Jenkins will need to SSH into the EC2 instance to 'cd' into the 'springapi' folder, re-compile & re-run the app

```
ssh -o StrictHostKeyChecking=no ubuntu@ec2-54-155-152-80.eu-west-1.compute.amazonaws.com 'sudo chmod 777 -R /repo'
scp -o StrictHostKeyChecking=no -r ../bianca-jsonvh-job1-ci-test/app/springapi ubuntu@ec2-54-155-152-80.eu-west-1.compute.amazonaws.com:/repo
ssh -o StrictHostKeyChecking=no ubuntu@ec2-54-155-152-80.eu-west-1.compute.amazonaws.com 'cd /repo/springapi; mvn clean package spring-boot:start'

```
6. ##### In the bash terminal on the local machine, push changes into the home.html folder to update the time and then push the changes in the dev branch:

```
cd ~/Desktop/Sparta Projects/tech242-jsonvoorhees-app/app/springapi/src/main/resources/templates
```
```
nano home.html
```

```
git add .
```

```
git commit -m "updated the time and date in the home.html file"
```

```
git push origin dev

```

##### And now on Jenkins all jobs must start one by one. When the last job is done, check to see if the changes have appeared on the main page.

![Alt text](<../readme-images/Jsonvh jobs/job 3/changes.png>)


