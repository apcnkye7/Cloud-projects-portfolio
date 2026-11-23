<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Encrypt Data with AWS KMS

**Project Link:** [View Project](https://nextwork.ai/projects/716e7f81-84d1-51d6-8945-d4860caebf77)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

In this project, I will demonstrate encrypting data with AWS.The goal is to create encryption keys with AWS KMS (Key Management Service),encrypt a DynamoDB database with a KMS key, add and retrieve data from your database to test your encryption,observe how AWS stops unauthorized access to your data and give a user encryption access.

### ✍️ What are we doing in this step?

In this step, I will create a key for encryption and set up the admins and users of that key because i need to encrypt the data in the DynamoDB

### Tools and concepts

Services I used include AWS KMS, DynamoDB tables, IAM users.Key concepts I learnt include encryption, decryption and access control tools

### Project reflection

This project took me approximately 60 minutes.The most challenging part was going through the key policies It was most rewarding to take my time to read through the policies in order to have an idea of how they worked

I chose to do this project today because i am building my AWS portfolio.Something that would make learning with NextWork even better is more secret projects

## Encryption and KMS

Encryption is the process of using  algorithms to convert data into a secure format called ciphertext .Companies and developers do this to protect data. Encryption keys are texts that tells the algorithm exactly how it would transform plain text into the jumbled up format called cipher text.

AWS KMS is a secure vault for your encryption keys. Key management systems are important because you can use them to create, manage, and use encryption keys that protect the data in your AWS resources.

Encryption keys are broadly categorized as symmetric and assymetric keys. I set up a symmetric key because it's easy to set up and you only need a single key to encrypt and decrypt

![Encryption and KMS](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-kms_a2b3c4d5)

### ✍️ What are we doing in this step?

In this step, I will create a DynamoDB table and set up my table's encryption with KMS because i want to implement data encryption in my dynamodb table

## Encrypting Data

My encryption key will safeguard data in DynamoDB, which is data at rest

The different encryption options in DynamoDB include "AWS owned key", "AWS managed key" and "Customer managed key". Their differences are based on who manages the key and where it's stored. I selected "Customer managed key"

### ✍️ What are we doing in this step?

In this step, I will add data to my DynamoDB table because i want to verify if i can see the encrypted data in the table.

![Encrypting Data](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-kms_q8r9s0t1)

## Data Visibility

Rather than controlling who has access to the key, KMS manages user permissions by the key's IAM policies.

Despite encrypting my DynamoDB table, I could still see the table's items because transparent data encryption in DynamoDB allows authorised users like my IAM to automatically see encrypted data. DynamoDB uses transparent data encryption, which means dynamodb retrieves the encryption key and decrypts on the behalf of the authorised user

### ✍️ What are we doing in this step?

In this step, I will create a test user using IAM and grant the user full access to DynamoDB but not to the KMS key because I want to test an IAM user without permissions to the KMS key.

![Data Visibility](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-kms_c0d1e2f3)

## Denying Access

I configured a new IAM user to have full access to the DynamoDB table.The permission policies I granted this user are for the DynamoDB table access but not the AWS KMS keys

### ✍️ What are we doing in this step?

In this step, I will Log into AWS as the test user because I want to try to view items in the encrypted DynamoDB table as the test user

After accessing the DynamoDB table as the test user, I encountered an access denied error because the data in the DynamoDB table is encrypted and the test IAM user i logged in with doesn't have access to the encrypted data in the dynamodb table. This confirmed the data in the DynamoDB table is safely encrypted and can't be accessed without authorisation

![Denying Access](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-kms_w0x1y2z3)

## EXTRA: Granting Access

To let my test user use the encryption key, I added the test user to the key users for the KMS key i created by scrolling to the key policy tab for my KMS key and adding the user to the key users. My key's policy was updated to allow the test user make use of the KMS key

Using the test user, I retried viewing the contents of the dynamodb table using my test user. I observed the items in the dynamodb talbe which confirmed that the test user has now access to the kms key

Encryption secures data instead of controlling access to the data.I could combine encryption with access control tools to  add an extra layer of security through access permissions and decryption keys.

![EXTRA: Granting Access](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-security-kms_feffb2fb8)
