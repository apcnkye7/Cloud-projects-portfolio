<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Launching VPC Resources

**Project Link:** [View Project](https://nextwork.ai/projects/8f49d756-9e51-58c0-856a-e71e54f064ab)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate how to launch ec2 instances in the virtual private cloud I'm doing this project to learn about launching resources in the VPC

### ✍️ What are we doing in this step?

In this step, I will create a VPC, subnets, internet gateway,route table, security group, network ACLs and private resources because i need these componenets for the project

### ✍️ What are we doing in this step?

In this step, I will create a new ec2 instance because i need to launch a new ec2 instance in my public subnet

### What is Amazon VPC?

Amazon VPC is an isolated environment of the AWS cloud and it is useful because it helps you to create and manage resources in a more controlled way

### How I used Amazon VPC in this project

I used Amazon VPC to create subnets, network acls, internet gateways, route tables, key pairs

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the resource maps

### This project took me...

This project took me 60 minutes

## Setting Up Direct VM Access

Directly accessing a virtual machine means logging into and managing the operating system of the machine directly

### SSH is a key method for directly accessing a VM

SSH traffic means connections established and data transmitted through the ssh protocol is encrypted

### To enable direct access, I set up key pairs

Key pairs are a set of public and private keys that engineers use to access their virtual machines

A private key's file format means the file format which is used to store the private key My private key's file format was ".pem"

## Launching a public server

I had to change my EC2 instance's networking settings by assigning it to the vpc i created, changing the subnet association to the public subnet and assigning the security group i created to the ec2 isntance

### ✍️ What are we doing in this step?

In this step, I will launch another ec2 instance because i want another ec2 instance in my private subnet

![Launching a public server](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-ec2_88727bef)

## Launching a private server

My private server has its own dedicated security group because i don't want public access to the instances in the private server

My private server's security group's source is kotei public security group which means that only resources within the vpc can communicate with the instances in the private subnet

### ✍️ What are we doing in this step?

In this step, I will create the VPC set  up in a different because i want to explore other ways in setting up a VPC to save time

![Launching a private server](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-ec2_4a9e8014)

## Speeding up VPC creation

I used an alternative way to set up an Amazon VPC! This time, I used the AWS resource map

A VPC resource map is an alternative option in AWS used to create VPCs , it offers a more visual representation of the components that make up the vpc.

My new VPC has a CIDR block of 10.0.0.0/16It is possible for my new VPC to have the same IPv4 CIDR block as my existing VPC because. VPCs are isolated networks in the cloud and remain disconnnected from each other till you establish connections through VPC peering which will cause you to use separate IPV4 blocks

![Speeding up VPC creation](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-ec2_1cbb1b88)

## Speeding up VPC creation

### Tips for using the VPC resource map

When determining the number of public subnets in my VPC, I only had two options: 0-2 This was because high availability is a key principle in the AWS framework

The set up page also offered to create NAT gateways, which are alternative ways that helps your private subnet communicate with the internet in a more secure way

![Speeding up VPC creation](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-ec2_8ee57662)
