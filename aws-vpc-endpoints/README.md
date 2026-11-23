<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# VPC Endpoints

**Project Link:** [View Project](https://nextwork.ai/projects/749fab76-0a0b-5822-9b31-c7863050c9bd)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate connecting an ec2 instance in a public subnet to an aws s3 bucket through vpc endpoints I'm doing this project to learn how aws resources created in public subnets in a VPC can communicate with other resources without using the public internet

### What is Amazon VPC?

Amazon VPC is a networking service in AWS that allows you to create a private, isolated virtual network for your AWS resources, such as EC2 instances, databases, and applications

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a vpc, configure subnets, route tables and security groups and also launch an ec2 instance in a public subnet which later was used to communicate with an external aws s3 bucket through a vpc endpoint

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the policy for endpoints

### This project took me...

This project took me 80 minutes

## In the first part of my project...

### Step 1 - Architecture set up

In this step, I will create a VPC ,launch an EC2 instance and set up an S3 bucket because these are the main components of the network architecture

### Step 2 - Connect to EC2 instance

In this step, I will connect to the ec2 instance i created through the ec2 instance connect and see if i can access the s3 buckets through the ec2 instance over the public internet because i want to analyze the network without the endpoint connections

### Step 3 - Set up access keys

In this step, I will give access to my ec2 instance  because i want my ec2 instance to have acess to my aws environment

### Step 4 - Interact with S3 bucket

In this step, I will use an ec2 instance to connect to the s3 bucket because i want to check if i can connect the ec2 instance to the s3 bucket without the endpoints

## Architecture set up

I started my project by launching a VPC and an ec2 instance in the vpc i created

I also set up an s3 bucket and uploads objects into the s3 bucket

![Architecture set up](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_4334d777)

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured my access key ID, AWS secret  access key, the default region name and output format

Access keys are credentials for your applications and other servers to log into AWS and talk to your AWS services/resources.

Secret access keys are like the password that pairs with your access key ID (your username).

### Best practice

Although I'm using access keys in this project, a best practice alternative is to use an IAM role

## Connecting to my S3 bucket

The command I ran was "aws s3 ls" This command is used to list the available s3 buckets

The terminal responded with the list of s3 buckets.This indicated that the access keys I set up helped my ec2 instance to get access to the aws environment

![Connecting to my S3 bucket](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_4334d778)

## Connecting to my S3 bucket

I also tested the command  aws s3 ls s3://kotei-vpc-project-which returned the objects in the bucket

![Connecting to my S3 bucket](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_4334d779)

## Uploading objects to S3

To upload a new file to my bucket, I first ran the command sudo touch /tmp/kotei.txt  This command creates the file "kotei.txt"

The second command I ran was " aws s3 cp /tmp/kotei.txt s3://kotei-vpc-project-hammond"This command will upload the text file into the s3 bucket

The third command I ran was "aws s3 ls s3://kotei-vpc-project-hammond" which validated that the file has been uploaded

![Uploading objects to S3](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_3e1e79a2)

## In the second part of my project...

### Step 5 - Set up a Gateway

In this step, I will set up a way for the VPC to communicate directly with the s3 bucket because i don't want the vpc to communicate with the s3 bucket over the public internet

### Step 6 - Bucket policies

Here i am going to limit my S3 bucket access's to only traffic from the endpoint i created.

### Step 7 - Update route tables

In this step, I will test my VPC endpoint set up because I want to troubleshoot a connectivity issue.

![In the second part of my project...](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_67081648)

### Step 8 - Validate endpoint conection

In this step, I will test the  VPC endpoint set up again because i want to know if the said changes have been effected

## Setting up a Gateway

I set up an S3 Gateway, which is a type of endpoint used specifically for Amazon S3 and DynamoDB

### What are endpoints?

An endpoint is a service that allows private connections between your VPC and other AWS services without needing the traffic to go over the internet.

![Setting up a Gateway](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_09bcaa8a)

## Bucket policies

A bucket policy is a type of IAM policy designed for setting access permissions to an S3 bucket

My bucket policy will denies all actions (s3:\*) on your S3 bucket and its objects to everyone (Principal: "\*")unless the access is from the VPC endpoint with the ID defined in aws:sourceVpce

![Bucket policies](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_7316a13d)

## Bucket policies

Right after saving my bucket policy, my S3 bucket page showed 'denied access' warnings. This was because the policy allows only actions coming from the vpc endpoint while it blocks any other including the aws management console

I also had to update my route table because the route table has no route  that directs traffic from the endpoint to the s3 bucket. the ec2 was trying to get to the s3 bucket through the route over the public internet

![Bucket policies](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_4ec7821f)

## Route table updates

To update my route table, I added my public subnet route table to the endpoints route table

After updating my public subnet's route table, my terminal could return the objects in my s3 bucket

![Route table updates](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_d116818e)

## Endpoint policies

An endpoint policy is a policy that controls access to the endpoint you have created

I updated my endpoint's policy by editing the endpoint policy. I could see the effect of this right away, because the command to list the s3 buckets in the cli returned with a permission denied message

![Endpoint policies](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-endpoints_3e1e79a3)
