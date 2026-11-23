<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Testing VPC Connectivity

**Project Link:** [View Project](https://nextwork.ai/projects/da091986-ef01-5973-a070-b15e174f59d8)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate VPC connectivity I'm doing this project to learn about to check how instances in a VPC are connected

### ✍️ What are we doing in this step?

In this step, I will set up my VPC ,subnet, internet gateway,route table, security group and network ACL's because these are key configurations to set up my instances

### ✍️ What are we doing in this step?

In this step, I will set up a connection to the public server in my VPC because I want test the connectivity within the VPC

### What is Amazon VPC?

Amazon VPC is an isolate environment on the cloud you can use to create and host your resources and it is useful because it helps you run an organized environment for your resources in the cloud

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to test connectivity between servers and their subnets, between servers in different subnets and between servers and the internet

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was working a lot in the terminal to test connectivity

### This project took me...

This project took me 120 minutes

## Connecting to an EC2 Instance

Connectivity means how different parts of the network communicate with each other

My first connectivity test was whether I could connect to the my public server

![Connecting to an EC2 Instance](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-connectivity_88727bef)

## EC2 Instance Connect

I connected to my EC2 instance using EC2 Instance Connect, which is a simplified method used to connect to instances through the AWS management console

My first attempt at getting direct access to my public server resulted in an error, because the security group allowed inbound traffic based on the HTTP protocol howeveer the instance connect operates on an SSH protocol

I fixed this error by adding a new inbound rule to allow SSH traffic

### ✍️ What are we doing in this step?

In this step, I will try to get my public server communicate with the private server because i want to test connectivity between resources in differenct subnets

![EC2 Instance Connect](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-connectivity_1cbb1b88)

## Connectivity Between Servers

Ping is is a common computer network tool used to check whether your computer can communicate with another computer or device on a network. I used ping to test the connectivity between my private server and public server

The ping command I ran was "ping 10.0.1.158"

The first ping returned "PNG 10.0.1.158 56(84) bytes of data". This meant that connection was established once and then interrupted ,thus, cutting messages from appearing in the terminal

![Connectivity Between Servers](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-connectivity_defghijk)

## Troubleshooting Connectivity

I troubleshooted this by checking the network access control list inbound rules as well as the security group inbound rules for the private server

### ✍️ What are we doing in this step?

In this step, I will check connectivity between my public server and the internet because i configured an internet gateway in the public server and i want to test it

![Troubleshooting Connectivity](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-connectivity_4a9e8014)

## Connectivity to the Internet

Curl is a command used to also verify connectivity between to servers through data transfers between the servers

I used curl to test the connectivity between the public server and the public internet

### Ping vs Curl

Ping and curl are different because ping checks if two servers can communicate while curls transfers data from one server to another

## Connectivity to the Internet

I ran the curl command "curl https://www.google.com"which returned an html file page of google

![Connectivity to the Internet](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-connectivity_8ee57662)
