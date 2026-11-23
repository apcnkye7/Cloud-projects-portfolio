<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Access S3 from a VPC

**Project Link:** [View Project](https://nextwork.ai/projects/36d7dc8f-3a9f-51ff-91ae-662077ea9920)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate how to access an s3 bucket from a VPC I'm doing this project to learn how to make other resources or services outside a VPC interact with resources in a VPC

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a networking service in AWS that allows you to create a private, isolated virtual network for your AWS resources, such as EC2 instances, databases, and applications.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create an EC2 instance

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was aws secret keys

### This project took me...

This project took me about 60 minutes

## In the first part of my project...

### Step 1 - Architecture set up

In this step, I will create a VPC and launch an EC2 instance in it because that's one of they key components in the architecure for this project

### Step 2 - Connect to my EC2 instance

In this step, I will connect directly to my ec2 instance because i want to try and access the resource directly using amazon instance connect

### Step 3 - Set up access keys

In this step, I will set up my AWS access keys  because the ec2 instance created needs credentials to access the AWS services i want it to interact with

## Architecture set up

I started my project by launching an ec2 instance in my VPC with the ec2 instance configured with an amazon linux 2023 AMI, t3 micro instance , no key pair , auto assigning IPV4 addresses to the instance and a security group that allows all ssh traffic

I also set up my s3 bucket and uploaded two files into the bucket

![Architecture set up](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-s3_4334d777)

## Running CLI commands

AWS CLI is a software that lets you run aws services and resources from the command line I have access to AWS CLI because i have aws credentials that gives me access to use this resource

The second command I ran was "aws configure" This command is used to set up my aws credentials

![Running CLI commands](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-s3_e7fa8776)

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured the aws credentials using aws configure. i used aws access key id and secret access key from the access key csv i downloaded after creating my access key

Access keys are credentials that my applications uses to log into my AWS account and interact with AWS services/resources

Secret access keys are passwords that are paired with access key IDS to access AWS services.

### Best practice

Although I'm using access keys in this project, a best practice alternative is  to create an IAM role with the necessary permissions and then attaching that role to your EC2 instance.

## In the second part of my project...

### Step 4 - Set up an S3 bucket

In this step, I will create an s3 bucket because i need an external service to interact with the VPC and the s3 bucket is the choice for this project

### Step 5 - Connecting to my S3 bucket

In this step, I will connect to the s3 bucket using the ec2 instance by opening the access key.csv file, copying the access key ID and pasting it in the ec2 terminal, next i copy and paste the secret key as well

## Connecting to my S3 bucket

The first command I ran was "aws s3 ls" This command is used to list s3 buckets in my aws accout

When I ran the command aws s3 ls again, the terminal responded with the number of my s3 bucket.This indicated that my ec2 instance can now communicate with s3 bucket since it has been configured with the necessary credentials to do so.

![Connecting to my S3 bucket](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-s3_4334d778)

## Connecting to my S3 bucket

Another CLI command I ran was aws s3 ls s3://kotei-vpc-project-hammond which returned the objects stored in my s3 bucket

![Connecting to my S3 bucket](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-s3_4334d779)

## Uploading objects to S3

To upload a new file to my bucket, I first ran the command "sudo touch /tmp/test.txt" to create the file first

The second command I ran was"aws s3 cp /tmp/test.txt s3://kotei-vpc-project-hammond" This command creates a copy of the file and uploads it to the s3 bucket

The third command I ran was "aws s3 ls s3://kotei-vpc-project-hammond" which validated that the object exists within the s3 bucket

![Uploading objects to S3](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-s3_3e1e79a2)
