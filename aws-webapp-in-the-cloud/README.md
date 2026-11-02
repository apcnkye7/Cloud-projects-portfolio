## Introducing Today's Project!

In this project, I will demonstrate launching an EC2 instance,using VS Code to set up a remote SSH connection to the EC2 instance and installing Maven and Java and generate a basic web app.

This project is part one of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project in 24 hours

I did this project because i am building a portfolio

### Key tools and concepts

Services I used were EC2 instances.Key concepts I learnt include connecting to the ec2 instance using the REMOTE-SSH extension in VS code editorl

### Project reflection

This project took me approximately 80 minutes.

One thing I didn't expect in this project was how i could use the terminal to make changes that would reflect directly in the ec2 instance

## Launching an EC2 instance

### What I did in this step

In this step, I will launch a new EC2 instance,set up a key pair for secure access,set up network settings for the instance.

I started this project by launching an EC2 instance because this creates a virtual computer/server for the project.

![Launching an EC2 instance](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/b71d29bd-8a1b-5fe0-9572-1c575423d558_7852fbf3)

### I also enabled SSH

SSH is  a protocol used to make sure only authorized users can access a remote server I enabled SSH so that it verifies if you have the correct private key that matches the public key on the server.

### Key pairs

A key pair is a pair type determines the algorithm used for generating the key pair's cryptographic keys.

### Downloaded key pair file

Once I set up my key pair, AWS automatically downloaded.

## Set up VS Code

### What I did in this step

In this step, I will download VS Code ,set up a terminal in VS Code, so I can communicate with the EC2 instance,update the key pair's permission settings, so I can use it to log into the EC2 instance

### What is VS Code?

VS Code is code editor

I installed VS Code to communicate with EC2 through the terminal in the code editor

![Set up VS Code](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/b71d29bd-8a1b-5fe0-9572-1c575423d558_53d05e68)

## My first terminal commands

A terminal is an interface where you can send instructions. The first command I ran for this project is cd \~\\Desktop\\DevOps

### Updating file permissions

I also updated my private key's permissions by running the following commands icacls "kotei-keypair.pem" /reset, icacls "kotei-keypair.pem" /grant:r "gabby:R",icacls "kotei-keypair.pem" /inheritance:r

![My first terminal commands](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/b71d29bd-8a1b-5fe0-9572-1c575423d558_9328ada1)

## SSH connection to EC2 instance

### What I did in this step

In this step, I will connect to the EC2 instance.

### Connecting to EC2

To connect to my EC2 instance, I ran the command "ssh -i "C:\\Users\\Gabby\\Desktop\\Devops\\kotei-keypair.pem" ec2-user@ec2-13-220-102-193.compute-1.amazonaws.com"

### This command required an IPv4 address

A server's IPV4 DNS is the public address for the EC2 server that the internet uses to find and connect to it.

![SSH connection to EC2 instance](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/b71d29bd-8a1b-5fe0-9572-1c575423d558_e3069dca)

## Maven & Java

### What I did in this step

In this step, I will install Apache Maven on the EC2 instance,install Amazon Corretto 8, a version of Java and verify the installations.

### Why I'm using Maven

Apache Maven is a tool that helps developers build and organize Java software projects

Maven is required in this project because we need to set up all the necessary web files to create a web app structure, so we can jump straight into the fun part of developing the web app sooner.

### Why I'm using Java

Java is a programming language used to build different types of applications, from mobile apps to large enterprise systems.

Java is required in this project because we need it to be able to use Maven to generate/build the web app today.

## Create the Application

### What I did in this step

In this step, I will run Maven commands in your terminal to generate a Java web app.

### Creating the Java web app

I generated a Java web app using the command "mvn archetype:generate -DgroupId=com.nextwork.app -DartifactId=nextwork-web-project -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false"

### ✍️ Can you see your Java web app?  (Your response to this won't be in your documentation)

not yet

### Installing Remote - SSH

I installed Remote - SSH, which is an SSH extension in VS Code lets you connect directly via SSH to another computer securely over the internet. I installed it to connect to the EC2 instance

### SSH configuration details

Configuration details required to set up a remote connection include Host, HostName, IdentityFile and User

![Create the Application](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/b71d29bd-8a1b-5fe0-9572-1c575423d558_2939cf01)

## Create the Application

### Exploring the project structure

Using VS Code's file explorer, I could see the files in the nextwork-web-project folder

Two of the project folders created by Maven are src and webapp, which are the web app's files

![Create the Application](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/b71d29bd-8a1b-5fe0-9572-1c575423d558_45f91fd7)

## Using Remote - SSH

### What I did in this step

In this step, I will install an extension in VS Code,use the extension to set up a connection between VS Code and the EC2 instance and explore and edit the Java web app's files using VS Code.

### Updating the web app

The index.jsp is a file used in Java web apps. It's similar to an HTML file because it contains markup to display web pages.

I edited index.jsp by changing the header and body messages in the editor

![Using Remote - SSH](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/b71d29bd-8a1b-5fe0-9572-1c575423d558_7a1de541)

## Using nano

### Additional improvements

In this secret mission, I will edit index.jsp using the terminal instead of an IDE.

### Terminal vs IDE

An alternative to using IDEs is. using the terminal To edit index.jsp, I ran the command nano index.jsp

Compared to using an IDE, editing index.jsp in the terminal felt just like the IDE. I'd be more likely to use an IDE if the codes to write are a lot

### Verifying my work

To verify my editing work in the terminal, I added a new line to the index.jsp file It was possible to see my changes in VS Code right away because the ec2 environment is connected to my code editor locally through the SSH connection

![Using nano](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/b71d29bd-8a1b-5fe0-9572-1c575423d558_a3324ad41)
