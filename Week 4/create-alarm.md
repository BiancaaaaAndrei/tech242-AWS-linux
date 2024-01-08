# Setting up a CPU usage alarm using the AWS Management Console

### To create an alarm based on CPU usage
Open the CloudWatch console at https://console.aws.amazon.com/cloudwatch/.

### In the navigation panel, choose Alarms, All Alarms.

### Choose Create alarm.

### Choose Select metric.

### In the All metrics tab, choose EC2 metrics.

### Choose a metric category (Per-Instance Metrics).

### Find the row with the instance that you want listed in the InstanceId column and CPUUtilization in the Metric Name column. Select the check box next to this row, and choose Select metric.

![Alt text](<../readme-images/Create alarm/x.png>)

### Under Specify metric and conditions, for Statistic choose Average, choose one of the predefined percentiles, or specify a custom percentile.

### Choose a period (I chose 1 minute for this exercise).

### Under Conditions, specify the following:

#### For Threshold type, choose Static.

![Alt text](<../readme-images/Create alarm/xxx.png>)

### Choose Next.

### Under Notification, choose In alarm and select an SNS topic to notify when the alarm is in ALARM state

![Alt text](<../readme-images/Create alarm/xxxx.png>)

### To have the alarm send multiple notifications for the same alarm state or for different alarm states, choose Add notification.

![Alt text](<../readme-images/Create alarm/xxxxx.png>)

### When finished, choose Next.

### Enter a name and description for the alarm. Then choose Next.

![Alt text](<../readme-images/Create alarm/xxxxxx.png>)

### Under Preview and create, confirm that the information and conditions are what you want, then choose Create alarm.

### Accept the subscription via email:

![Alt text](<../readme-images/Create alarm/WhatsApp Image 2024-01-08 at 14.34.58 (1).jpeg>)

### Email Outcome:

![Alt text](<../readme-images/Create alarm/WhatsApp Image 2024-01-08 at 14.34.58.jpeg>)
![Alt text](<../readme-images/Create alarm/WhatsApp Image 2024-01-08 at 14.34.59.jpeg>)



