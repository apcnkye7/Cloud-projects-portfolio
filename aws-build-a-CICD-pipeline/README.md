<picture><source media="(prefers-color-scheme: dark)" srcset="https://nextwork.ai/static/nextwork-logo-paper.svg" /><img src="https://nextwork.ai/static/nextwork-logo-leather.svg" alt="NextWork" width="300" /></picture>

# Build a CI/CD Pipeline with AWS

**Project Link:** [View Project](https://nextwork.ai/projects/7ade5e2f-0020-55fb-9bba-abede6ce1de9)

**Author:** Gabby Hammond

---

## Introducing Today's Project!

In this project, I will demonstrate creating a complete CI/CD pipeline with AWS CodePipeline,connecting to my source code, build, and deployment stages,test automatic deployments and learn how to roll back changes

### ✍️ What are you doing in this step and why?

In this step, I will start creating a new pipeline in CodePipeline.

### Key tools and concepts

Services I used were CodeBuild,CodeArtfifact,CodeDeploy,CodePipeline,S3,IAM and EC2 instances.Key concepts I learnt include the continuous integration and continuous development pipeline for development, rollbacks

### Project reflection

This project took me approximately 2 hours. The most challenging part was the rollbacks.It was most rewarding to read the error message and fix it with resources online

I chose to do this project today because I am building a job portfolio.Something that would make learning with NextWork even better is more secret missions.

### ⭐️ Well done on completing the 7 Day DevOps challenge!

Are there any other projects or series you'd like to see at NextWork? What would make learning an even better experience for you? more devops projecs i think

## Starting a CI/CD Pipeline

AWS CodePipeline is a pipeline where you can create a workflow that automatically moves your code changes through the build and deployment stage.

CodePipeline offers different execution modes based on how the CodePipeline handles multiple runs of the same pipeline. I chose "Superseded" other options include Queued and Parallel

A service role gets created automatically during setup so that CodePipeline gives me permission to access other AWS resources it needs to run my pipeline, such as S3 buckets for storing artifacts or CodeBuild for building your code.

### ✍️ What are you doing in this step and why?

In this step, I will Connect CodePipeline to your GitHub repository and branch,connect CodePipeline to my CodeBuild project,connect CodePipeline to my CodeDeploy deployment group and configure webhook events to automatically trigger the pipeline

![Starting a CI/CD Pipeline](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7ade5e2f-0020-55fb-9bba-abede6ce1de9_gdnhtm)

## CI/CD Stages

The three stages I've set up in my CI/CD pipeline are Source stage, build stage and the deploy stage .While setting up each part, I learnt about how each part is connected to each other in the pipeline.

CodePipeline organizes the three stages into Source,Build and Deploy. In each stage, you can see more details on the Stage ID link in the Executions tab.

### ✍️ What are you doing in this step and why?

In this step, I will test the pipeline by making a code change and pushing it to GitHub.

![CI/CD Stages](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7ade5e2f-0020-55fb-9bba-abede6ce1de9_fbdetger)

## Source Stage

In the Source stage, the default branch tells CodePipeline to monitor this branch for changes and trigger the pipeline whenever there's a commit to it.

The source stage is also where you enable webhook events, which  are like digital notifications. When you enable webhook events, CodePipeline sets up a webhook in the GitHub repository. This webhook is configured to listen for specific events, such as code pushes to the master branch.

![Source Stage](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7ade5e2f-0020-55fb-9bba-abede6ce1de9_sergt)

## Build Stage

The Build stage sets up where the source code gets compiled and packaged into something that can be deployed. I configured build provider and build type The input artifact for the build stage is the SourceArtifact

![Build Stage](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7ade5e2f-0020-55fb-9bba-abede6ce1de9_j1k2l3m4)

## Deploy Stage

The Deploy stage is the final step in the pipeline. It's responsible for taking the application artifacts (the output from the Build stage) and deploying them to the target environment, the EC2 instance. I configured the deploy provider, input artifact  and the deployment group

### ✍️ What are you doing in this step and why?

In this step, I will finish creating the pipeline and observe how the pipeline starts up and connect GitHub, CodeBuild and CodeDeploy.

![Deploy Stage](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7ade5e2f-0020-55fb-9bba-abede6ce1de9_m4n5o6p7)

## Success!

Since my CI/CD pipeline gets triggered by changes made to the codebase in my github branch I tested my pipeline by adding some few lines to the index.jsp file and then pushed it to the master branch

The moment I pushed the code change the source stage of the pipeline was updated with the change i made.The commit message under each stage reflects the changes made

Once my pipeline executed successfully, I checked the public IPV4 DNS to see if the changes made actual reflected in the app

![Success!](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7ade5e2f-0020-55fb-9bba-abede6ce1de9_e1f2g3h4)

## Testing the Pipeline

In a project extension, I initiated a rollback on the Deploy stage.Automatic rollback is important for  errors in new deployments

During the rollback, the source and build stage are not affected because they were no code bugs in the build and source stages. the only focus was on the deploy stage.I could verify this by comparing executions in all stages

After rollback, the live web app reverted to the previous version

![Testing the Pipeline](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/7ade5e2f-0020-55fb-9bba-abede6ce1de9_sdfgsdfgdf)
