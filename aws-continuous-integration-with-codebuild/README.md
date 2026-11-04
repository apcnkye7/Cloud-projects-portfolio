## Introducing Today's Project!

In this project, I will demonstrate creating and configuring a CodeBuild project from scratch,connecting the CodeBuild project to my GitHub repository and define the build process using a buildspec.yml file and automate testing using CodeBuild

### ✍️ What are you doing in this step and why?

In this step, I will Launch an EC2 instance using the AWS Management Console to nderstand the benefits of using EC2 for this project.Then i will troubleshoot common issues during the instance launch.

### ✍️ What are you doing in this step and why?

In this step, I will set up a CodeArtifact repository to store the web app's packages,create an IAM policy and role for CodeArtifact access,configure Maven settings to use CodeArtifact,build the web app with Maven and verify the connection with CodeArtifact.

### ✍️ What are you doing in this step and why?

In this step, I will create a new CodeBuild project as the next step for the project

### Key tools and concepts

Services I used were CodeBuild,CodeArtifact,CodeConnect,CloudShell ,EC2,S3 and IAM . Key concepts I learnt include building a CodeBuidl project, configuring it for it to build successfully, assigning IAM policies to IAM roles and configuring git

### Project reflection

This project took me approximately 120 minutes The most challenging part was the secret mission. It was most rewarding to carefully go through each line of code in the yml file as my CodeBuild was failing for most of the time.

### ✅ Why did you do this project today?

I did this project because i am working on my portfolio

This project is part four of a series of DevOps projects where I'm building a CI/CD pipeline! I'll be working on the next project in 24 hours

## Setting up a CodeBuild Project

CodeBuild is a continuous integration service, which means it acts like  a quality control checkpoint that automatically kicks in whenever anyone on your team makes changes to your code.Engineering teams use it because they don't have to manually set up and manage any build servers themselves, and they only pay for the compute time they use for building the projects instead of entire servers that are idle most of the time,

My CodeBuild project's source configuration means the location of the code that CodeBuild will fetch, compile, and package into a file you can deploy.and I selected Github

### ✍️ What are you doing in this step and why?

In this step, I will set up a connection between the AWS account and GitHub using AWS CodeConnections because i selected Github as a source for my CodeBuild

![Setting up a CodeBuild Project](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/92664c9b-5395-50c5-82bc-e72e574a6140_fewgrhte)

## Connecting CodeBuild with GitHub

There are multiple credential types for GitHub, like Personal access token and OAuth app  I used GitHub App because it's the simplest and most secure option

The service that helped connect with Github is AWS CodeConnections.

### ✍️ What are you doing in this step and why?

In this step, I will configure CodeBuild's environment settings,configure Amazon S3 to store build artifacts,enable CloudWatch logs for monitoring build processes.

![Connecting CodeBuild with GitHub](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/92664c9b-5395-50c5-82bc-e72e574a6140_a7c98e2d)

## CodeBuild Configurations

### Environment

My CodeBuild project's Environment configuration means defining the compute resources, operating system, runtime, and container/instance images that CodeBuild will use to run your build and test commands.  it includes settings like provisioning model,environment image, compute,etc

### Artifacts

Build artifacts are the tangible outputs of the build process. They're what you'll actually deploy to your servers or distribute to users. That's why storing them properly in S3 is so important - they're the whole reason we're running the build in the first place. My build process will  create one build artifact that packages up everything a server could need to host our web app in one neat bundle.To store them, I created an s3 bucket

### Packaging

When setting up CodeBuild, I also chose to package artifacts in a zip because zip compression can significantly reduce the size of the artifacts, which means faster uploads to S3, less storage costs, and quicker downloads when you need to use them

### Monitoring

For monitoring, I enabled CloudWatch Logs, which  is a monitoring service that collects and tracks logs from AWS services. In this project, CloudWatch will record everything that happens during the build process, including the commands that are run, the output of those commands, and any errors that occur. This is incredibly useful for debugging and understanding what went wrong if a build fails.

### ✍️ What are you doing in this step and why?

In this step, I will start my first build in CodeBuild and troubleshoot a build failure by adding a buildspec.yml file to the web app repository.

## buildspec.yml

My first build failed because the buildspec.yml file we added to the build configuration doesn't exist.A buildspec.yml file is needed because without this file, CodeBuild doesn't know how to build your project

The first two phases in my buildspec.yml file are the install and prebuild phases.The third phase in my buildspec.yml file is the build and post\_build.The fourth phase in my buildspec.yml file is artifacts phase

### ✍️ What are you doing in this step and why?

In this step, I will re-run the build process in CodeBuild,troubleshoot a second build failure, this time by giving CodeBuild the permission to access CodeArtifact,run and verify a successful build!

![buildspec.yml](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/92664c9b-5395-50c5-82bc-e72e574a6140_35588a47)

## Success!

My second build also failed, but with a different error that said "OMMAND\_EXECUTION\_ERROR: Error while executing command: CODEARTIFACT\_AUTH\_TOKEN=\`aws codeartifact get-authorization-token --domain kotei --domain-owner 145250404307 --region us-east-1 --query authorizationToken --output text\`. Reason: exit status 254". To fix this i need to grant CodeBuild's IAM role the permission to access CodeArtifact.

To resolve the second error, I granted CodeBuild's IAM role the permission to access CodeArtifact  When I built my project again, I saw a success message

To verify the build, I checked the s3 bucket to verify if an artifact was created. Seeing the artifact tells me the build was successful

![Success!](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/92664c9b-5395-50c5-82bc-e72e574a6140_d9cc6191)

## Automating Testing

In a project extension, I'm creating a simple unit test for your Java web application,triggering a build to see the tests run automatically I added a test script that  performs a simple validation tests on your project structure - is there a src folder and an index.jsp file in the project directory

To add the test script to the build process, I added this line of code to the build.yml file "build:\
    commands:\
      \- echo "====== BEGINNING TEST PHASE ======"\
      \- echo "Running tests on $(date)"\
      \- chmod +x run-tests.sh\
      \- ./run-tests.sh\
      \- echo "====== TEST PHASE COMPLETE ======"\
      \- echo "====== BEGINNING BUILD PHASE ======"\
      \- echo "Build started on $(date)"\
      \- mvn -s settings.xml compile\
      \- echo "====== BUILD PHASE COMPLETE ======"\
" and did the rebuild again

After pushing my code to GitHub, I ran the build again I could see success on the codebuild page.

![Automating Testing](https://nextwork.ai/stimulated_silver_silly_moray_eel/uploads/92664c9b-5395-50c5-82bc-e72e574a6140_sm-test-script-upload)
