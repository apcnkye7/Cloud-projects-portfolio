<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Build a Security Monitoring System

**Project Link:** [View Project](https://nextwork.ai/projects/a6948fcf-cdce-53e8-9037-892917ce7585)

**Author:** Gabby Hammond

---

![](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/a6948fcf-cdce-53e8-9037-892917ce7585_reghtjy)

## Introducing Today's Project!

In this project, I will demonstrate setting up AWS CloudTrail to track secret access events, using AWS CloudWatch to log access attempts and trigger notifications,creating SNS alerts to get notified when secrets are accessed and building a second notification system to compare which approach delivers better security alerts. I'm doing this project to learn about building a security monitoring system

### ✍️ What are we doing in this step?

In this step, I will create a new secrets manager secret.

### Tools and concepts

Services I used were AWS cloudtrail,cloudwatch,cloudshell,s3,AWS SNS, and AWS secrets manager.Key concepts I learnt include monitoring,sns topics, metrics and alarms

### Project reflection

This project took me approximately 2 hoursThe most challenging part was debugging why the emails weren't appearing after accessing the secrets.It was most rewarding to go through the steps carefully

### ❤️ Thanks for doing this project!

Why did you do this project today?To build my portfolio Did this project meet your goals?  Yes What would make your learning experience with NextWork even better? More secret missions

## Create a Secret

Secrets Manager is an AWS service that helps you protect secrets, which are passwords, API keys, credentials and sensitive information.

To set up for my project, I created a secret called TopSecretInfo that contains a dummy key and a dummy value. both are just strings

### ✍️ What are we doing in this step?

In this step, I will create a new CloudTrail trail to record my account's activity and configure the trail to store logs in an S3 bucket because this step forms the beginning of the monitoring system i want to set up

![Create a Secret](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/a6948fcf-cdce-53e8-9037-892917ce7585_o5p6q7r8)

## Set Up CloudTrail

CloudTrail is an AWS monitoring service I set up a trail to track the access to the AWS secret i created in secret manager

CloudTrail events include types like management events,data events,insight events and network activity events

### Read vs Write Activity

Read API activity involves just looking at resources without making any changes to them. Write API activity involves making changes to the resources.For this project, we need both

### ✍️ What are we doing in this step?

In this step, I will generate a secret access event because i want to verify if the cloudtrail monitoring system is working correctly

## Verifying CloudTrail

I retrieved the secret in two ways: First through the aws management console Second using the aws cloudshell

To analyze my CloudTrail events, I visited the cloudtrail event history with the "secretsmanager.amazonaws.com" as the event source I found a history of all events related to the secrets manager This tells me i viewed my secrets in the secrets manager

### ✍️ What are we doing in this step?

In this step, I will enable a CloudWatch Logs for my CloudTrail trail, define a CloudWatch Metric to track secret access because i want to track secret access using cloudwatch metrics

![Verifying CloudTrail](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/a6948fcf-cdce-53e8-9037-892917ce7585_s8t9u0v1)

## CloudWatch Metrics

CloudWatch Logs is a service that helps you bring together your logs from different AWS services, including CloudTrail, for visibility, troubleshooting, and analysis.It's important for monitoring because it can monitor logs from a wide variety of sources

CloudTrail's Event History is useful for keeping events only for a few number of days, for aws it's up to 90 days while CloudWatch Logs are better for keeping logs for a long period of time

A CloudWatch metric is a time-ordered sequence of data points that represents the performance of an AWS resource. When setting up a metric, the metric value represents what  gets recorded when our filter spots a match in the logs.Default value is used when what gets recorded when our filter doesn't find any matches during a given time period.

### ✍️ What are we doing in this step?

In this step, I will create a CloudWatch Alarm based on the SecretIsAccessed metric,create an SNS topic to send email notifications,subscribe an email address to the SNS topic.

![CloudWatch Metrics](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/a6948fcf-cdce-53e8-9037-892917ce7585_a9b0c1d2)

## CloudWatch Alarm

A CloudWatch alarm is an automated monitoring rule in cloudwatch I set my CloudWatch alarm threshold to 1 so the alarm will trigger when the secret is accessed

I created an SNS topic along the way. An SNS topic is a  broadcast channel for your notifications.My SNS topic is set up to SecurityAlarms

AWS requires email confirmation because they need to confirm if it's really you receiving the notifications.This helps prevent sending notifications to people who didn't ask for them

### ✍️ What are we doing in this step?

In this step, I will retrieve the secret value again to trigger the alarm to verify if the alarm system is working

![CloudWatch Alarm](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/a6948fcf-cdce-53e8-9037-892917ce7585_fsdghstt)

## Troubleshooting Notification Errors

To test my monitoring system, I checked my email.The results were i didn't receive an email of secrets access.

When troubleshooting the notification issues I checked my cloudtrail,cloudwatch log delivery,metric filters and alarm configuration to verify everything was working properly

I initially didn't receive an email before because of the we set the statistic to average. The key solution was to change it to sum

## Success!

To validate i run the command in the cli to retrieve the secrets value once more after the changes. I checked by checking the cloudwatch dashboard to see if i got any alarm notification.I received an email to confirm

![Success!](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/a6948fcf-cdce-53e8-9037-892917ce7585_ageraergearge)

## Comparing CloudWatch with CloudTrail Notifications

In a project extension, I allowed sns notification delivery directly from my cloudtrial because i wanted to reduce the complexity of the architecture by sending sns notifications directly from cloudtrail without using the cloudwatch

After enabling CloudTrail SNS notifications, my inbox was filled with a lot of emails from cloudtrail In terms of the usefulness of these emails, I thought some mails were redundant and i didn't need to see them

![Comparing CloudWatch with CloudTrail Notifications](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/a6948fcf-cdce-53e8-9037-892917ce7585_d7e8f9g0)
