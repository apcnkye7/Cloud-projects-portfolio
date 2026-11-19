<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Set Up Multiple Slots in a Lex Chatbot

**Project Link:** [View Project](https://nextwork.ai/projects/13cfd692-9802-5c98-ada7-92fde8b30a99)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate setting up multiple slots in a Lex Chatbot

### ✍️ What are we doing in this step?

In this step, I will demonstrate  setting up multiple slots in a Lex Chatbot.

### ✍️ What are we doing in this step?

In this step, I will set up a new intent that uses two accountType slots.

### What is Amazon Lex?

Amazon Lex is an AWS service that helps you create AI chatbots and it is useful because it simplifies the creation of AI chatbots from a complex infrastructure to a simple one

### How I used Amazon Lex in this project

In today's project, I used Amazon Lex to set Up Multiple Slots in a Lex Chatbot

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the visual builders

### This project took me...

This project took me about an hour

### ❤️ Thanks for doing this project!

I chose to do this project today because i am building a job portfolio.Something that would make learning with NextWork even better is more secret missions

## TransferFunds

An intent I created for my chatbot was TransferFunds, which is used for transferring money between accounts

![TransferFunds](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/13cfd692-9802-5c98-ada7-92fde8b30a99_67890123)

## Using multiple slots

For this intent, I had to use the same slot type twice. This is because i am transferring from one account to another and both belong to the slot "accountType"

### ✍️ What are we doing in this step?

In this step, I will explore Lex's conversation flow feature and explore Lex's visual builder feature.

I also learnt how to create confirmation prompts, which are \
 repeat back information for the user to confirm.

![Using multiple slots](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/13cfd692-9802-5c98-ada7-92fde8b30a99_97dc2351)

## Exploring Lex features

Lex also has a special conversation flow feature that shows every step in a conversation in a logical, chronological order.

You could also set up your intent using a visual builder! A visual builder is a visual representation of the intent you  build. Visual builders can be used to build intents from scratch

### ✍️ What are we doing in this step?

In this step, I will use CloudFormation to deploy BankerBot in seconds and resolve connection issues with the deployed bot.

![Exploring Lex features](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/13cfd692-9802-5c98-ada7-92fde8b30a99_12345678)

## AWS CloudFormation

AWS CloudFormation is service that  gives you an easy way to create and set up AWS resources using infrastructure as code.

I used CloudFormation to deploy a banker bot

![AWS CloudFormation](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/13cfd692-9802-5c98-ada7-92fde8b30a99_c4fc89af)

## The final result!

Re-building my bot with CloudFormation took me less than 5 minutes

There was an error after I deployed my bot! The error was "Access denied while invoking lambda function". I fixed this by giving my lambda function the permission by adding a resource based policy statement

![The final result!](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/13cfd692-9802-5c98-ada7-92fde8b30a99_505be5b8)

## Using the visual builder

Using the visual builder, I added a new slot for checking balance after transfer , if the transfer is successful and the user wants to check balance, the check balance intent is triggered and if the the user doesn't want to check balance after the transfer the conversation ends.

The new Get slot value card will trigger when the transfer is complete. This card will try to capture whether the use wants to check the account balance

![Using the visual builder](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/13cfd692-9802-5c98-ada7-92fde8b30a99_9cac15cd4)
