<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Connect Amazon Lex with Lambda

**Project Link:** [View Project](https://nextwork.ai/projects/05a8853b-a1e0-5be3-a93f-adeecd72e61c)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate connecting Amazon Lex with Lambda

### ✍️ What are we doing in this step?

In this step, I will create a new bot from scratch on Amazon Lex,set up a WelcomeIntent,customize a FallbackIntent, i.e. the BankerBot says a customised error message if it doesn't understand the user's input and set up a CheckBalance with a custom slot type called accountType.

### ✍️ What are we doing in this step?

In this step, I will use AWS Lambda to generate random bank balance numbers.

### What is Amazon Lex?

Amazon Lex is an AWS service that helps you create AI chatbots and it is useful because it simplifies the creation of AI chatbots from a complex infrastructure to a simple one

### How I used Amazon Lex in this project

In today's project, I used Amazon Lex to customize a chatbot with the addition of a lambda function to automatically generate random numbers as an account balance for the accounts in the chatbot

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the use of lambda functions integrating directly to the chatbot

### This project took me...

This project took me 40 minutes

### ❤️ Thanks for doing this project!

I chose to do this project today because I am building a portfolio.Something that would make learning with NextWork even better is more secret projects

## AWS Lambda Functions

is a service that lets you run code in the cloud without needing to manage any computers/servers

In this project, I created a Lambda function to generate randome numbers for a bank account balance

### ✍️ What are we doing in this step?

In this step, I will connect the Lambda function to BankerBot.

![AWS Lambda Functions](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/05a8853b-a1e0-5be3-a93f-adeecd72e61c_97dc2351)

## Chatbot Alias

An alias is like a pointer for a specific version of the bot.

TestBotAlias is  a default version of the bot that's made for testing or development.

To connect Lambda with my BankerBot, I visited my bot's TestBotAlias and and clicked on the language for the alias. i changed the source to BankingBotEnglish and for the lambda function version or alias, i selected the $LATEST option

### ✍️ What are we doing in this step?

In this step, I will connect the Lambda function to the CheckBalance intent.

![Chatbot Alias](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/05a8853b-a1e0-5be3-a93f-adeecd72e61c_c4fc89af)

## Code Hooks

A code hook is a feature that helps you connect your chatbot to custom Lambda functions for doing specific tasks during a conversation.

Even though I already connected my Lambda function with my chatbot's alias, I had to use code hooks because the hooks are used to handle more complex actions that the basic chatbot setup can't do on its own, like checking data from a database or making decisions based on past conversations.

I could find code hooks at "On successful fulfilment bubble"

![Code Hooks](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/05a8853b-a1e0-5be3-a93f-adeecd72e61c_505be5b9)

## The final result!

I've set up my chatbot to trigger Lambda and return a random dollar figure when the a user tells your bot the account they want to check, and their birthday for verification

![The final result!](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/05a8853b-a1e0-5be3-a93f-adeecd72e61c_505be5b8)

## Customizing the Lambda function

To level up the connection between Lambda and Lex, I am updating the message that the chatbot would send back to users when they're checking their account balance.

Now, the message my users see when they ask for their bank balance is " Hello! Your Savings account balance, tucked away in bank of Ghana, is currently $276.89."I can customise this message even further by further editing the description variable in the lambda function

![Customizing the Lambda function](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/05a8853b-a1e0-5be3-a93f-adeecd72e61c_38b5f5691)
