<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launch a Kubernetes Cluster

**Project Link:** [View Project](https://nextwork.ai/projects/aa8525df-82a0-5697-8721-a03b2db2c635)

**Author:** Gabby Hammond  
**Email:** hammondgabby7436@gmail.com

---

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aa8525df-82a0-5697-8721-a03b2db2c635_e5f6g7h8)

## Introducing Today's Project!

In this project, I will launch and connect to an EC2 instance,create a Kubernetes cluster,monitor the cluster creation with CloudFormation,access the cluster using an IAM access entry.

## What is Kubernetes?

Kubernetes is a container orchestration platform Companies and developers use Kubernetes to  keep large, container-based applications steady and easy to scale with traffic

I used eksctl to create the  Amazon EKS cluster in my terminal. The create cluster command I ran defined  cluster named kotei-eks-cluster,launched a node group called nextwork-nodegroup,used t3.micro EC2 instances as nodes,started my node group with 3 nodes and automatically scale between 1 (minimum) and 3 nodes (maximum) based on demand and used Kubernetes version 1.31 for the cluster setup.

I initially ran into two errors while using eksctl. The first one was because eksctl wasn't installed on my ec2 instance The second one was because i didn't have the permissions to create an Amazon kubernetes cluster in my ec2 instance

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aa8525df-82a0-5697-8721-a03b2db2c635_ff9bfc221)

## eksctl and CloudFormation

CloudFormation helped create my EKS cluster because eksctl sets up a CloudFormation stack to automate the creation of all the necessary resources for the EKS cluster. It created VPC resources because a VPC resource is need for the the kubernetes cluster to work

There was also a second CloudFormation stack for the kubernetes nodes.The difference between a cluster and node group is the cluster is the whole environment the containerized application while the node group are the actual servers that run the containers

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aa8525df-82a0-5697-8721-a03b2db2c635_w3e4r5t6)

## The EKS console

I had to create an IAM access entry in order to make the the cluster give me access the nodes.An access entry is  a handshake that connects AWS and Kubernetes I set it up by giving my IAM user the "AmazonEKSClusterAdminPolicy" role 

 

It took me 20 minutes to create my cluster. Since I'll create this cluster again in the next project of this series, maybe this process could be sped up if I use automated provisioning modes, fast node launchers, and streamlined infrastructure-as-code tools instead of manual console clicks or heavy CloudFormation stacks

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aa8525df-82a0-5697-8721-a03b2db2c635_e5f6g7h8)

## EXTRA: Deleting nodes

Did you know you can find your EKS cluster's nodes in Amazon EC2? This is because Amazon EKS cluster nodes are actually Amazon EC2 instances under the hood.

Desired size means the number of nodes you want running in your node group.Mininum and maximum sizes are helpful for scaling up or scaling down to help keeping the app running all the time.

When I deleted my EC2 instances after some few minutes the node group instances were created again. This is because the instances  are managed by an Amazon EC2 Auto Scaling Group

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aa8525df-82a0-5697-8721-a03b2db2c635_q7r8s9t0)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/aa8525df-82a0-5697-8721-a03b2db2c635)*
