<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Creating a Private Subnet

**Project Link:** [View Project](https://nextwork.ai/projects/4e96e29d-98b8-551e-ae93-da39c36e30fd)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate private subnets in a VPC  I'm doing this project to learn about how private subnets are configured in VPCs

### ✍️ What are we doing in this step?

In this step, I will create a VPC, subnets, an internet gateway, a route table, a security group and a network ACL because i need them set up my virtual private cloud before creating the private subnet

### ✍️ What are we doing in this step?

In this step, I will set up a private subnets because private subnets are ideal for some real-world tasks where we want to keep some resources from the public

### What is Amazon VPC?

Amazon VPC is an isolated virtual network environment you create on the cloud. It is useful because it allows you launch your resources in a controlled and secured environment where you configure everything yourself

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create private subnets, private route tables, private network access control lists

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is

### This project took me...

This project took me about 60 mins

## Private vs Public Subnets

The difference between public and private subnets is that the public subnets are openly connected to the internet while the private subnets are not

Having private subnets are useful because some applications will require some level of privacy for the resources that run the application

My private and public subnets cannot have the same IP addresses

### ✍️ What are we doing in this step?

In this step, I will create a private route table  because a private subnet also needs to be associated with a route table

![Private vs Public Subnets](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-private_afe1fdbd)

## A dedicated route table

By default, my private subnet is associated with default route table created by AWS for all subnets in my VPC

I had to set up a new route table because i don't want the private subnets to be associated with the public route table

My private subnet's dedicated route table only has one inbound and one outbound rule that allows traffic into the resource in the private subnet

### ✍️ What are we doing in this step?

In this step, I will set up a private Network ACL because i want to add an extra layer of security to the private subnet

![A dedicated route table](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-private_b4b904b5)

## A new network ACL

By default, my private subnet is associated with the VPCs default NACL

I set up a dedicated network ACL for my private subnet because i want to restrict traffic and protect the private subnet

My new network ACL has two simple rules - deny all inbound and outbound traffic

![A new network ACL](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-private_1ed2cb07)
