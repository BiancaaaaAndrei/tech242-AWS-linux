# Create our first jobs on Jenkins

## 1. Change directory into the .ssh folder
```
cd .ssh
```

## 2. Generate an SSH key
```
ssh-keygen -t rsa -b 4096 -C "biancaaandrei@yahoo.com"
```
### Enter file in which to save the key (/c/Users/bianc/.ssh/id_rsa) and write down the ssh file name: 

```
bianca-jenkins-2-github-jsonvh
```

### Push enter for the passphrase

### Go on GitHub and add the deploy key in the tech242-jsonvoorhees-app repo:
Go on the tech242-jsonvoorhees-app repo> settings > deploy Keys > add deploy key > put the details > allow access

### Go and log into Jenkins

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