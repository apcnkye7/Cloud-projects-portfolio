<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Secure Secrets with Secrets Manager

**Project Link:** [View Project](https://nextwork.ai/projects/d6a05ea4-6c31-5e53-8688-de54814d6209)

**Author:** Gabby Hammond

---

![](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/d6a05ea4-6c31-5e53-8688-de54814d6209_r7s8t9u0)

## Introducing Today's Project!

In this project, I will demonstrate how to use AWS Secrets Manager .I'm doing this project to learn to securely store and retrieve application credentials.

### ✍️ What are we doing in this step?

In this step, I'm going to access a GitHub repository containing a web app's code, identify where credentials are stored,clone the repository to my computer and hardcode the AWS credentials.

### Tools and concepts

Services I used were aws secrets manager, s3 buckets and IAM Key concepts I learnt include using secrets manager to store sensitive credentials for use in external applications without having to hardcode them

### Project reflection

This project took me approximately 120 minutesThe most challenging part was setting up the secrets manager and app configuration in my terminal.It was most rewarding to read the errors and figure out what was wrong

I chose to do this project today because i am trying to build a portfolio for work.Something that would make learning with NextWork even better is clarity on some of the projects. Running the app.py in this project required aws configure which wasn't captured in the project details

## Hardcoding credentials

In this project, a sample web app is exposing the AWS credentials of an active AWS account It is unsafe to harcode credentials because unauthorized users can log into the AWS account using those credentials to steal data and cause damage

I've set up the initial configuration with "AWS\_ACCESS\_KEY\_ID = YOUR_AWS_ACCESS_KEY_ID\
AWS\_SECRET\_ACCESS\_KEY = YOUR_AWS_SECRET_ACCESS_KEY\
AWS\_REGION = "us-east-2""\
 These credentials are just examples because using  my actual credentials is not a secure approach .

### ✍️ What are we doing in this step?

In this step, I'm going to make a copy of the original repository, push the code with the example credentials to my Github and use Github secret scanning

![Hardcoding credentials](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/d6a05ea4-6c31-5e53-8688-de54814d6209_j2k3l4m5)

## Using my own AWS credentials

As an extension for this project, I also decided to install all the dependencies required for the app.py to run to set up my virtual environment, I installed python3 and pip. i used the command "python -m venv venv" to set up the environment and used ".\\venv\\Scripts\\activate" to activate the virtual environment. \
Then i run "pip install -r requirments.txt" to install all the dependencies required for the application

When I first ran the app, I ran into an error because the  credentials in config.py, which are not real AWS credentials.

To resolve the 'InvalidAccessKeyId' error, I updated the config.py file with the aws credentials of one of the IAM users i created.

![Using my own AWS credentials](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/d6a05ea4-6c31-5e53-8688-de54814d6209_wghjteykut)

## Pushing Insecure Code to GitHub

Once I updated the web app code with credentials, I forked the repository because the fork allows me to make changes without affecting the main repository. A fork is different from a clone a fork allows me to make online changes to the repository while a clone makes the repository offline

To connect my local repository to the forked repository, I used the command "git  remote set-url origin \<repo\_url\>"Then I used git add and git commit to stage the changes and save a snapshot of the changes respectively. Finally, git push uploads the local commits to the repository

GitHub blocked my push because it contained an AWS access key ID and a secret key .This is a good security feature because it prevents accidental exposure of secrets

### ✍️ What are we doing in this step?

In this step, I'm going to create a new secret in Secrets manager to store the example AWS credentials because Github automatically blocks pushing code with hardcoded credentials

![Pushing Insecure Code to GitHub](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/d6a05ea4-6c31-5e53-8688-de54814d6209_o2p3q4r5)

## Secrets Manager

Secrets Manager is a service that helps you securely store and manage secrets, such as database credentials, API keys, and other sensitive information.I'm using it to store the AWS credentials. Other common use cases include storing database credentials

Another feature in Secrets Manager is secret rotation which means the process of automatically changing your secrets on a regular schedule.It's useful in situations where a secret gets compromised.

Secrets Manager provides sample code in various languages, like python This is helpful because it helps develops integrate with their applications easily.

### ✍️ What are we doing in this step?

In this step, I'm going to use the sample code from the AWS secrets manager and update the config.py file to use the secrets manager instead because i want to make the config.py file a more secure file.

![Secrets Manager](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/d6a05ea4-6c31-5e53-8688-de54814d6209_h2i3j4k5)

## Updating the web app code

I updated the config.py file to retrieve the AWS credentials from secrets manager. The get\_secret() function will be is responsible for retrieving the secret from Secrets Manager.

I also added code to config.py to extract the credentials from the secret and assigning them to the AWS\_ACCESS\_KEY\_ID, AWS\_SECRET\_ACCESS\_KEY, and AWS\_REGION variables. This is important because the  app.py code expects them

![Updating the web app code](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/d6a05ea4-6c31-5e53-8688-de54814d6209_v0w1x2y3)

## Rebasing the repository

Git rebasing is  a feature in github.I used it to restart a commit session by droping the first commit This was necessary because the first commit has hardcoded aws credentials which gets picked up by github in the subsequent commits

A merge conflict occurred during rebasing because i changed some same lines of codes in different git commit sessions. I resolved the merge conflict by deleting the conflicting lines detected by git

Once the merge conflict was resolved, I verified it by running the "git rebase --continue" and then running "git push" to push the updated config file. I then checked the config file content in the github repo

![Rebasing the repository](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/d6a05ea4-6c31-5e53-8688-de54814d6209_t5u6v7w8)
