<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Build an AI Chatbot with Amazon Bedrock

**Project Link:** [View Project](https://nextwork.ai/projects/5a33756f-a675-5a80-9738-048dc500cabc)

**Author:** Gabby Hammond

---

![](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/5a33756f-a675-5a80-9738-048dc500cabc_t4w8n1x5)

## Introducing Today's Project

In this project, I'm going to build an AI Chatbot with Amazon Bedrock.

### Key tools and concepts

The key tools I used include AWS bedrock and AWS Cloudshell Key concepts I learnt include large language models and guardrails

### Challenges and wins

This project took me approximately an hour

## Discovering Amazon Bedrock

In this step, I'm going to navigate to Amazon Bedrock in the AWS Console,explore foundation models in the Model catalog and chat with Amazon Nova 2 Lite in the playground.

![Discovering Amazon Bedrock](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/5a33756f-a675-5a80-9738-048dc500cabc_j5k8m3n6)

### Understanding Foundation Models

I learned that a foundation model is a large AI model that has been pre-trained on massive datasets.  Amazon Bedrock provides different foundational models from different providers

## Chatting with an AI Model

I sent a prompt about explaining cloud computing in 3 sentences The model responded by doing exactly that

![Chatting with an AI Model](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/5a33756f-a675-5a80-9738-048dc500cabc_b3c6d8f1)

## Writing My First AI API Call

In this step, I'm going to use CloudShell to write a Python script that calls the Bedrock Converse API and run the script and see an AI-generated response.

![Writing My First AI API Call](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/5a33756f-a675-5a80-9738-048dc500cabc_m4r9w2t6)

### Understanding the Converse API

I created a client using boto3 from python library.The messages list contains a dictionary with keys "role" and "content"

## Running the Bedrock Script

I ran my script and the AI responded with the answer to the prompt in the script The response came from the cloud shell terminal

![Running the Bedrock Script](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/5a33756f-a675-5a80-9738-048dc500cabc_b6d1g5k9)

## Building a Multi-Turn Chatbot

In this step, I am building a chatbot using bedrock. Conversation history matters because the large language models are stateles, for every time we invoke the LLM , it processes a brand-new, isolated event with zero memory of anything i asked it in the previous turn.

### System Prompt and Inference Parameters

I configured the system prompt to  give the chatbot a job description of the users before it starts talking to them. I adjusted the inferenceConfig to control how the model generates responses

![Building a Multi-Turn Chatbot](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/5a33756f-a675-5a80-9738-048dc500cabc_h5f2c8y7)

## Adding Guardrails for Responsible AI

In this project extension, I'm going to create a guardrail with content filters,add the guardrail to your Converse API call and test that harmful content requests get blocked.

![Adding Guardrails for Responsible AI](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/5a33756f-a675-5a80-9738-048dc500cabc_s6n3p9w1)

### Testing Content Safety

In this project extension, I tested the guardrail by writing a new script for the chatbot using the guardrails. i run the script and tested it with a harmful prompt. it responded by saying it can't generate harmful responses

![Adding Guardrails for Responsible AI](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/5a33756f-a675-5a80-9738-048dc500cabc_t2j7q5x8)

## Project Wrap-Up

I did this project today to build my portfolio Another skill I want to learn is building more complicated models
