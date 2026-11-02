## Introducing Today's Project!

In this project, I will set up the backend of an app for deployment,Install kubectl and deploy the backend on a Kubernetes cluster.

### ✍️ Don't forget to delete your resources!

Amazon EKS is not AWS Free Tier eligible. AWS charges $0.10 for every hour my EKS cluster is running. To minimise costs, I will delete resources after completion

### ✍️ What are we doing in this step?

In this step, I will launch and connect to an EC2 instance,set up eksctl ,my instance's AWS credentials and create an EKS cluster.

### Tools and concepts

I used Amazon EKS, ECR,eksctl to create and manage my kubernetes clusters, store container images .Key concepts include using manifests and services to define how traffic flows internally between the pods and between the pods and the external environment

### Project reflection

This project took me approximately. 80 minutes

I chose to do this project today because i want to build my portfolio for a job Something that would make learning with NextWork even better is more secret missions

## Project Set Up

### Kubernetes cluster

To set up today's project, I launched a Kubernetes cluster. The cluster's role in this deployment is that it acts like a command center which tells the EC2 instances when to start,stop or scale each of the containers . It keeps the apps deployment running smoothly while the user can focus on writing code for the application

### ✍️ What are we doing in this step?

In this step, I will pull the backend code of the app from github.

### Backend code

I retrieved backend code by pulling the repository from github. Pulling code is essential to this deployment because it allows us to have our own working copy of the original

### ✍️ What are we doing in this step?

In this step, I will... because build a container image of the backend code.

### Container image

Once I cloned the backend code, I built a container image because the container images lets Kubernetes set up multiple, identical containers so the application runs consistently across different environments. I used the coommand "sudi yum install -y docker" to first install docker in the ec2 instance, then i used "sudo service docker start" to start docker, next i added my ec2-user to the docker groups using the command "sudo usermod -a -G docker ec2-user" then finally i used "docker build -t nextwork-flash-backend ." to build the container images.

### ✍️ What are we doing in this step?

In this step, I will store the Docker image of the backend in a repository.

I also pushed the container image to a container registry, which stores the docker images i created. ECR facilitates scaling for my deployment because without them i would have to preload every node in your Kubernetes cluster with your image. I'd also need to update each node manually with every change to your container image.

### ✍️ What are we doing in this step?

In this step, I will create the Deployment manifest, which gives Kubernetes instructions on deploying the containerized backend to the Kubernetes cluster and create the Service manifest, which tells Kubernetes how to expose the application and route traffic to it.

## Manifest files

Kubernetes manifests are a set of instructions that tells Kubernetes how to run your app.  Manifests are helpful because Kubernetes uses it to know what the app needs, like which containers to run, how many copies to create, and how much memory to allocate.

A Kubernetes deployment manages how to keep your app running. The container image URL in my Deployment manifest tells Kubernetes where to pull the container image from when it deploys your application.

My Service manifest sets up a service where we send external traffic to port 8080 on any pod labeled app:nextwork-flask-backend.

### ✍️ What are we doing in this step?

In this step, I will Install kubectl, a command-line tool for using Kubernetes and deploy the app with Kubernetes.

![Manifest files](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/090a4709-f1f4-5d95-ae4d-b8199bf808ed_b01876554)

## Backend Deployment!

To deploy my backend application, I used kubectl to apply the manifest files, which deploys the app across the cluster.

### kubectl

kubectl is a command-line tool for interacting with Kubernetes resources (like Deployment or Service resources) once the cluster is up and running. I need this tool to apply my manifests and deploy my application. I can't use eksctl for the job because the command isn't installed

![Backend Deployment!](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/090a4709-f1f4-5d95-ae4d-b8199bf808ed_6cfb382f2)

## Verifying Deployment

My extension for this project is to use the EKS console to view the nodes created in the kubernetes cluster. I had to set up IAM access policies because even though i had administrator access, kubernetes has its own set of permissions which i had not yet given to my IAM role.I set up access by using this command "eksctl create iamidentitymapping --cluster kotei-eks-cluster --arn arn:aws:iam::145250404307:user/kotei-IAM --group system:masters --username admin --region us-east-1"

Once I gained access into my cluster's nodes, I discovered pods running inside each node. Pods  bundle containers together so they can work as a unit. Pods are the smallest things you can deploy - you can't deploy containers on their own; they must be inside a pod .Containers in a pod share the same network space and storage so they can communicate and share data more efficiently.

The EKS console shows you the events for each pod, where I could see the steps that happened when Kubernetes was creating your pod This validated the backend has been deployed

![Verifying Deployment](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/090a4709-f1f4-5d95-ae4d-b8199bf808ed_3b391f873)
