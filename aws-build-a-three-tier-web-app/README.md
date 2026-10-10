<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Three-Tier Web App

**Project Link:** [View Project](https://nextwork.ai/projects/f10f5983-0a15-5628-94b2-1cc37b19cb8c)

**Author:** Gabby Hammond  
**Email:** hammondgabby7436@gmail.com

---

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/f10f5983-0a15-5628-94b2-1cc37b19cb8c_2b3c4d5e)

## Designing a Three-Tier Web Application

### Project goals and learning objectives

In this project, I will demonstrate creating a three tier application using aws services. I'm doing this project to learn how to create a storage bucket for the  website's files with S3, distribute  content globally with CloudFront, build the brains of the  application using serverless functions with Lambda,create an API to handle user requests with API Gateway, store and retrieve user data with DynamoDB and connect all these services together seamlessly for the three-tier architecture.

## Delivering the Website Through CloudFront

### Presentation tier architecture

For the presentation tier, I will set up an S3 bucket to store the website's files,upload a simple index.html file to the bucket and set up CloudFront to deliver the website's content globally.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/f10f5983-0a15-5628-94b2-1cc37b19cb8c_3a4b5c6d)

### Accessing the delivered website

I accessed my delivered website by entering the cloudfront distribution domain url in my browser "https://d1ziu6l6z3zln3.cloudfront.net/"

## Building Serverless Application Logic

### Logic tier architecture

For the logic tier, I will set up a Lambda function to fetch data from a DynamoDB table,write  code for the Lambda function,create an API Gateway REST API,create a resource and method to handle GET requests,deploy the API to make it accessible.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/f10f5983-0a15-5628-94b2-1cc37b19cb8c_6a7b8c9d)

### Retrieving data with Lambda

The Lambda function retrieves data by looking for specific user data based on a userId and the returns that data

## Creating the DynamoDB Data Layer

### Data tier architecture

For the data tier, I will set up a DynamoDB table,add user data into your table.

### DynamoDB table design

The partition key for my DynamoDB table is "userID"which means we will query items in the table using their user id

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/f10f5983-0a15-5628-94b2-1cc37b19cb8c_u1v2w3x4)

## Connecting the Application Tiers

### Integration strategy

Once all three layers of my three-tier architecture are set up, the next step is to update the script.js file with JavaScript code to make an API request and verify that the data is displayed on the website.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/f10f5983-0a15-5628-94b2-1cc37b19cb8c_a112c3d5)

### Testing API responses

To test my API,  i invoked the prod stage url in my browser " https://vmqmr4an8e.execute-api.us-east-1.amazonaws.com/prod/users?userId=1" The results were the items stored in my dynamodb table.

### Investigating missing user data

Make a suggestion on why you can't see any user data yet. Don't be shy - this won't go in your documentation.
i don't think there is an api that allows you access user information from the front end of the website.

### Diagnosing the CloudFront error

The error in my distributed site was because the script for the website was missing the production stage api url that will allow me make the GET requests to the database

### Updating the website script

To resolve the error, I updated script.js by entering the production api url. I then reuploaded it into S3 because i needed the updated version for the frontend of the application to work 

## Troubleshooting and Validating the Full Web App

### End-to-end validation plan

In this step, I will test the CloudFront site again.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/f10f5983-0a15-5628-94b2-1cc37b19cb8c_a1b2c3d5)

### Diagnosing the browser error

I ran into a second error after updating script.js. This was an error with Cross-Origin Resource Sharing) because the API Gateway is not configured to allow requests from the CloudFront URL.  

### Resolving CORS in the API

To resolve the CORS error, I first enabled CORS for my users resources then i checked the "GET" and "OPTIONS" for the resource and entered the cloudfront domain url in the "Access-Control-Allow-Origin" box

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/f10f5983-0a15-5628-94b2-1cc37b19cb8c_1qthryj2)

### Updating Lambda for CORS

I also updated my Lambda function because when proxy integration is enabled, API Gateway simply forwards the request to the Lambda function and expects the Lambda to return the full HTTP response, including the CORS headers. The changes I made were to put the CORS response headers in the lambda function

### Verifying the completed connection

I verified the fixed connection between API Gateway and CloudFront by allowing CORS for the API resource and also adding CORS headers to the lambda function

## Reflecting on the Serverless Build

### Services and concepts learned

Services I used were AWS DynamoDB, AWS lambda, AWS API Gateway, AWS S3 , AWS IAM.Key concepts I learnt include Lambda functions, cross origin resource sharing, API resources and API methods

### Project experience and challenges

This project took me approximately 2 hours The most challenging part was reading the errors on the DevTools page It was most rewarding to read the error messages there and following the guidelines

### Learning reflection

I chose to do this project today because i am building a portfolio.Something that would make learning with NextWork even better is more secret projects

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/f10f5983-0a15-5628-94b2-1cc37b19cb8c)*
