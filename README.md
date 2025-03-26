# 7 Day DevOps Challenge: NextWork Web Project

## Overview
This project builds a CI/CD pipeline for a Java-based web application running on an AWS EC2 instance. The pipeline automates the build, testing, and deployment processes, integrating GitHub and AWS CI/CD tools. It demonstrates version control with Git, automating code deployment, and improving software release cycles.

## Features
- **Version Control:** Manage code changes with Git.
- **Remote Repository:** Sync code with GitHub.
- **Secure Auth:** Use Personal Access Tokens for GitHub authentication.
- **Remote Editing:** Edit code on EC2 via VSCode.
- **CI/CD Pipeline:** Automate build and deployment steps using AWS tools.
- **Java Web App:** The project uses Java, Maven, and other AWS services for development and deployment.

## Technologies
Here’s what I’m using for this project:

- **Amazon EC2:** The web app is developed and deployed on EC2 virtual servers, providing cloud-based development and hosting.
- **VSCode:** I use Visual Studio Code with the Remote-SSH extension for editing files directly on the EC2 instance.
- **GitHub:** All project code is stored and versioned on GitHub.
- **Maven:** The build automation tool used for managing dependencies and building the Java application.
- **AWS CI/CD Tools:** The project leverages AWS services to automate the software delivery pipeline:
- **AWS CodeArtifact**: Manages project dependencies and artifacts.
- **AWS CodeBuild**: Handles the build process, compiling source code and running tests.
- **AWS CodeDeploy**: Automates deployment across EC2 instances.
- **AWS CodePipeline**: Integrates and automates the entire workflow from GitHub to CodeDeploy.

## Setup & Installation

1. **Prerequisites:**
   - AWS EC2 instance with Git and Maven installed.
   - VSCode with the Remote-SSH extension for editing files.
   - A GitHub account.

2. **Clone the Repository:**

   ```bash
   git clone https://github.com/yourusername/nextwork-web-project.git
   cd nextwork-web-project
   ```

3. **Install Dependencies:**
   - Install Maven dependencies:

     ```bash
     mvn install
     ```

4. **Configure Git:**

   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "your.email@example.com"
   ```

5. **Connect to GitHub:**
   - Generate a Personal Access Token on GitHub.
   - Add the remote repository:

     ```bash
     git remote add origin https://github.com/yourusername/nextwork-web-project.git
     ```

## Usage

1. **Edit Files:**
   - Open the project in VSCode.
   - Modify files (e.g., update `index.jsp` with personalized content).

2. **Stage, Commit, and Push Changes:**

   ```bash
   git add .
   git commit -m "Describe your changes here"
   git push -u origin main
   ```

3. **Review History:**
   - To view pending changes, run:

     ```bash
     git diff --staged
     ```

   - To view commit history, run:

     ```bash
     git log
     ```

## CI/CD Pipeline
This project is part of a 7-day challenge that gradually builds a complete CI/CD pipeline. Future updates will add testing and automated deployment using AWS services like CodeBuild, CodeDeploy, and CodePipeline.

## Troubleshooting
- **Authentication:** Use a Personal Access Token instead of your password.
- **No Updates on GitHub:** Ensure that you have committed and pushed your changes.
- **Terminal Issues:** Press `q` to exit pager views if the terminal seems stuck.

## Contributing
Contributions are welcome! Fork the repository and submit pull requests with improvements or bug fixes.

## Acknowledgements
Special thanks to **[NextWork](https://learn.nextwork.org/app)** for their project guide and support. You can get started with this DevOps series project too by [clicking here](https://learn.nextwork.org/projects/aws-devops-vscode?track=high).
