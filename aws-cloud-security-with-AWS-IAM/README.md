<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Cloud Security with AWS IAM

**Project Link:** [View Project](https://nextwork.ai/projects/51a5fd24-7458-58a6-8653-9b90119a0e4a)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate cloud security with IAM I'm doing this project to learn to authorize and authenticate users in a cloud network

### Tools and concepts

Services I used were AWS IAM and AWS ec2.Key concepts I learnt include Iam users,user groups, alias, json policies and IAM policy simulator

### Project reflection

This project took me approximately 90 minutes The most challenging part was the simulator and the json policy code It was most rewarding to see everything working after debugging correctly

### ❤️ Thanks for doing this project!

I chose to do this project today because i wanted to learn how to implement cloud security through IAMs. Something that would make learning with NextWork even better is make the secret projects more

## Tags

### What I did in this step

In this step, I will launch EC2 instances because i want to increase computing  power

### Understanding tags

Tags are labels attached to AWS resources for proper organization

### My tag configuration

The tag I’ve used on my EC2 instances is called kotei-dev The value I’ve assigned for my instances are production and development

![Tags](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-iam_2e0e5a5d)

## IAM Policies

### What I did in this step

In this step, I will create an IAM policy because i want to control the kind of access users can have to the ec2 instances .

### Understanding IAM policies

IAM Policies are rules for what you can do with AWS resources

### The policy I set up

For this project, I’ve set up a policy using JSON

### Policy effect

I’ve created a policy that controls what can be done in the ec2 instances created. There are policies for the kind of access you can have in the instances based on the environments you are working on using the tags assigned to the instances

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy means whether a policy allows or denies an action, the action is what you can and can't do and the resource is what the policy applies to

## My JSON Policy

![My JSON Policy](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-iam_1c864649)

## Account Alias

### What I did in this step

In this step, I will simply create an aws account alias because i need to give access to the instances created

### Understanding account aliases

An account alias is a friendly name you can use to log in to your management console instead of your account id

### Setting up my account alias

Creating an account alias took me 2 minutes Now, my new AWS console sign-in URL is https://kotei-alias.signin.aws.amazon.com/console

![Account Alias](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-iam_0eb4439b)

## IAM Users and User Groups

### What I did in this step

In this step, I will set up a dedicated IAm group  because i want to manage permissions to the instances i have created

### Understanding user groups

IAM user groups are a collection of IAM users

### Attaching policies to user groups

I attached the policy I created to this user group, which means users in the IAM group can only interact with the instances created based on the rules defined in the policies created for the user group

### Understanding IAM users

IAM users are people that will get access to resources in the AWS account

## Logging in as an IAM User

### Sharing sign-in details

The first way is through sharing the csv file with the sign in details or email sign instructions to the user

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed AWS is giving me instrcutions for a newly logged in user and also i have being denied access to some services.This was because of the permisions decided in the policies created for the IAM user

![Logging in as an IAM User](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-iam_6f2ab446)

## Testing IAM Policies

### What I did in this step

In this step, I will log in using the IAM users i have created because I want to test the access policies i have created for the IAM users

### Testing policy actions

I tested my JSON IAM policy by logging in as an IAM user and tried stopping the production and development instances

### Stopping the production instance

When I tried to stop the production instance i received a failed to stop error This was because the policy defined doesn't allow actions on the production instance

![Testing IAM Policies](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance it worked this was because the IAM policy defined for the IAM user allows it

![Testing IAM Policies](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-iam_1811801c)

## IAM Policy Simulator

To extend my project, I'm going to test IAM policies using the IAM policy simulator I'm doing this because testing IAM policies can be disruptive to other users

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is a tool that allows you simulate actions and test permissions. It's useful for testing policies for IAM users without creating disruptions and logging in as an IAM user

### How I used the simulator

I set up a simulation for whether the dev user group has permissions to stop instances  or delete tags for the ec2 instances.The results were denied for both so I had to adjust the tags for the simulation scope

![IAM Policy Simulator](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-iam_069d8a621)
