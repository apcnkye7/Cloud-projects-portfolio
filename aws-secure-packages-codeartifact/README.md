## Introducing Today's Project!

In this project, I will demonstrate setting up CodeArtifact as a repository for your project's dependencies, use IAM roles and policies to give your web app access to CodeArtifact and verify the web app's connection to CodeArtifact, create and add  packages to the CodeArtifact repository

### ✍️ What are you doing in this step and why?

To set up for this project, I am launching an EC2 instance

### ✍️ What are you doing in this step and why?

In this step, I will use the terminal to connect to your EC2 instance via SSH,install Java and Maven on the EC2 instance,\
generate a basic Java web app,connect VS Code to the EC2 instance using the Remote - SSH extension.

### ✍️ What are you doing in this step and why?

In this step, I will install Git on the EC2 instance,set up a GitHub repository,connect the local web app to the GitHub repository.

### ✍️ Why are you setting up CodeArtifact repository in this project?

In this step, I will create and configure a new CodeArtifact repository because CodeArtifact provides a centralized, secure, and scalable way to manage dependencies for the Java projects, improving build consistency and security.

### Key tools and concepts

Services I used were EC2,IAM , CloudShell and CodeArtifiact Key concepts I learnt include CodeArtifact repositories,domains, configuring a settings.xml file so maven can work with CodeArtifact

### Project reflection

This project took me approximately 2 hours,It was most rewarding to follow the step by step guidance carefully

### ✅ Why did you do this project today?

I did this project today because i am building a portfolio

This project is part three of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project n 24 hours

## CodeArtifact Repository

CodeArtifact is  a secure, central place to store all your software packages. Engineering teams use artifact repositories because they can easily share and use the same versions of packages, instead of everyone working with a different version of the same package.

A domain is a folder that holds multiple repositories belonging to the same project or organization. My domain is "kotei"

A CodeArtifact repository can have an upstream repository, which means a  backup library that the primary repository can access when it doesn't have what you need.My repository's upstream repository is Maven Central

![CodeArtifact Repository](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/8c60d99f-e8ff-519e-a0d6-e8dfe8fa1b67_n4o5p6q7)

### ✍️ What are we doing in this step?

In this step, I will try connecting Maven with CodeArtifact, create a new IAM policy,set up the policy to grant an EC2 instance access to CodeArtifact.

## CodeArtifact Security

### Issue

To access CodeArtifact, we need an authorization token. I ran into an error when retrieving a token because AWS operates on a principle of least privilege and our EC2 instance doesn't have permissions to access CodeArtifact

### Resolution

To resolve the error with my security token, I created a policy that gives me access to certain pemissions to CodeArtifact, then i attached this policy to an IAM role which was attached to the ec2 instance i am currently running. This resolved the error because the ec2 instance now has the necessary permissions for CodeArtifact

### ✍️ What are you doing in this step and why?

In this step, I will verify the CodeArtifact connection by finish setting up the connection between Maven and CodeArtifact,compile thhe Maven project using the settings.xml file.

It's security best practice to use IAM roles because roles can be used to define the kind of access one can have to resources on AWS

## The JSON policy attached to my role

The JSON policy I set up grants the IAM to get authorization token, repository endpoint, read from repository from CodeArtifact

### ✍️ What are we doing in this step?

In this step, I will create a new IAM role for EC2 that has the new policy attached,attach the IAM role to the EC2 instance and re-run the export token command

![The JSON policy attached to my role](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/8c60d99f-e8ff-519e-a0d6-e8dfe8fa1b67_23rp7q8r9)

## Maven and CodeArtifact

### To test the connection between Maven and CodeArtifact, I compiled my web app using settings.xml

The settings.xml file configures Maven how to behave across all the projects. By configuring settings.xml properly, we're creating a seamless connection between Maven and CodeArtifact.

Compiling means translating the project's code into a language that computers can understand and run.

![Maven and CodeArtifact](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/8c60d99f-e8ff-519e-a0d6-e8dfe8fa1b67_c17eace8)

## Verify Connection

After compiling, I checked the packages page in the CodeArtifact dashboard and saw the packages uploaded

![Verify Connection](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/8c60d99f-e8ff-519e-a0d6-e8dfe8fa1b67_1d79e699)

## Uploading My Own Packages

In a project extension, I also decided to create my own custom package,publish it directly to my CodeArtifact repository,experience the full package lifecycle by downloading my own package\
This is useful in situations where intellectual property comes into play

To create my own package, I first created a simple text document in aws cloudshell using the command "echo "Hellooooo this is a test package!" \> secret-mission.txt", next i bundled the text file int a compressed form using "tar -czvf secret-mission.tar.gz secret-mission.txt"I also generated a security hash because CodeArtifact requires a security hash to verify its integrity

To publish the package, I used the command "aws codeartifact publish-package-version \\\
  \--domain kotei \\\
  \--repository kotei-devops-cicd \\\
  \--format generic \\\
  \--namespace secret-mission \\\
  \--package secret-mission \\\
  \--package-version 1.0.0 \\\
  \--asset-content secret-mission.tar.gz \\\
  \--asset-name secret-mission.tar.gz \\\
  \--asset-sha256 $ASSET\_SHA256" \
When I look at the package details in CodeArtifact, I can see the version status and origin of the new package created

To validate my packages, I then downloaded using the command\
"aws codeartifact get-package-version-asset \\\
\>   --domain kotei \\\
\>   --repository kotei-devops-cicd \\\
\>   --format generic \\\
\>   --namespace secret-mission \\\
\>   --package secret-mission \\\
\>   --package-version 1.0.0 \\\
\>   --asset secret-mission.tar.gz \\\
\>   secret-mission.tar.gz"\
I viewed the downloaded file with the command "tar -xzvf secret-mission.tar.gz\
secret-mission.txt\
\~ $ cat secret-mission.txt" and saw the contents of the txt file

![Uploading My Own Packages](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/8c60d99f-e8ff-519e-a0d6-e8dfe8fa1b67_sm12-upload)
