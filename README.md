## 7-Day DevOps Challenge: NextWork Web Project

### Overview

This repository demonstrates a complete CI/CD pipeline for a Java-based web application running on AWS EC2. It integrates GitHub with AWS CI/CD services to automate build, test, and deployment workflows, showcasing best practices in version control, continuous integration, and continuous deployment.

### Features

* **Version Control:** Git tracking for all code changes
* **Remote Repository:** Sync with GitHub
* **Secure Authentication:** GitHub Personal Access Tokens
* **Remote Development:** VSCode Remote‑SSH on EC2
* **CI/CD Pipeline:** AWS CodePipeline, CodeBuild, CodeDeploy, CodeArtifact
* **Java Web App:** Maven‑based build and packaging

### Technologies

* **Amazon EC2:** Cloud servers for hosting and development
* **VSCode + Remote‑SSH:** Edit files directly on EC2
* **GitHub:** Source code management and collaboration
* **Maven:** Dependency management and build automation
* **AWS CodeArtifact:** Artifact repository
* **AWS CodeBuild:** Build and test automation
* **AWS CodeDeploy:** Deployment orchestration
* **AWS CodePipeline:** End‑to‑end workflow automation

### Table of Contents

1. [Prerequisites](#prerequisites)
2. [Installation](#installation)
3. [Configuration](#configuration)
4. [Usage](#usage)
5. [CI/CD Pipeline](#cicd-pipeline)
6. [Troubleshooting](#troubleshooting)
7. [Contributing](#contributing)

---

### Prerequisites

* An AWS account with permissions to create EC2, IAM, CodeArtifact, CodeBuild, CodeDeploy, and CodePipeline resources
* AWS CLI configured with appropriate credentials
* Java SDK and Maven installed on your local machine or EC2
* VSCode with Remote‑SSH extension
* Git and GitHub account

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/<your-username>/nextwork-web-project.git
   cd nextwork-web-project
   ```
2. Install dependencies:

   ```bash
   mvn install
   ```

### Configuration

1. Configure Git locally:

   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```
2. Connect to GitHub with a Personal Access Token:

   ```bash
   git remote add origin https://<TOKEN>@github.com/<your-username>/nextwork-web-project.git
   ```
3. SSH into your EC2 instance and install required packages:

   ```bash
   sudo yum update -y
   sudo yum install git java-11-openjdk-devel maven -y
   ```

### Usage

1. Open the project in VSCode via Remote‑SSH.
2. Make code changes (e.g., update `src/main/webapp/index.jsp`).
3. Stage, commit, and push:

   ```bash
   git add .
   git commit -m "Describe your changes"
   git push origin main
   ```
4. Monitor the pipeline in the AWS Console under CodePipeline.

### CI/CD Pipeline

This pipeline runs on every push to the `main` branch:

1. **Source:** GitHub repository triggers via webhook
2. **Build:** CodeBuild compiles and tests the application
3. **Deploy:** CodeDeploy pushes artifacts to the EC2 instance

Future enhancements will include automated testing and multi‑region deployments.

### Troubleshooting

* **Authentication Errors:** Verify your GitHub token scopes
* **Build Failures:** Check the `buildspec.yml` and ensure Maven can resolve dependencies
* **Deployment Hangs:** Confirm IAM roles and instance tags match your CodeDeploy configuration

### Contributing

Contributions are welcome! Fork this repo, create a feature branch, and submit a pull request.
