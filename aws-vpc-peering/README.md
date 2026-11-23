<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# VPC Peering

**Project Link:** [View Project](https://nextwork.ai/projects/fd75209e-d2a1-5bdd-90e8-bdb9ee49de16)

**Author:** Gabby Hammond

---

![](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-peering_88727bef)

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate VPC peering  I'm doing this project to learn how two VPCs can communicate with each other

### What is Amazon VPC?

Amazon VPC is an isolated environment of the cloud that allows you to create and manage resources and it is useful because it helps in proper management of the resources on the cloud

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create VPCs, peering connections,subnets, route tables,elastic Ip addresses

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the elastic ip address feature in aws

### This project took me...

This project took me 70 minutes

## In the first part of my project...

### Step 1 - Set up my VPC

In this step, I will create two VPCs because they are the basic requisite to set up for the peering task

### Step 2 - Create a Peering Connection

In this step, I will set up a peering connection between the VPCs i have created because a peering connection is needed for the VPCs to communicate with their unique private addresses so data/traffic wouldn't be routed on public addresses

### Step 3 - Update Route Tables

In this step, I will set up a route for traffic flow between the VPCs because this is essential for the VPCS to communicate in a secure and regulated way because traffic in the VPCs wouldn't know how to reach the resources in the other VPCs without a route

### Step 4 - Launch EC2 Instances

In this step, I will launch an ec2 instance in the VPCs because I will use them to test the VPC peering connection

## Multi-VPC Architecture

I started my project by launching two VPCs with two public subnets, zero private subnets, in 1 availability zones, an internet gateway for each, no VPC endpoints and no NAT gateways

The CIDR blocks for VPCs 1 and 2 are 10.1.0.0/16 and 10.2.0.0/16 They have to be unique because i don't want the resources in the VPCs to overlap

### I also launched 2 EC2 instances

I didn't set up key pairs for these EC2 instances as EC2 instance connect already manages key pairs for us

![Multi-VPC Architecture](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-peering_11111111)

## VPC Peering

A VPC peering connection is a connection that allows VPCs to communicate directly with each other

VPCs would use peering connections to establish a connection link using private unique addresses

The difference between a Requester and an Accepter in a peering connection is a requester initiates the peering connection while the accepter accepts the peering connection invitation

![VPC Peering](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-peering_1cbb1b88)

## Updating route tables

After accepting a peering connection, my VPCs' route tables need to be updated because i need to set up routes that will carry traffic between the VPCs. I need to update the route tables to include the IP addresses of the respective VPCs as destinations in the route tables

My VPCs' new routes have a destination of 0.0.0.0/0,10.1.0.0/16,10.2.0.0/16 The routes' target was internet gateway,the VPC connection link and the local

![Updating route tables](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-peering_4a9e8014)

## In the second part of my project...

### Step 5 - Use EC2 Instance Connect

In this step, I will use ec2 instance connect to connect to the ec2 instance i have created because i want to test to see if there will be any bug with the connection

### Step 6 - Connect to EC2 Instance 1

In this step, I will connect to the ec2 instance one more time becausen I want to verify if the elastic Ipv4 address association worked

### Step 7 - Test VPC Peering

In this step, I will test the VPC peering connection

## Troubleshooting Instance Connect

Next, I used EC2 Instance Connect to connect to the ec2 instance created in the VPC

I was stopped from using EC2 Instance Connect as the ec2 instance i created wasn't assigned any public Ipv4 address

![Troubleshooting Instance Connect](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-peering_7685490c)

## Elastic IP addresses

To resolve this error, I set up Elastic IP addresses. Elastic IP addresses are static IP addresses created by AWS that you can associate to your resources

Associating an Elastic IP address resolved the error because the instance connect establishes the connection to the instance through the public ipv4 address

![Elastic IP addresses](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-peering_45663498)

## Troubleshooting ping issues

To test VPC peering, I ran the command ping 10.2.7.167

A successful ping test would validate my VPC peering connection because it verifies that connection has been successfully established between the VPCs through the messages displayed on the terminal

I had to update my second EC2 instance's security group because it didn't allow ICMP traffic I added a new rule that  allowed ICMP traffic

![Troubleshooting ping issues](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-peering_7a29d352)
