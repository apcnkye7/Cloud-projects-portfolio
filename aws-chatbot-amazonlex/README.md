<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Build a Chatbot with Amazon Lex

**Project Link:** [View Project](https://nextwork.ai/projects/143bcc99-ef5a-58e7-96f0-45d7c00b761a)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate building AI chatbots using Amazon Lex

### What is Amazon Lex?

Amazon Lex is an AWS service that helps you create AI chatbots

### Key tools and concepts

Services I used were amazon lex.Key concepts I learnt include chatbots,nlp , WelcomeIntent and FallbackIntent

### Personal reflections

One thing I didn't expect in this project was the concept of intents

### Project timeline

This project took me approximately 40 minutes.

### ❤️ Thanks for doing this project!

I chose to do this project today because I am building a portfolio for work. Something that would make learning with NextWork even better is more secret projects

## Setting up a Lex chatbot

### Approach to chatbot setup

In this step, I will create a new bot from scratch on Amazon Lex

### Chatbot creation process

I created my chatbot from scratch with Amazon Lex. Setting it up took me about 5 minutes

### IAM role configuration

While creating my chatbot, I also created a role with basic permissions because Amazon Lex needs the permission to call other AWS services on my behalf

### Intent classification confidence score

In terms of the intent classification confidence score, I kept the default value of 0.40. This means that the chatbot needs to be at least 40% confident that it understands what the user is asking to be able to give a response.

![Setting up a Lex chatbot](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/143bcc99-ef5a-58e7-96f0-45d7c00b761a_97dc2351)

## Intents

In this step, I will Train BankerBot to greet the users.

### Creating my first intent

Intents are what the user is trying to achieve in their conversation with the chatbot

I created my first intent, WelcomeIntent, to welcome a user when they say hello

### Testing chatbot responses

I launched and tested my chatbot, which could respond successfully if I enter "hiya","help me"

## Handling unrecognized inputs

My chatbot returned the error message 'Intent FallbackIntent is fulfilled' when I entered "how are you", "good afternoon" This error message occurred because Amazon Lex doesn't recognize those utterances

![Handling unrecognized inputs](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/143bcc99-ef5a-58e7-96f0-45d7c00b761a_505be5b8)

## Configuring FallbackIntent

In this step, I will customise FallbackIntent to send user-friendly messages

### When FallbackIntent triggers

FallbackIntent is a default intent in every chatbot that gets triggered when the chatbot has a confidence score below the threshold you set for all intents.

I wanted to configure FallbackIntent because I wanted to customise FallbackIntent to send user-friendly messages

### My FallbackIntent configuration

To configure FallbackIntent, I changed the closing response messages when the FallbackIntent was triggered

I also added variations! What this means for an end user is it helps them modify their responses in a way for the chatbot to understand

## FallbackIntent with Variations

![FallbackIntent with Variations](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/143bcc99-ef5a-58e7-96f0-45d7c00b761a_c4fc89af)

## Initial Responses

In this project extension I'm about to modify the FallbackIntent with an initial response,add variations to the initial response.

### Setting up initial responses

Initial responses are  greetings or confirmations the chatbot sends right after it figures out the user's intent. Lex would send the initial response at the very start of your intent's flow, before anything else you've set up in the intent. I've set up initial responses for making the bot sound more human like in the conversation

### Initial response implementation

The initial response messages I set up are "One moment" and "Hmm this is interesting".For the user, this means the chatbot still doesn't quite get what he or she is trying to say

![Initial Responses](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/143bcc99-ef5a-58e7-96f0-45d7c00b761a_09bcb9701)
