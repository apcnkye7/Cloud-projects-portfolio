<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Website Delivery with CloudFront

**Project Link:** [View Project](https://nextwork.ai/projects/c1513937-a6bf-53e9-9512-a7d466c0e79c)

**Author:** Gabby Hammond  
**Email:** hammondgabby7436@gmail.com

---

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/c1513937-a6bf-53e9-9512-a7d466c0e79c_1dddddwe)

## Introducing Today's Project!

In this project, I will demonstrate website delivery with AWS CloudFront I'm doing this project to learn about how to optimize website performance and ensure scalable, efficient content delivery.

### Tools and concepts

Services I used were CloudFront,S3 Key concepts I learnt include content delivery network (CDN), and OAC and OAC policy

### Project reflection

This project took me approximately an hour and 30 mins.The most challenging part was getting the site to be hosted through the cloudfront domain url It was most rewarding to go through the error messages and debugging steps online

I chose to do this project today because i am building a portfolio Something that would make learning with NextWork even better is more clarity with some steps especially the static url hosting to compare the load times.

## Set Up S3 and Website Files

I started the project by creating an S3 bucket to store the website files. I can't use CloudFront for this task because it is not a storage solution in AWS, it's only used for content delivery by hosting content that is stored somewhere else, for instance an s3 bucket

The three files that make up my website are index.html, which is the main file for a website,style.css, which is where you write down the visual appearance of your website's HTML elements and script.js, which a JavaScript file that adds interaction to your website

I validated that my website files work by downloading them and opening to verify the content.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/c1513937-a6bf-53e9-9512-a7d466c0e79c_qgo7wcd3)

## Exploring Amazon CloudFront

Amazon CloudFront is a content delivery network, which means  it speeds up the distribution of your static and dynamic web content, such as .html, .css, .js, and image files. Businesses and developers use CloudFront because it delivers contents with a low latency thus guarenteeing best performance

To use Amazon CloudFront, you set up distributions, which are a set of instructions that tells CloudFront how to deliver your content.I set up a distribution for a single website.The origin is an s3 bucket

The default root object for my CloudFront distribution is index.html. This means that when a user visits the CloudFront URL, CloudFront serves the index.html file from the S3 bucket as the website's main page.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/c1513937-a6bf-53e9-9512-a7d466c0e79c_qgo7wcdt)

## Handling Access Issues

When I tried visiting my distributed website, I ran into an access denied error because i havent't given permissions to CloudFront to access the files in the s3 bucket because s3 buckets are private by default.

My distribution's origin access settings were public This caused the access denied error because it means anybody can access the contents in the s3 bucket however s3 is private by default so the access is denied

To resolve the error, I set up origin access control (OAC). OAC is 
 a special user for CloudFront that lets you keep your S3 bucket and objects not publicly accessible, while still making sure they can be accessed through CloudFront.

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/c1513937-a6bf-53e9-9512-a7d466c0e79c_egrhntyu)

## Updating S3 Permissions

Once I set up my OAC, I still needed to update my bucket policy because i need to grant my OAC permission to the bucket's contents.

Creating an OAC automatically gives me a policy I could copy, which grants the OAC permissions to access the contents in the bucket

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/c1513937-a6bf-53e9-9512-a7d466c0e79c_eg98ntyu)

## S3 vs CloudFront for Hosting

## S3 vs CloudFront Load Times

Load time means how quickly content on your website loads.The load times for the CloudFront site were faster than the S3 site because CloudFront uses the cache delivery system to deliver content faster

A business would prefer CloudFront when serving content with low latency is  high priority. S3 static website hosting might be sufficient when low latency isn't a priority

![Image](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/c1513937-a6bf-53e9-9512-a7d466c0e79c_12verpuh)

---

*Built with [NextWork](https://nextwork.ai) - [View this project](https://nextwork.ai/projects/c1513937-a6bf-53e9-9512-a7d466c0e79c)*
