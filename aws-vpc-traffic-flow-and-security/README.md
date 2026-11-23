<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# VPC Traffic Flow and Security

**Project Link:** [View Project](https://nextwork.ai/projects/fe5ed473-5874-57e1-a58f-d9b3d652330c)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate VPC traffic flow and security I'm doing this project to learn about route tables, security groups and network acess control lists

### ✍️ What are we doing in this step?

In this step, I will create a VPC,subnet and an internet gateway because they are the basics for the VPC

### ✍️ What are we doing in this step?

In this step, I will create a route table because i want to direct traffic from the resource to the internet gateway

### What is Amazon VPC?

Amazon VPC is virtual network you create on the cloud  and it is useful because it gives you a virtual network you can work with easily

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create VPCS, security groups, network access control lists, route tables, inbound and outbound rules and subnets

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was ec2 global view

### This project took me...

This project took me about an hour

## Route tables

Route tables is a table of rules that directs where traffic(data) flows in your network

Routes tables are needed to make a subnet public because simply attaching an internet gateway to a subnet doesn't automatcially route traffic. we need the route table for the public subnet to map the traffic

## Route destination and target

Routes are defined by their destination and target, which means the range of IPV4 addresses where the traffic wants to reach and the road where the traffic will take to their destination

The route in my route table that directed internet-bound traffic to my internet gateway had a destination of 0.0.0.0/0 and a target of igw-03db2efcde31ae53c

### ✍️ What are we doing in this step?

In this step, I will create a security group for the resources in my VPC because security groups are needed to control what traffic goes in and out of a resource in a vpc subnet

![Route destination and target](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-security_0a07b191)

## Security groups

Security groups are checkpoints that controls what kind of traffic flows in and out of the resources defined in the networks within your VPC

### Inbound vs Outbound rules

Inbound rules are rules that control what data goes into the resources in the security group I  configured an inbound rule that allows my resources communicate with the public internet

Outbound rules are rules that control the data that goes out of the resources in the security group.By default, my security group's outbound rule already allow outbound traffic

### ✍️ What are we doing in this step?

In this step, I will create a network access control list because i want to improve the network security

![Security groups](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-security_92b0b0b4)

## Network ACLs

Network ACLs are security rules created to control what kind of traffic goes into a subnet within the VPC

### Security groups vs. network ACLs

The difference between a security group and a network ACL is that security groups are attached to resources while network ACLs are attached to subnets

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, a network ACL's inbound and outbound rules will allow all inbound and outbound traffic

In contrast, a custom ACL’s inbound and outbound rules are automatically set to deny all traffic

![Default vs Custom Network ACLs](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-security_4faeb056)

## Tracking VPC Resources

I created additional VPC Instead of my usual region, I used us-east-1 Teams would use multiple regions to deploy the resources

EC2 Global View is a tool where you can find all resources you have deployed in other regions I could even narrow down my search by typing in a specific region. Without EC2 Global View, you'd have to switch between regions to track your resources

Now that I've learnt about EC2 Global View, I'd use it again to track any AWS resources i will be deploying in the future

![Tracking VPC Resources](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-security_b03ea6162)
