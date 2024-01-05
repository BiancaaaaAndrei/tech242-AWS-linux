# Monitoring and alert management 

## Overview

This documentation provides an in-depth understanding of the system monitoring and alert management concepts discussed in our session. The session covers various scenarios, challenges, solutions, and best practices associated with monitoring and managing system resources.

## Scenario 1: No Monitoring

### Problem Statement

In this scenario, the absence of monitoring is identified as a critical issue. The potential consequences include system overload, service interruptions, and unresponsiveness, particularly during periods of sudden traffic spikes.

### Challenges

- Lack of visibility into system metrics.
- Inability to anticipate and address performance issues.
- Potential impact on end-user experience and satisfaction.

## Scenario 2: Manual Monitoring with Dashboard

### Introduction to CloudWatch

In response to the challenges of Scenario 1, CloudWatch, a monitoring service in AWS, is introduced. The session emphasizes the need for manual monitoring through a dashboard displaying key metrics.

### Key Points

- CloudWatch facilitates monitoring of metrics such as CPU load, memory usage, and network traffic.
- A dashboard is utilized to display chosen metrics, providing a visual representation of system performance.
- Challenges include the impracticality of continuous manual monitoring.

## Scenario 3: Alarms and Notifications

### Introduction to Alarms

To address the limitations of manual monitoring, alarms triggered by specific metric thresholds are introduced. Alarms are designed to notify relevant personnel when critical thresholds are breached.

### Important Considerations

- Alarms are set up for essential metrics, such as CPU load, memory usage, or network traffic.
- Notification methods may include email, SMS, or other alerting mechanisms.
- Considerations for time zones are highlighted to ensure timely responses.

## Scenario 4: Automatic Response with Auto-Scaling

### Introduction to Auto-Scaling

The best-case scenario involves automatic responses triggered by CloudWatch monitoring. AWS Auto Scaling Groups are introduced as a mechanism to dynamically adjust resources based on demand.

### Configuration and Best Practices

- Auto-Scaling Groups allow for dynamic resource adjustments, adding or removing virtual machines.
- Configuring auto-scaling parameters, including minimum, maximum, and desired instances, is crucial.
- Testing auto-scaling under different scenarios ensures optimal performance.

### Cost Considerations

- Cost-effectiveness is emphasized, requiring careful consideration of maximum resources to avoid unnecessary expenses.
- Balancing resource availability with cost efficiency is essential for a well-optimized system.

## Pitfalls and Considerations

### Potential Pitfalls

- Insufficient resources for unexpected situations can lead to system failures.
- Thorough testing is crucial to identify and address any issues with auto-scaling configurations.

### Testing and Best Practices

- Regular load testing helps determine system performance thresholds and informs auto-scaling configurations.
- Continuous monitoring and adjustments based on real-world scenarios contribute to system reliability.

## Visual Representation

The session encourages the creation of diagrams to visually represent scenario number 2:

### Go on the "Monitoring" section of your instance
![Go on the "Monitoring" section of your instance](<../readme-images/Day 5 Monitoring ss/monitoring.png>)

### Click on enable monitoring
![Click on enable monitoring](<../readme-images/Day 5 Monitoring ss/2. enable monitoring.png>)

### Create a dashboard
![Create a dashboard](<../readme-images/Day 5 Monitoring ss/3. create dashboard - will take all the charts and add them to one dash.png>)

### Now click create
![Now click create](<../readme-images/Day 5 Monitoring ss/4. click create.png>)

### Click add to dashboard
![Click add to dashboard](<../readme-images/Day 5 Monitoring ss/5.png>)

### Outcome
![Outcome](<../readme-images/Day 5 Monitoring ss/6. results.png>)

### Now expand the CPU window and change the monitoring to 1 minute as well as 1h instead of 3
![Now expand the CPU window and change the monitoring to 1 minute as well as 1h instead of 3](<../readme-images/Day 5 Monitoring ss/7. change to 1 minute monitor after expansing the cpu window.png>)

