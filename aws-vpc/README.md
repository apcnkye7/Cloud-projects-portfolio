<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Build a Virtual Private Cloud

**Project Link:** [View Project](https://nextwork.ai/projects/7f907ac7-2473-5c15-a8be-edb36581cdba)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

In this project, I will demonstrate how to create a virtual private cloud on AWS I'm doing this project to learn about AWS VPCs

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, I will access the AWS VPC console because I want to create a virtual private cloud on AWS

### How VPCs work

VPCs are isolated network environments you create on the cloud to isolate resources on the cloud .

### Why there is a default VPC in AWS accounts

There was already a default VPC in my account ever since my AWS account was created. This is because the default VPC created is needed to launch resources in AWS

![Virtual Private Clouds (VPCs)](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which is a range of addresses or block or IP addresses that can be assigned to the resources in my VPC

## Subnets

### What I did in this step

In this step, I will launch subnets within my VPC because the VPC is nothing but a large isolated environment and i need to partition them into sub-isolated environments to contain other resources i will use in the cloud. this is to prevent clumsiness in my virtual private cloud environment

### Creating and configuring subnets

Subnets are isolated environments you create in a VPC to group resources with similar access rules and regulations. There are already subnets existing in my account, one for every availability zone in the region

### Public vs private subnets

The difference between public and private subnets are public subnets are connected to the internet while private subnets do not have direct access to the internet. For a subnet to be considered public, it has to to be connected to the internet using the internet gateway

![Subnets](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled auto assign IPv4 addresses This setting makes sure any resources launched in my public subnet has an public IP address so that it can access or be accessible to the internet

## Internet gateways

### What I did in this step

In this step, I will create an internet gateway for the subnets within my virtual private cloud because the internet gateway is needed for communication between resources in my public subnet and the internet

### Setting up internet gateways

Internet gateways are gateways used to establish connection between instances launched in a VPC with the internet

Attaching an internet gateway to a VPC means resources in the VPC can now access the internet. If I missed this step resources in the VPC won't be able to access the internet

![Internet gateways](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-vpc_4ae90410)

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, I will use AWS cloudshell to launch a VPC because i want to find an efficient way of launching VPCs without using the console

### Exploring CloudShell and CLI

VPC resources could also be created with CloudShell, which is a shell environment in AWS where you can directly write code. CLI is the command line interactive environment in cloudshell that allows you to write scripts

### Debugging my setup

To set up a VPC or a subnet, you can use the command"aws ec2 create-subnet --vpc-id VPC-ID "\
 Make sure to avoid errors by including the cidr block "--cidr-block ADD-CIDR-BLOCK-HERE" so the command becomes \
 aws ec2 create-subnet --vpc-id VPC-ID --cidr-block ADD-CIDR-BLOCK-HERE

![Using the AWS CLI](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

Compared to using the AWS Console, an advantage of using commands is you can always track what you did  and debug easily if something goes wrong. An advantage of using the Console is you don't have to write code. Overall, I preferred the cli
