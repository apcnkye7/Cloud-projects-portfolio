<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Add Custom Slots to a Lex Chatbot

**Project Link:** [View Project](https://nextwork.ai/projects/9b23ef35-9a36-5a21-9a3c-cfa3d61a0e2b)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### ✍️ What are we here to do today?

In this project, I will demonstrate adding custom slots to the Lex Chatbot

### ✍️ What are we doing in this step?

In this step, I will create a new bot from scratch on Amazon Lex

### ✍️ What are we doing in this step?

In this step, I will create my first slot to store a user's bank account type and save different bank account types that Lex should know.

In today's project, I used Amazon Lex to create custom slots for the chat bot

### What is Amazon Lex?

Amazon Lex is an AWS service that helps you create AI chatbots and it is useful because it simplifies the creation of AI chatbots from a complex infrastructure to a simple one

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how much technicality goes in the failure responses

### This project took me...

This project took me an hour

### ❤️ Thanks for doing this project!

I chose to do this project today because i am building a work portfolio.Something that would make learning with NextWork even better is more secret projects

## Slots

Slots are pieces of information that a chatbot needs to complete a user's request. Think of them as blanks that need to be filled in a form.

By adding custom slots in utterances, my chatbot's users  can provide business-specific values such accountType and dateOfBirth

In this project, I created a custom slot type to specify an account type

![Slots](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/9b23ef35-9a36-5a21-9a3c-cfa3d61a0e2b_97dc2351)

## Connecting slots with intents

This slot type has restricted slot values, which means  only the values that you specify will for the slot type will count as valid

### ✍️ What are we doing in this step?

In this step, I will set up a new intent for checking user's bank account balance and add slots in the intent, so Lex can store the user's bank account type and birthday.

I associated my custom slot with CheckBalance, which checks a users bank account balance and date of birth

![Connecting slots with intents](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/9b23ef35-9a36-5a21-9a3c-cfa3d61a0e2b_c4fc89af)

## Slot values in utterances

I included slot values in some of the utterances (i.e. user inputs) by adding a prompt in the slots for accountType and dateOfBirth

![Slot values in utterances](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/9b23ef35-9a36-5a21-9a3c-cfa3d61a0e2b_505be5b8)

## Handling failures in slot values

I added variations for the dateOfBirth slot prompt, such as "Sorry, that wasn't clear to me. What's your date of birth?"The messages play in order, so my end user will see message 1 before message 2 and message 3

I also used failure responses to make sure the FallBackIntent isn't triggered. A default setting I changed was to change the intent dropdown in the slot capture fail respone to "elicit a slot"

![Handling failures in slot values](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/9b23ef35-9a36-5a21-9a3c-cfa3d61a0e2b_a028bc8d2)
