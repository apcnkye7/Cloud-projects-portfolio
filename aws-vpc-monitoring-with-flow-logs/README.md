<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# VPC Monitoring with Flow Logs

**Project Link:** [View Project](https://nextwork.ai/projects/6954a600-a89e-56b0-886b-7054da118a3b)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate VPC monitoring in the AWS cloud I'm doing this project to learn about network monitoring in a VPC since it is essential to know how your network is operating in the cloud

### What is Amazon VPC?

Amazon VPC (Virtual Private Cloud) is a networking service in AWS that allows you to create a private, isolated virtual network for your AWS resources, such as EC2 instances, databases, and applications and it useful because it helps you control your own cloud environment

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to host two ec2 instances, establish a vpc peering connection, create flow logs to monitor network activity

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the insights in a dashboard form in cloudwatch

### This project took me...

This project took me 70 minutes

## In the first part of my project...

### Step 1 - Set up VPCs

In this step, I will create two VPCs because the VPCs form the core of the network i am trying to build on the cloud.

### Step 2 - Launch EC2 instances

In this step, I will launch an ec2 instance because I need a resource within the VPC i have created

### Step 3 - Set up Logs

In this step, I will set up the VPC flow logs because I want to track all inbound and outbound network traffic

### Step 4 - Set IAM permissions for Logs

In this step, I will create an IAM policy and role because i need to give VPC flow logs the permissions to write logs and send them to cloudwatch

## Multi-VPC Architecture

I started my project by launching two VPCs with a single public subnet in one availability zone

The CIDR blocks for VPCs 1 and 2 are. 10.1.0.0/16 and 10.2.0.0/16 They have to be unique because unique ipv4 addresses are needed to prevent confusing when routing traffic

### I also launched EC2 instances in each subnet

My EC2 instances' security groups allow all traffic as well as ICMP traffic This is because when using the ping command to check if the VPCs are communication, if ICMP traffic isn't allowed, connection will be denied

![Multi-VPC Architecture](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-monitoring_e7fa8775)

## Logs

Logs are pieces of information that gives insight about everything happening in your aws account

Log groups are big folders where you keep related logs together

![Logs](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-monitoring_e8398869)

### ✍️ What is a flow log?

Flow logs are tiny pieces of information that capture traffic going to and from the network

## IAM Policy and Roles

I created an IAM policy because VPC flow logs don't have the permissions by default to create and send logs to amazon cloud watch thus i need a policy to allow that

I also created an IAM role because i needed to assign the IAM policy i created to an IAM role for it to be used on a resource

A custom trust policy is a specific type of policy that narrowly defines what a user can do

![IAM Policy and Roles](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-monitoring_4334d777)

## In the second part of my project...

### Step 5 - Ping testing and troubleshooting

In this step, I will generate flow traffic because i want to test if the VPC flow logs are working correctly in the network

### Step 6 - Set up a peering connection

In this step, I will set up a vpc peering connection  because the instances in vpc 1 and vpc 2 can only transfer data to each other via their public addresses whilst we want to change that and make them route to their private addresses instead

### Step 7 - Analyze flow logs

In this step, I will visit the flog logs recorded about my VPCs public subnets because i want to analyse the flog logs for insight about my network activity

## Connectivity troubleshooting

My first ping test between my EC2 instances had no replies, which means the ec2 instances couldn't communicate with each other

![Connectivity troubleshooting](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-monitoring_99d4ba42)

I could receive ping replies if I ran the ping test using the other instance's public IP address, which means Instance 2 is correctly configured to respond to ping requests, and Instance 1 can actually communicate with Instance 2 if it traffic goes across the public internet

## Connectivity troubleshooting

Looking at VPC 1's route table, I identified that the ping test with Instance 2's private address failed because there's no route that connects to the private link addresses

### To solve this, I set up a peering connection between my VPCs

I also updated both VPCs' route tables so that the VPCs have the peering connection established between them so traffic can be routed from one VPC to another

![Connectivity troubleshooting](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-monitoring_7316a13d)

## Connectivity troubleshooting

I received ping replies from Instance 2's private IP address! This means that the VPC peering connection is working between my VPCs

![Connectivity troubleshooting](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-monitoring_4ec7821f)

## Analyzing flow logs

Flow logs tell us about all the network activiites that occurs in the network

For example, the flow log I've captured tells us that 76 bytes of data was sent between these time unix time  periods 1787145021 1787145049

![Analyzing flow logs](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-monitoring_d116818e)

## Logs Insights

Logs Insights is a CloudWatch feature that analyzes your logs.

I ran the query "SOURCE "arn:aws:logs:us-east-1:145250404307:log-group:koteivpcflowlogsgroup" START=-1w END=0s |\
stats sum(bytes) as bytesTransferred by srcAddr, dstAddr\
| sort bytesTransferred desc\
| limit 10" This query finds the top 10 source–destination IP address pairs that transferred the most data through your VPC during the last week

![Logs Insights](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-monitoring_3e1e79a1)
