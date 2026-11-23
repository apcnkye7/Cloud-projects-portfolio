<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Host a Website on Amazon S3

**Project Link:** [View Project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to use amazon services to host a static website using s3 buckets. I'm doing this project to learn amazon cloud services

### Tools and concepts

Services I used were s3 buckets Key concepts I learnt include uploading website files to a website, configuring the files for the website to be made public, configuring a bucket policy to prevent unauthorised deletion of the inde.html files

### Time, challenges, and wins

This project took me approximately 40 minsThe most challenging part was making the acl public. It was most rewarding to patiently follow the video guideline

### ❤️ Thanks for doing this project!

I chose to do this project today because i need to update my cloud knowledge and keep myself conversant with cloud services.Something that would make learning with NextWork even better is keep up the good work

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will create an s3 bucket because website files need storage

### How long it took to create the bucket

Creating an S3 bucket took me less than 10 minutes

### Region selection

The Region I picked for my S3 bucket was seoul because it is close to me

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means any name you choose can't be used by another person

![How I Set Up an S3 Bucket](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-host-a-website-on-s3_ba6d42ad)

## Upload Website Files to S3

### What I did in this step

In this step, I will upload website content to the bucket because the website requires those files

### Files I uploaded

I uploaded two files to my S3 bucket - they were the index.html file and the "everyone should be in a job they love" folder

### How the files work together

Both files are necessary for this project as they contain files for the website hosting

![Upload Website Files to S3](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-host-a-website-on-s3_a265af88)

## Static Website Hosting on S3

### What I did in this step

In this step, I will configure the s3 bucket for the static website hosting because the website needs to be made available

### Understanding website hosting

Website hosting means making the website public on the internet

### How I enabled website hosting

To enable website hosting with my S3 bucket, I have to enable static website hosting

### Access Control Lists (ACLs)

An ACL is a set of rules on who can get access to your buckets

![Static Website Hosting on S3](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-host-a-website-on-s3_c22c54c0)

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website is enabled, S3 produces a bucket endpoint URL, which is a url that allows people visit the website files in the bucket as a website

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw a 403 errorThe reason for this error was the files in the bucket are private

![Bucket Endpoints](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-host-a-website-on-s3_22ce4daf)

## Success!

### What I did in this step

In this step, I will make the website files public because the files are automatically made private in the s3 buckets

### How I resolved the 403 error

To resolve this 403 Forbidden error, I made the objects in the s3 buckets public by making the selecting the making public using acl option

### ✅ What were the key services and concepts you learnt in this project?

Services I used were s3 buckets.Key concepts I learnt include configuring buckets using acls and bucket policies.

### ✅ How long did it take you to complete this project?

This project took me approximately 45 mins.The most challenging part was deleting the buckets It was most rewarding to read and follow error messages on the console

### ❤️ Thanks for doing this project!

I chose to do this project today because i want to revise my cloud knowledge.Something that would make learning with NextWork even better is adding more projects!!

![Success!](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-host-a-website-on-s3_5d4474f9)

## Bucket Policies

### What I did in this extension

In this project extension I'm about to set up a bucket policy I'm doing this so that people can't delete the html files in the bucket since the website has been publicly enabled using the acl

### Understanding bucket policies

An alternative to ACLs are bucket policies, which are statements that controls how people interact with your s3 buckets.The benefit of using bucket policies is to avoid unauthorised actions in your s3 buckets while ACLs are useful for who can see your s3 buckets

![Bucket Policies](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/aws-host-a-website-on-s3_sm2sm2sm)

### What my bucket policy does

My bucket policy prevents the index.html file from being deleted by everyone I tested this by trying to delete the html myself  and saw an error message
