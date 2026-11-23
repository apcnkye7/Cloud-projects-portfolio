<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Create S3 Buckets with Terraform

**Project Link:** [View Project](https://nextwork.ai/projects/10d3e52a-a2ad-597e-9e1c-33526bde77ba)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

In this project, I will install and configure Terraform,configure my AWS credentials in the terminal, create and manage S3 buckets with Terraform and upload files to S3 using Terraform.

### ✍️ What are we doing in this step?

In this step, I will download and install Terraform and verify my installation.

### Tools and concepts

Services I used were S3, IAM and AWS CLI and terraform.Key concepts I learnt include infrastructure as code, creating access keys, using the AWS CLI ,using terraform commands like terraform init, plan and apply

### Project reflection

This project took me approximately an hourThe most challenging part was setting up the s3 using terraform apply. It was most rewarding to read the error message and debug using resources online

I chose to do this project today because i am building a work portfolio Something that would make learning with NextWork even better is more secret projects

## Introducing Terraform

Terraform is a tool that helps you build and manage your cloud infrastructure using code.

Terraform is one of the most popular tools used for infrastructure as code (IaC), which is the practice of describing your cloud setup (like your servers, storage, networks) in plain text files instead of clicking through a web console. When you run those files, the cloud builds everything exactly as you've written it written

### ✍️ What are we doing in this step?

In this step, I wil create a project directory and set up the main configuration file.

Terraform uses configuration files to to define and manage infrastructure.  main.tf is a central file in a Terraform project,It's where you write down what you want your infrastructure to look like, using Terraform's language.

### ✍️ What are we doing in this step?

In this step, I will add terraform code to the main.tf file

![Introducing Terraform](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/10d3e52a-a2ad-597e-9e1c-33526bde77ba_9i0j1k2l)

## Configuration files

The configuration is structured in the cloud provider and the resource. The advantage of doing this is to separate the resource  and the provider for more readability and easy editing

### My main.tf configuration has three blocks

The first block indicates the provider blockThe second block provisions the resources The third block manages the permissions and policies associated with the resource

![Configuration files](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/10d3e52a-a2ad-597e-9e1c-33526bde77ba_ljvh9876)

## Customizing my S3 Bucket

For my project extension, I visited the official Terraform documentation to  find and read documentation about Terraform modules and providers.The documentation shows the setup instructions, descriptions of each available resource, best practice tips and examples, and parameters for customization.

I chose to customise my bucket by adding tags because i want a unique identificaition for my bucket When I launch my bucket, I can verify my customization by viewing the resource details in the console.

### ✍️ What are we doing in this step?

In this step, I will initialize Terraform,plan the infrastructure changes i.e. preview how the configuration will change my AWS environment.

![Customizing my S3 Bucket](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/10d3e52a-a2ad-597e-9e1c-33526bde77ba_ffe757cd3)

## Terraform commands

I ran 'terraform init' to download the necessary plugins, backend, modules and lock file for the terraform project

Next, I ran 'terraform plan' to create an execution plan, showing  what changes Terraform will make to the infrastructure based on the configuration files

### ✍️ What are we doing in this step?

In this step, I will install AWS CLI,generate AWS access keys and configure CLI with the access key.

![Terraform commands](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/10d3e52a-a2ad-597e-9e1c-33526bde77ba_3g4h5i6j)

## AWS CLI and Access Keys

When I tried to plan my Terraform configuration, I received an error message that says no credential sources found because i havent' configured my aws credentials to allow terraform build resources on my aws account

To resolve my error, first I installed AWS CLI, which is a tool that lets you manage your AWS services from your terminal

I set up AWS access keys to configure my credientials in the AWS cli. I created those access keys using my IAM user

### ✍️ What are we doing in this step?

In this step, I will apply the Terraform configuration and verify that I've launched an S3 bucket

![AWS CLI and Access Keys](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/10d3e52a-a2ad-597e-9e1c-33526bde77ba_7j8k9l0m)

## Lanching the S3 Bucket

I ran 'terraform apply' to apply the changes I've written in the Terraform configuration. It creates, modifies, or deletes resources in the infrastructure based on the code Running 'terraform apply' will affect my AWS account by creating the resources specified in the

The sequence of running terraform init, plan, and apply is crucial because terraform init needs to set up the project first by downloading necessary plugins and setting up the state file, which is a file Terraform uses to track the current state of your infrastructure. There actually aren't any errors if you skip terraform plan. This is because terraform apply will automatically run a plan and ask for confirmation before making any changes. But, skipping the explicit terraform plan means you might miss reviewing these changes in detail.

![Lanching the S3 Bucket](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/10d3e52a-a2ad-597e-9e1c-33526bde77ba_1q2w3e4r)

## Uploading an S3 Object

I created a new resource block to add an object to the s3 bucket i created

We need to run terraform apply again because we made changes to the main.tf file which we need to apply to the s3 bucket

To validate that I've updated my configuration successfully, I checked the contents of the buckets in my aws management console

![Uploading an S3 Object](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/10d3e52a-a2ad-597e-9e1c-33526bde77ba_9o0p1a2s)
