<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Deploy a Web App with CodeDeploy

**Project Link:** [View Project](https://nextwork.ai/projects/836cda66-f725-5082-bdb3-0152b1d7a61b)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

In this project, I will demonstrate launching a deployment environment using AWS CloudFormation, write deployment scripts to automate deployment commands, deploy the web app with CodeDeploy and implement a disaster recovery technique ie.roll back a deployment

### ✍️ What are we doing in this step?

In this step, I will use CloudFormation to launch an EC2 instance using CloudFormation,configure network settings for the EC2 instance and understand Infrastructure as Code.

### Key tools and concepts

Services I used were AWS CodeBuild, CodeDeploy,S3,CodeArtifact, EC2 ,IAM. Key concepts I learnt include deployment, deployment groups, rollbacks,

### Project reflection

This project took me approximately 4 hours. The most challenging part was deploying the application using CodeDeploy. It was most rewarding to stick to the guidelines in the steps

### ✅ Why did you do this project today?

I did this project because i am building a portfolio for work

This project is part five of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project in 24 hours

## Deployment Environment

To set up for CodeDeploy, I launched an EC2 instance and VPC because  this new instance is created specifically for running our application in a live, production environment i.e. what users will see. By having a separate EC2 instance for deploying our application, we avoid the risk of testing any code changes/new features in a live production environment that users end up seeing too.

Instead of launching these resources manually, I used. a cloudformation template in a yaml.file When I need to delete these resources i just need to delete the stack

Other resources created in this template include subnet,route tables and internet gateway.They're also in the template because a subdivision of the VPC where you can place resources, we need to define how network traffic is routed within the VPC and also allow resources in the VPC to connect to the internet

### ✍️ What are we doing in this step?

In this step, I will create deployment scripts for installing dependencies, starting, and stopping the server,create an appspec.yml file to tell CodeDeploy how to handle the deployment process and update the buildspec.yml to package deployment files in the build artifact.

![Deployment Environment](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/836cda66-f725-5082-bdb3-0152b1d7a61b_val-5)

## Deployment Scripts

Scripts are mini-programs that automate tasks. To set up CodeDeploy, I also wrote scripts to install dependencies and start a server

The 'install\_dependencies will script set up all the software needed to run our website by installing programs (called Tomcat and Apache) that handle internet traffic and host our application

The start\_server.sh will start both Tomcat (our Java application server) and Apache (our web server) and makes sure they'll restart automatically if the EC2 instance ever reboots.

The stop\_server.sh will safely stop the web server services by first checking if they're running.

## appspec.yml

Then, I wrote an appspec.yml file to act as  the instruction manual for CodeDeploy The key sections in appspec.yml are version,files,hooks

I also updated buildspec.yml because after building the app, we need to make sure to include these additional files in the final package which are the appspec.yml and scripts folder because CodeDeploy will need them to properly deploy the application. Without them, CodeDeploy wouldn't know what to do with the compiled code.

### ✍️ What are we doing in this step?

In this step, I will configure a CodeDeploy application, which is an application that I want to deploy,create a CodeDeploy deployment group, which is like a folder of deployment settings for the same application,give CodeDeploy the permission to access CodeArtifact

![appspec.yml](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/836cda66-f725-5082-bdb3-0152b1d7a61b_val-12)

## Setting Up CodeDeploy

A deployment group is a collection of EC2 instances that are grouped to deploy something together.A CodeDeploy application is like the main folder for your deployment project. It doesn't do much on its own, but it helps you organize everything related to deploying one application.

To set up a deployment group, you also need to create an IAM role to  let CodeDeploy work with the EC2 instances.

Tags are helpful for easy identification I used the tag role -webserver to tag the ec2 instances for the deployment groups

![Setting Up CodeDeploy](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/836cda66-f725-5082-bdb3-0152b1d7a61b_val-18)

## Deployment configurations

Another key settings is the deployment configuration, which affects  how quickly you'd like to roll out your application.  I used CodeDeployDefault.AllAtOnce,  we only have one instance and speed is the priority here.

### ✍️ What are we doing in this step?

In this step, I will create a deployment to monitor the deployment process,access and verify the deployed web application.

In order to connect the ec2 instance to codedeploy a CodeDeploy Agent is also set up to  let your EC2 instance communicate with CodeDeploy.

![Deployment configurations](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/836cda66-f725-5082-bdb3-0152b1d7a61b_val-20)

## Success!

A CodeDeploy deployment is a single update to your application, with its own unique ID and history.The difference to a deployment group is Aadeployment group is a configuration container / target collection (essentially a logical folder or grouping of your EC2 instances and settings) while the deployment is the single update

I had to configure a revision location, which means the place where CodeDeploy looks to find your application's build artifacts.  My revision location was the S3 bucket that's storing my WAR file, so CodeDeploy knows where to find the latest version of the web app it's deploying to the deployment EC2 instances

To check that the deployment was a success, I visited the ublic IPv4 DNS of the ec2 instance I saw the homepage of the website.

![Success!](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/836cda66-f725-5082-bdb3-0152b1d7a61b_val-27)

## Disaster Recovery

In a project extension, I decided to The intentional error I created was intentionally create a broken deployment and watch it fail in real-time.This will cause the deployment to fail because the command systemctll is not a correct command in the stop\_server.sh file and so it will break the deployment

I also enabled rollbacks with this deployment, which means system returns back to normal in cases of a failed deployment

When my deployment failed, the automatic rollback was triggered because we enabled automatic rollback when creating the deployments. To actually recover from failed deployment Id have to rollback to the known good working version. In production environments more advance tools like the AWS CodePipeline can be configured to automatically roll back to the last successful deployment when a failure is detected, which eliminates the need for manual intervention.

![Disaster Recovery](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/836cda66-f725-5082-bdb3-0152b1d7a61b_rollback-validation-upload)
