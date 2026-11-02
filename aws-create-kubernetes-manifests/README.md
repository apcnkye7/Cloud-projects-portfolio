## Introducing Today's Project!

In this project, I will set up a deployment manifest that tells Kubernetes how to deploy my backend and set up a service manifest that tells Kubernetes how to expose my backend to my users.

### ✍️ Don't forget to delete your resources!

Repeat this: 'Amazon EKS is not AWS Free Tier eligible. AWS charges $0.10 for every hour my EKS cluster is running. To minimise costs, I will delete all my resources today.'

### ✍️ What are we doing in this step?

In this step, I will launch and connect to an EC2 instance,set up eksctl , my instance's AWS credentials and create an EKS cluster.

### Tools and concepts

I used Amazon EKS, ECR,eksctl to create and manage my kubernetes clusters, store container images .Key concepts include using manifests and services to define how traffic flows internally between the pods and between the pods and the external environment

### Project reflection

I chose to do this project today because I am building my portfolio. Something that would make learning with NextWork even better is more secret projects

This project took me approximately 70 minutes

## Project Set Up

### Kubernetes cluster

To set up today's project, I launched a Kubernetes cluster. Steps I took to do this included creating an ec2 instance, setting up the eksctl command in the ec2 instance terminal, creating an IAM role to give the ec2 instance administrator permissions and then finally running the code to create the EKS clusters

### ✍️ What are we doing in this step?

In this step, I will pull the code for my backend

### Backend code

I retrieved the backend that I plan to deploy by cloning the code for the github repository for the project. Backend is the "brain" of an application. It's where your app processes user requests and stores and retrieves data

### ✍️ What are we doing in this step?

In this step, I will build a container image of the backend.

### Container image

Once I cloned the backend code, I built a container image because the container images lets Kubernetes set up multiple, identical containers so the application runs consistently across different environments. I used the coommand "sudi yum install -y docker" to first install docker in the ec2 instance, then i used "sudo service docker start" to start docker, next i added my ec2-user to the docker groups using the command "sudo usermod -a -G docker ec2-user" then finally i used "docker build -t nextwork-flash-backend ." to build the container images.

### ✍️ What are we doing in this step?

In this step, I will store the Docker image of the backend in a repository using the elastic container registry

I also pushed the container image to a container registry, because before kubernetes can coordinate the container images, it needs to do that from a registry and pushing the image to the ecr makes it possible. To push the image to ECR, I used the commands in the "push commands" tab of the ecr

### ✍️ What are we doing in this step?

In this step, I will Create the Deployment manifest, because this gives Kubernetes instructions on deploying the  containerized backend to the Kubernetes cluster

## Manifest files

Kubernetes manifests are a set of instructions that tells Kubernetes how to run your app.  Manifests are helpful because Kubernetes uses it to know what the app needs, like which containers to run, how many copies to create, and how much memory to allocate.

A Kubernetes deployment manages how to keep your app running. The container image URL in my Deployment manifest tells Kubernetes where to pull the container image from when it deploys your application.

### ✍️ What are we doing in this step?

In this step, I will create the Service manifest, which tells Kubernetes how to expose the application and route traffic to it.

![Manifest files](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/ccc2aecf-ba9e-5ebe-98ec-e0c4aec9c4ea_b01876554)

## Service Manifest

A Kubernetes Service acts like a traffic controller that keeps traffic flowing to the right pods inside the app. You need a Service manifest to tell Kubernetes to create or update that traffic controller. The Service manifest is what you use to expose your app to the outside world or other parts of your system.

My Service manifest sets up a service where we send external traffic to port 8080 on any pod labeled app:nextwork-flask-backend.

![Service Manifest](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/ccc2aecf-ba9e-5ebe-98ec-e0c4aec9c4ea_b01876555)

## Deployment Manifest

Annotating the Deployment manifest helped me understand what each section of code in the yaml file meant.

A notable line in the Deployment manifest is the number of replicas, which means  identical copies (or instances) of the app Kubernetes should run.  Pods are relevant to this because pods are the smallest unit you can deploy and it's impossible to deploy a container without a pod.

One part of the Deployment manifest I still want to know more about is how the whole pipeline works end to end for an application

![Deployment Manifest](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/ccc2aecf-ba9e-5ebe-98ec-e0c4aec9c4ea_6aae73e71)
