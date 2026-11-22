<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# AI Email Router with Bedrock Flows

**Project Link:** [View Project](https://nextwork.ai/projects/1ad0650f-9ca0-5154-9968-d73bd3d10eed)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

Today I am building a complete email routing pipeline in Amazon Bedrock Flows that takes a raw customer email, classifies it as a complaint, question, or refund request using a prompt template, then routes it through a condition node to generate the appropriate tailored response.

## Navigating Amazon Bedrock

In this step, I am getting ready to build by setting up amazon bedrock

![Navigating Amazon Bedrock](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_f3j8w2n5)

## Creating the Classifier Prompt

In this step, I am creating a classifier prompt in Prompt Management that categorizes emails by intent,then I test the classifier with sample emails and create a version of my prompt.

### Understanding the classifier prompt

This prompt tells the AI to read the  customer email and classify it as exactly one of: complaint, question, or refund.

![Creating the Classifier Prompt](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_x9m3t6k1)

### How the classifier works

When I tested the classifier, it output. the response in lowercase. The format matters because if the format of the responses changes, the routing breaks, thus the prompt needs to be updated.

## Building the Response Prompt Library

In this step, I am creating  a complaint response prompt with an empathetic tone and  a general-purpose response prompt.

![Building the Response Prompt Library](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_y2j8b4w6)

## Building the Email Router Flow

In this step, I am going to create a Bedrock Flow with the email classifier prompt,add a condition node to route emails by classification and connect two response prompts and save the flow.

![Building the Email Router Flow](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_w3x8n5q2)

### How the classifier routes emails

The modelCompletion output contains whatever the AI model outputs - in our case, the classification label (complaint, question, or refund).

![Building the Email Router Flow](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_h4y2c8f6)

### Completing the flow architecture

The flow connects to the EmailClassifier prompt, the ComplaintResponse promt and the  The classifier output feeds into the Complaintchecker  which routes to the ComplaintResponsePrompt and the GeneralResponsePrompt

![Building the Email Router Flow](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_a5d3g7k1)

## Testing and Debugging the Flow

In this step, I am testing an email through the flow,verifying that different email types route correctly and using the trace viewer to debug your flow.

![Testing and Debugging the Flow](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_p4w8n1y6)

### Tracing the email routing path

The classifier output was "complaint" and the condition node routed it to to the nodeName "ComplaintChecker"

![Testing and Debugging the Flow](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_v6b1c8f4)

### How default routing works

The question email reaches the general response branch because i only set up one explicit condition for "complaint" , everything else falls through the default path as a generaal purpose response prompt

## Adding Content Safety with Guardrails

### Configuring content filters

I enabled filters for harmful user inputs or prompts.Filtering is important because it ensures the classification model works on safe, clean, and relevant data while protecting your system from malicious threats and high costs.

![Adding Content Safety with Guardrails](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_v8km3q2x)

### Normal vs. harmful email behavior

I sent a normal email and it classified it as a normal message. Then I sent a harmful email and the guardrails were activated.

![Adding Content Safety with Guardrails](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_j6yd2m8k)

![Adding Content Safety with Guardrails](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/1ad0650f-9ca0-5154-9968-d73bd3d10eed_w3bp5n1f)

## Wrapping Up

The key tools I used include IAM roles and Amazon Bedrock.Key concepts I learnt include IAM permissions, Flowbuilder ,prompts and Guardrails

### Time and effort

This project took me approximately an hour. The most challenging part was the guardrail part.

### What's next

I did this project today to build my portfolio.Another skill I want to learn is to build more sophisticated models myself
