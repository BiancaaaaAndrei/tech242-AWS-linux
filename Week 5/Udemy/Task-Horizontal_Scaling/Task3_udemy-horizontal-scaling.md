# Task 3: Configure CloudWatch monitoring of the EC2 instance
- Will need to create a CloudWatch alarm that monitors the EC2 instance for a hardware failure event and immediately invokes auto-recovery procedure to get the EC2 instance up and running again. Configure the CloudWatch alarms to send SNS notifications to your email address.


### 1.	Enter CloudWatch in the search bar and select CloudWatch service
 
### 2.	Expand Alarms section on the left sidebar, click on the in-alarm menu item and then click on the Create alarm button
![Alt text](../readme-images/Horizontal-scaling/t3-2.png)
 
### 3.	Click on the Select metric button
![Alt text](../readme-images/Horizontal-scaling/t3-3.png)
 
### 4.	Copy the Instance ID of the instance created in Task 1
![Alt text](../readme-images/Horizontal-scaling/t3-4.png)

### 5.	Paste this Instance ID in the search bar for Metrics and click on EC2 > Per-Instance Metrics
![Alt text](../readme-images/Horizontal-scaling/t3-5.png)
 
### 6.	Select StatusCheckFailed_System metric
![Alt text](../readme-images/Horizontal-scaling/t3-6.png)
 
### 7.	Specify metric and conditions for the alarm

a.	Select Average for Statistic and 1 minute for Period
![Alt text](../readme-images/Horizontal-scaling/t3-7a.png)
 
b.	Select threshold type, alarm condition and threshold value like so:
![Alt text](../readme-images/Horizontal-scaling/t3-7b.png)
 
### 8.	Now lets configure actions for the alarm. We shall create two actions for this alarm - a notification action (this will be used to send you an email when the EC2 instance has a hardware failure) and an EC2 action (this will be used to automatically recover the EC2 instance from a hardware failure. The failure will be simulated via the CloudWatch Alarms API for the purpose of this lab)

a.	In the Notification section, Select In alarm as the option for Alarm State Trigger, select Create new topic for SNS topic. Provide a name for the topic - Lab_EC2_Alarm. Then enter your email address as the endpoint. Click on the Create Topic button
![Alt text](../readme-images/Horizontal-scaling/t3-8a.png)
 
b.	You should see your topic created successfully
![Alt text](../readme-images/Horizontal-scaling/t3-8b.png)
 
c.	Lets create the EC2 action. Select In alarm as the option for Alarm State Trigger. Then select Recover this instance as the action type. Click on the Next button
![Alt text](../readme-images/Horizontal-scaling/t3-8c.png)
 
### 9.	Enter Lab-EC2-Recover as the alarm name and the alarm description. Click on Next
![Alt text](../readme-images/Horizontal-scaling/t3-9.png)
 
### 10.	Preview all sections for your alarm and click on the Create alarm button to complete the set up for the alarm
 
You should see that the alarm has been created successfully. However, the alarm shows up in the pending confirmation status. This is because you need to confirm the subscription for the SNS notifications that will be sent to your email.
 
### 11.	Go to your inbox for the email address youve used in Step 8a above. Click on the Confirm subscription link in the email that you have received from AWS Notifications.
![Alt text](../readme-images/Horizontal-scaling/t3-11.png)
 
 


