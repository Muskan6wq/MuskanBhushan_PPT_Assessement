Objective:
Create a custom Virtual Private Cloud.

Description:
A VPC was created with subnets, route tables, and an Internet Gateway to understand AWS networking fundamentals.


Task Name:
CloudWatch Alarm on EC2 CPU Usage

What I did:
In this task, I created a CloudWatch alarm for my EC2 instance.
If CPU usage goes above 70%, the alarm should:
1) Send me an email
2) Automatically stop the EC2 instance

Steps I followed:

1. I launched an Ubuntu EC2 instance.
2. I checked that CloudWatch monitoring is enabled for the instance.
3. I created an SNS topic and subscribed my email to it.
4. I confirmed the subscription from my email inbox.
5. I went to CloudWatch → Alarms → Create alarm.
6. I selected EC2 → Per-Instance Metrics → CPUUtilization.
7. I set the condition:
   - CPUUtilization
   - Greater than 70%
   - For consecutive periods
8. In alarm actions:
   - I selected SNS topic to send email
   - I selected EC2 action → Stop instance
9. I created the alarm successfully.

How I tested the alarm:

1. I connected to my EC2 instance using SSH.
2. I installed stress-ng tool.
3. I generated CPU load using stress-ng command.
4. CPU usage increased above 70%.
5. CloudWatch alarm changed state to ALARM.
6. I received an email notification.
7. EC2 instance stopped automatically.

Command I used to increase CPU:

sudo stress-ng --cpu 1 --cpu-load 80 --timeout 2m

Final Result:
The CloudWatch alarm worked correctly.
When CPU crossed 70%, email alert was sent and EC2 instance stopped automatically.

Learning Outcome:
I learned how to:
- Monitor EC2 using CloudWatch
- Create CPU-based alarms
- Use SNS for email notifications
- Automate EC2 actions using alarms

Result:
Custom isolated network environment created.
