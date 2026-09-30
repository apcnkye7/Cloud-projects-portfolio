<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# APIs with Lambda + API Gateway

**Project Link:** [View Project](https://nextwork.ai/projects/2af91800-3f42-5fc1-b405-c5069180c0df)

**Author:** Gabby Hammond  
**Email:** hammondgabby7436@gmail.com

---

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/2af91800-3f42-5fc1-b405-c5069180c0df_c9d0e1f2)

## Introducing Today's Project!

In this project, I will demonstrate APIs with API Gateway and Lambda functions.I'm doing this project to learn building the logic tier of an application using aws services.

### Tools and concepts

Services I used were API gateway and AWS Lambda functions. Key concepts I learnt include Lambda functions, API resources, API methods, deployment stages and API documentation

### Project reflection

This project took me approximately an hour.

I chose to do this project today because i am building a portfolio.Something that would make learning with NextWork even better is more secret missions.

## Lambda functions

AWS Lambda is a service that lets you run code without needing to manage any computers/servers. I'm using Lambda in this project to write code to fetch data from a database and provide it to a user on the website.

The code I added to my function will retrieve data from a dynamoDB table. It looks for specific user data based on a 'userId' and returns that data. If there's an error e.g. the userId doesn't exist in the database, it returns an error message.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/2af91800-3f42-5fc1-b405-c5069180c0df_a1b2c3d5)

## API Gateway

APIs are ways through which different software systems to talk to each other. There are different types of APIs, like REST API,HTTP and WebSocket.My API is a REST API

Amazon API Gateway is an AWS service that makes it easy for developers to create, publish, maintain, monitor, and secure APIs at any scale. I'm using API Gateway in this project to act as a front door to my lamda functions(it receives requests and forwards them to the lambda function for processing).

When a user makes a request the API gateway forwards the request to the lambda function for processing and it returns the response from the lambda function back to the user

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/2af91800-3f42-5fc1-b405-c5069180c0df_m3n4o5p6)

## API Resources and Methods

An API is made up of resources, which  are individual endpoints within your API that handle different parts of its functionality

Each resource consists of methods, which are the actions you can perform on a resource.

I created a GET method for the /users resource that willl pass the request to the Lamdba function.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/2af91800-3f42-5fc1-b405-c5069180c0df_c9d0e1f2)

## API Deployment

When you deploy an API, you deploy it to a specific stage. A stage is is a snapshot of your API at a specific point in time. I deployed to prod(production)

To visit my API, I deployed the API to the production stage and used the  invoke URL in my browser.The API displayed an error because the DynamoDB table hasn't been set up yet.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/2af91800-3f42-5fc1-b405-c5069180c0df_3ethryj2)

## API Documentation

For my project's extension, I am writing API documentation because. i  want a documentation explaining how to use my API correclty and efficiently.You can do this in API gateway

Once I prepared my documentation, I can publish it to the production stage.You have to publish your API to a specific stage because the documentation has to be consistent with the API version deployed to that stage.

My published and downloaded documentation showed me my API documentation and other documentation that API Gateway has automatically generated.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/2af91800-3f42-5fc1-b405-c5069180c0df_z9a0b1c2)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/2af91800-3f42-5fc1-b405-c5069180c0df)*
