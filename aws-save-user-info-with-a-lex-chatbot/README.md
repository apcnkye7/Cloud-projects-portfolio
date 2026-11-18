<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Save User Info with a Lex Chatbot

**Project Link:** [View Project](https://nextwork.ai/projects/19e304aa-a759-5670-97ff-e3e1c45436eb)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate saving User Info with a Lex Chatbot

### ✍️ What are we doing in this step?

In this step, I will set up a new Lex chatbot called BankerBot, set up a WelcomeIntent and a FallbackIntent  and a CheckBalance intent set up with a custom slot type called accountType. Then i generate random bank balance figures for the account balance

### ✍️ What are we doing in this step?

In this step, I will save the user's birthday from the CheckBalance intent.

### What is Amazon Lex?

Amazon Lex is an AWS service that helps you create AI chatbots and it is useful because it simplifies the creation of AI chatbots from a complex infrastructure to a simple one

### How I used Amazon Lex in this project

In today's project, I used Amazon Lex to create a banking bot with a feature that stores user birthday for a moment to make followup checks on their account balances easy.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was using an output context as an input context tag for another intent

### This project took me...

This project took me an hour

### ❤️ Thanks for doing this project!

I chose to do this project today because i am building a job portfolio.Something that would make learning with NextWork even better is more secret projects

## Context Tags

Context tags is a feature used to store and check for specific information across different parts of a conversation

There are two types of context tags: Output context tag and Input context tag

I created a context tag called "contextCheckBalance" This context tag was created in the intent "CheckBalance". This tag stores information about the user's birthday

### ✍️ What are we doing in this step?

In this step, I will set up a new intent  because there might be a scenario where we have to check multiple accounts for a user

![Context Tags](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/19e304aa-a759-5670-97ff-e3e1c45436eb_97dc2351)

## FollowUpCheckBalance

I created a new intent called FollowupCheckBalance. The purpose of this intent is to handle follow up questions without asking for the user's birthday again

### ✍️ What are we doing in this step?

In this step, I will set up FollowupCheckBalance's dateOfBirth slot to use saved information.

This intent is connected to the previous intent I made, CheckBalance, because that intent already returns random balances using the lambda function

![FollowUpCheckBalance](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/19e304aa-a759-5670-97ff-e3e1c45436eb_12345678)

## Input Context Tag

I created an input context, contextCheckBalance, that  is the output context in the primary CheckBalance intent

![Input Context Tag](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/19e304aa-a759-5670-97ff-e3e1c45436eb_c4fc89af)

## The final result!

To see the context tags and followup intent in action, I used the command "and savings?"

If I had gone straight to trying to trigger FollowUpCheckBalance without setting up any context the chatbot wouldn't have understood that command

![The final result!](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/19e304aa-a759-5670-97ff-e3e1c45436eb_505be5b8)

## Managing context expiry

An extension for this project is to manage contextCheckBalance's context expiry, which means how long your bot will remember information for. By default, expiry is in 90 secs

I updated my bot's context expiry to 1 turn and 5 secs What this means for my end users is that the bot will forget context from your first balance check in just 1 message, or 5 seconds.

A long context expiry window would be helpful when you expect the user to have long conversations and run through multiple intents in the same session. A shorter context expiry window would be helpful when  information is sensitive and you'd want to protect the user from attackers getting access to chat windows with lots of active contexts.

![Managing context expiry](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/19e304aa-a759-5670-97ff-e3e1c45436eb_81b763822)
