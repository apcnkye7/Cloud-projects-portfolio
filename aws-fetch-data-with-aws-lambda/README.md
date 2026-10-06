<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Fetch Data with AWS Lambda

**Project Link:** [View Project](https://nextwork.ai/projects/465096ce-f136-53fb-8a99-ebab7c406cd9)

**Author:** Gabby Hammond  
**Email:** hammondgabby7436@gmail.com

---

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/465096ce-f136-53fb-8a99-ebab7c406cd9_p9thryj2)

## Introducing Today's Project!

In this project, I will demonstrate fetching data with AWS lambda. I'm doing this project to learn how to store and manage application data with AWS

### Tools and concepts

Services I used were lamda functions, DynamoDB tables.Key concepts I learnt include Lambda functions,Lambda execution roles ,inline policies and lambda tests.

### Project reflection

This project took me approximately 60 minutes 

I chose to do this project today because i am building my portfolio for a job role. Something that would make learning with NextWork even better is more secret projects

## Project Setup

To set up my project, I created a database using DynamoDB table. The partition key is "userID" which means i will be using this key to query the database for quick and efficient access.

In my DynamoDB table, I added the following attributes "{
  "userId": "1",
  "name": "Test User",
  "email": "test@example.com"
}"DynamoDB is schemaless, which means you can add attributes as you need, and every item in your database can have a different set of attributes.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/465096ce-f136-53fb-8a99-ebab7c406cd9_a112c3d5)

### AWS Lambda

AWS Lambda is is a service that lets you run code without needing to manage any computers/servers.I'm using Lambda in this project to write code that retrieves data from tables on demand.

## AWS Lambda Function

My Lambda function has an execution role, which is By default, the role makes sure the function only has the permissions it needs to do its job, minimizing the potential for security vulnerabilities.

My Lambda function will take a userId as input, grab the corresponding data from the UserData table, and return it .The second half of the code handles potential errors during the database operation, so that I get a tailored error message that tells me what went wrong.

The code uses AWS SDK, which is a set of tools that let developers build apps that interact with AWS. My code uses SDK to use pre-written functions for communicating with DynamoDB and getting data from a table

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/465096ce-f136-53fb-8a99-ebab7c406cd9_a1b2c3d5)

## Function Testing

To test whether my Lambda function works, I used the test option. The test is written in JSON If the test is successful, I'd see the attributes of the userid i used for the test.

The test displayed a 'success' because the function itself could run but the function's response was actually "Accessdenied" because the lambda role doesn't have the permissions to access data in the DynamoDB table.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/465096ce-f136-53fb-8a99-ebab7c406cd9_u1v2w3x4)

## Function Permissions

To resolve the AccessDenied error we need to identify the error message to see the appropriate dynamodb role we are going to assign to the lambda role .

There were four DynamoDB permission policies I could choose from, but I didn't pick they don't meet the the requirements based on the error message i got from testing the lambda function. those roles address something else 

I also didn't pick DynamoDBFull access because that gives me complete access to the DynamoDB table which we don't need at the moment.AmazonDynamoDBReadOnlyAccess was the right choice because it addresses exactly what we need, that is only retrieving data from the table.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/465096ce-f136-53fb-8a99-ebab7c406cd9_3ethryj2)

## Final Testing and Reflection

To validate my new permission settings, I rerun the test again. The results were "{
  "email": "test@example.com",
  "name": "Test User",
  "userId": "1"
}" because the lambda function role now has the necessary permissions to retrieve from the dynamodb table.

Web apps are a popular use case of using Lambda and DynamoDB. For example, I could add items to a dynamodb table using lambda

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/465096ce-f136-53fb-8a99-ebab7c406cd9_p9thryj2)

## Enahancing Security

For my project extension, I challenged myself to create an inline policy for the lambda role. This will give the policy a more granular control on what the lambda role can retrieve from the DynamoDB table.

To create the permission policy, I used the JSON method because writing the policies in the JSON format is more convenient

When updating a Lambda funciton's permission policies, you could risk breaking the permissions you once gave to your lambda role. I validated that my Lambda function still works by running the test again

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/465096ce-f136-53fb-8a99-ebab7c406cd9_1qthryj2)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/465096ce-f136-53fb-8a99-ebab7c406cd9)*
