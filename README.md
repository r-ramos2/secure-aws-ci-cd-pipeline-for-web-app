<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a CI/CD Pipeline with AWS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-codepipeline-updated)

---

![Image](http://learn.nextwork.org/serene_teal_majestic_duck/uploads/aws-devops-codepipeline-updated_fbdetger)

---

## Introducing Today's Project!

In this project, I will demonstrate building a CI/CD pipeline using AWS CodePipeline. I'm doing this project to learn how to automate the build and deployment of a web app, integrating services like CodeBuild and CodeDeploy for efficient delivery.

### Key tools and concepts

Services I used were AWS CodePipeline, CodeDeploy, CodeBuild, EC2, S3, CloudFormation, IAM, and CodeArtifact. Key concepts I learnt include CI/CD automation, infrastructure as code, and automated rollback and deployment.

### Project reflection

This project took me approximately 3 hours. The most challenging part was integrating multiple AWS services, while the most rewarding was seeing seamless, automated deployments in real time.

---

## Starting a CI/CD Pipeline

AWS CodePipeline is a fully managed service that automates the workflow for building, testing, and deploying applications. It integrates with AWS services to ensure consistent, reliable, and automated deployments, minimizing manual intervention.

CodePipeline offers different execution modes based on concurrency. I chose Superseded mode, where new executions replace the old. Other options include Queued mode, where executions wait, and Parallel mode, which allows concurrent executions.

A service role gets created automatically during setup so CodePipeline can perform actions on your behalf, like accessing resources such as S3 buckets and CodeBuild, ensuring the pipeline runs smoothly without manual intervention.

![Image](http://learn.nextwork.org/serene_teal_majestic_duck/uploads/aws-devops-codepipeline-updated_gdnhtm)

---

## CI/CD Stages

​The three stages I've set up in my CI/CD pipeline are Source, Build, and Deploy. While setting up each part, I learned about automating code integration, building processes, and deployment strategies for efficient and reliable software delivery.

CodePipeline organizes the three stages into Source, Build, and Deploy. In each stage, you can see more details on actions performed, their providers, execution times, and success or failure statuses. 

![Image](http://learn.nextwork.org/serene_teal_majestic_duck/uploads/aws-devops-codepipeline-updated_fbdetger)

---

## Source Stage

​In the Source stage, the default branch tells CodePipeline to monitor that branch for changes, ensuring the pipeline triggers on new commits. The default branch serves as the primary base of development, where all changes eventually merge back.

The source stage is also where you enable webhook events, which allow CodePipeline to automatically start your pipeline whenever code is pushed to your specified branch in GitHub.

![Image](http://learn.nextwork.org/serene_teal_majestic_duck/uploads/aws-devops-codepipeline-updated_sergt)

---

## Build Stage

The Build stage sets up CodeBuild to compile and package our web app. I configured the Source stage to output our code as SourceArtifact. The input artifact for the build stage is SourceArtifact, ensuring CodeBuild always processes the latest code.

![Image](http://learn.nextwork.org/serene_teal_majestic_duck/uploads/aws-devops-codepipeline-updated_j1k2l3m4)

---

## Deploy Stage

​The Deploy stage deploys the built application to the target environment. I configured AWS CodeDeploy as the deployment provider, selected the existing CodeDeploy application and deployment group, and enabled automatic rollback to ensure stability.

![Image](http://learn.nextwork.org/serene_teal_majestic_duck/uploads/aws-devops-codepipeline-updated_m4n5o6p7)

---

## Success!

Since my CI/CD pipeline gets triggered by code changes, I tested my pipeline by adding a new line in index.jsp's <body> section, committing, and pushing to master. This confirmed automated deployment.

​The moment I pushed the code change to GitHub, CodePipeline automatically detected the update, initiating the Source stage. The commit message under each stage reflects the changes made, confirming the pipeline's responsiveness to code updates.​

​Once my pipeline executed successfully, I checked the deployment by accessing the web application through its public URL. The new line added to index.jsp was visible, confirming that CodePipeline had automatically deployed my latest changes. ​

![Image](http://learn.nextwork.org/serene_teal_majestic_duck/uploads/aws-devops-codepipeline-updated_e1f2g3h4)

---

## Testing the Pipeline

---

---
