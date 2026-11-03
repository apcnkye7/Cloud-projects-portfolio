![](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7e90bd3d-4280-57c7-ba1f-0fb7cf5673f3_dd9d254e)

## Introducing Today's Project!

In this project, I will demonstrate setting up Git and GitHub,connect the web app project to a GitHub repo, make changes to the web app code - and watch the GitHub repo update too,set up a README file for your repo.

### ✍️ What are we doing in this step?

In this step, I will launch an EC2 instance,set up VSCode on my local computer,use Remote - SSH to connect VSCode with the EC2 instance.

### ✍️ What are we doing in this step?

In this step, I will Install Git on my EC2 instance.

### Key tools and concepts

Services I used were EC2 instances, GIt Key concepts I learnt include Git commands

### Project reflection

This project took me approximately 60 minutes The most challenging part was configuring the git account It was most rewarding to follow the steps closely.

I did this project because I am building a portfolio

This project is part two of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project in 24 hours

## Git and GitHub

Git is like a time machine and filing system for your code. It tracks every change you make, which lets you go back to an earlier version of your work if something breaks. I installed Git using the commands "sudo dnf update -y\
sudo dnf install git -y"

### ✍️ What are we doing in this step?

In this step, I will set up a GitHub account,create a GitHub repository.

GitHub is a storage space for different version of a project that Git tracks .I'm using GitHub in this project to track my file activities

![Git and GitHub](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7e90bd3d-4280-57c7-ba1f-0fb7cf5673f3_efaadbf7)

## My local repository

A Git repository is a folder that contains all your project files and their entire version history.

### ✍️ What are we doing in this step?

In this step, I will set up a local git repo in your web app folder and connect the local repo with the GitHub repo.

Git init is a command that sets up the directory as a local Git repository which means changes are now tracked for version control. I ran git init in the ec2 instance

A branch in Git is a parallel versions or 'alternate universes' of the same project.After running git init, the response from the terminal was  "Initialized empty Git repository in /home/ec2-user/nextwork-web-project/.git/"

![My local repository](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7e90bd3d-4280-57c7-ba1f-0fb7cf5673f3_7bf21bae)

## To push local changes to GitHub, I ran three commands

### git add

The first command I ran was "git add .".A staging area is the area where Git  puts together all your modified files for a final review before you commit them.

### git commit

The second command I ran was "git commit -m "Updated index.jsp with new content" Using '-m' means leaving a message describing what the commit is about.

### git push

The third command I ran was "git push -u origin master" Using '-u' means  setting an 'upstream' for your local branch, which means you're telling Git to remember to push to master by default.

![To push local changes to GitHub, I ran three commands](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7e90bd3d-4280-57c7-ba1f-0fb7cf5673f3_c92fbe05)

## Authentication

When I commit changes to GitHub, Git asks for my credentials because Git needs to double check that you have the right to push any changes to the remote origin your local repo is connected with

### Local Git identity

Git needs my name and email because it has to authenticate

Running git log showed me the commit branch and author for the commit made

### ✍️ What are we doing in this step?

In this step, I will make changes to your web app,commit and push those changes.

![Authentication](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7e90bd3d-4280-57c7-ba1f-0fb7cf5673f3_9a27ee3b)

## GitHub tokens

GitHub authentication failed when I entered my password because GitHub phased out password authentication to connect with repositories over HTTPS as there are too many security risks and passwords can get intercepted over the interne

### ✍️ What are we doing in this step?

In this step, I will set up a token on GitHub,use the generated token to access the GitHub repo from the local repo.

A GitHub token is a unique string of characters that looks like a random password I'm using one in this project because authentication from http failed

I could set up a GitHub token by generating a classic token using the developer settings

![GitHub tokens](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7e90bd3d-4280-57c7-ba1f-0fb7cf5673f3_fa11169d)

## Making changes again

I wanted to see Git working in action, so I updated the index.jsp file I couldn't see the changes in my GitHub repo initially because i hadn't pushed those changes to my repository yet

I finally saw the changes in my GitHub repo after committing and pushing to my github repository

![Making changes again](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7e90bd3d-4280-57c7-ba1f-0fb7cf5673f3_6becb2bc)

## Setting up a READMe file

As a finishing touch to my GitHub repository, I added a README file, which is a document that introduces and explains your project, like what the project does, how to set it up, and how to use it.I added a README file by the command "touch README.md"

My README is written in Markdown because you can make words bold, create headers, add links, and use bullet points - all with simple symbols added to your text.

Special characters can help you format text in Markdown, such as @,#

My README file has 5 sections that outline the Introduction, Technologies, Setup, Contact, Conclusion

![Setting up a READMe file](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7e90bd3d-4280-57c7-ba1f-0fb7cf5673f3_c94976902)
