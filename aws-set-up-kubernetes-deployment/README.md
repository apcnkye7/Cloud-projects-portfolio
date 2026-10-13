<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Set Up Kubernetes Deployment

**Project Link:** [View Project](https://nextwork.ai/projects/ca1e2f05-dd07-5e77-b83c-1e6a6516944c)

**Author:** Gabby Hammond  
**Email:** hammondgabby7436@gmail.com

---

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/ca1e2f05-dd07-5e77-b83c-1e6a6516944c_45e6c3de5)

## Introducing Today's Project!

In this project, I will clone a backend application from GitHub,build a Docker image of the backend,push an image to an Amazon ECR repository,troubleshoot installation and configuration errors

### Tools and concepts

I used Amazon EKS, Git and Amazon ECR  to create a kubernetes cluster, clone a github repository and create and store a docker container. Key steps include creating the cluster using the command "eksctl create cluster \
  --name nextwork-eks-cluster \
  --nodegroup-name nextwork-nodegroup \
  --node-type t3.micro \
  --nodes 3 \
  --nodes-min 1 \
  --nodes-max 3 \
  --version 1.33 \
  --region your-region-code"
cloning the repository using git clone "repo url", next i created a docker container using the command "docker build -t nextwork-flask-backend .", next i created a container registry using the command "aws ecr create-repository \
  --repository-name nextwork-flask-backend \
  --image-scanning-configuration scanOnPush=true \"

### Project reflection

This project took me approximately 2 hours

Something new that I learnt from this experience was amazon container registry and containerization using aws services

## What I'm deploying

To set up today's project, I launched a Kubernetes cluster. Steps I took to do this included giving my ec2 instance permission to run the Amazon EKS by attaching the IAM role to it, installing the ekstcl command in my ec2 instance and running the following code to create the eks cluster "eksctl create cluster \
  --name nextwork-eks-cluster \
  --nodegroup-name nextwork-nodegroup \
  --node-type t3.micro \
  --nodes 3 \
  --nodes-min 1 \
  --nodes-max 3 \
  --version 1.33 \
  --region ap-northeast-2"

### I'm deploying an app's backend

Next, I retrieved the backend that I plan to deploy. An app's backend means code files that make the application function behind the scenes I retrieved backend code by cloning the code's repository from github to my ec2 instance

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/ca1e2f05-dd07-5e77-b83c-1e6a6516944c_1ebb86c71)

## Building a container image

Once I cloned the backend code, my next step is to build a container image of the backend. This is because we need to set up multiple, identical containers so the application runs consistently across different environments.

When I tried to build a Docker image of the backend, I ran into a permissions error because The commands I ran to install Docker installed it for the root account, so only my root user can talk to the Docker engine. But, I've actually set up the Instance Connect session with another user called ec2-user, so Docker commands are blocked.

To solve the permissions error, I added the ec2-user to the docker group using this command "sudo usermod -a -G docker ec2-user".The Docker group is  a group in Linux systems that gives users the permission to run Docker commands

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/ca1e2f05-dd07-5e77-b83c-1e6a6516944c_45e6c3de5)

## Container Registry

I'm using Amazon ECR in this project to store the container images of the backend i created using Docker.ECR is a good choice for the job because it lets lets Elastic Kubernetes Service (EKS) deploy the container image with minimal authentication setup.

Container registries like Amazon ECR are great for Kubernetes deployment because they allow you deploy the container image with minimal authentication setup.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/ca1e2f05-dd07-5e77-b83c-1e6a6516944c_l2m3n4o5)

## EXTRA: Backend Explained

After reviewing the app's backend code, I've learnt that the backend fetches data based on a search topic you enter,the backend code uses Flask to connect with an external API (Hacker News Search API) and process the data,the backend then sends the data back as formatted JSON.

### Unpacking three key backend files

The requirements.txt file lists the dependencies an application needs to run properly.

The Dockerfile gives Docker instructions on  how a Docker image of the backend should be built.Key commands in this Dockerfile include FROM, LABEL, WORKDIR, COPY, RUN, CMD

The app.py file contains the the main code for the backend

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/ca1e2f05-dd07-5e77-b83c-1e6a6516944c)*
