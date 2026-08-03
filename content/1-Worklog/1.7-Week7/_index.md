---
title: "Week 7 Worklog"
date: 2026-08-03
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Week 7 Objectives

* Understand the DevOps culture and the CI/CD workflow.
* Manage source code using Git and GitHub.
* Build an automated CI/CD pipeline with GitHub Actions.
* Automate application testing, building, and packaging.
* Push Docker images to Amazon Elastic Container Registry (Amazon ECR).
* Automatically deploy new application versions to AWS.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| **2** | - Learned about DevOps principles and the Software Development Life Cycle (SDLC).<br>- Studied the differences between Continuous Integration (CI), Continuous Delivery, and Continuous Deployment.<br>- Reviewed Git Branches, Commits, Merges, and Pull Requests.<br>- Established source code management practices for the project. | 03/08/2026 | 03/08/2026 | <https://docs.github.com/actions> |
| **3** | - Learned the structure of GitHub Actions workflows.<br>- Created workflow files under the `.github/workflows` directory.<br>- Configured workflow triggers for Push and Pull Request events.<br>- Added jobs to check out the source code and prepare the build environment. | 04/08/2026 | 04/08/2026 | <https://docs.github.com/actions/writing-workflows> |
| **4** | - Configured dependency installation.<br>- Automated unit testing and application builds.<br>- Stored build artifacts for later use.<br>- Reviewed workflow logs and resolved pipeline execution issues. | 05/08/2026 | 05/08/2026 | <https://docs.github.com/actions/automating-builds-and-tests> |
| **5** | - Added Docker image build steps to the pipeline.<br>- Configured AWS authentication using GitHub Secrets or IAM Roles.<br>- Logged in to Amazon ECR.<br>- Tagged Docker images using the Commit SHA and pushed them to Amazon ECR. | 06/08/2026 | 06/08/2026 | <https://github.com/aws-actions/amazon-ecr-login> |
| **6** | - Deployed the latest application version to Amazon ECS, Amazon EKS, or Amazon EC2.<br>- Verified deployment status and reviewed application logs.<br>- Tested source code changes to trigger the CI/CD pipeline.<br>- Completed the project documentation for the CI/CD workflow. | 07/08/2026 | 07/08/2026 | <https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-cd-pipeline.html> |

### Achievements

* Understood the purpose and key stages of the CI/CD process.
* Managed source code using Git branches and Pull Requests.
* Created GitHub Actions workflows using YAML.
* Automated testing and application builds whenever source code changed.
* Stored build artifacts generated during the pipeline.
* Automatically built and pushed Docker images to Amazon ECR.
* Secured sensitive credentials using GitHub Secrets.
* Successfully deployed applications to AWS.
* Learned how to analyze workflow logs and identify pipeline failures.

### Challenges and Solutions

| Challenges | Solutions |
| --- | --- |
| The pipeline was not triggered. | Verified the branch name and the events defined in the `on` section of the workflow. |
| The build process could not locate the JAR file. | Executed the Maven or Gradle build step before building the Docker image and verified the artifact path. |
| GitHub Actions could not authenticate with Amazon ECR. | Verified the AWS Region, IAM permissions, and authentication credentials. |
| A new Docker image was pushed, but the application was not updated. | Created a new Task Definition revision or updated the deployment to use the latest image tag. |
| Sensitive information was exposed in the workflow. | Moved all credentials to GitHub Secrets or adopted OpenID Connect (OIDC) for secure authentication. |

---

### Weekly Reflection

Week 7 helped me understand how DevOps bridges software development and operations by automating the software delivery process. Instead of building and deploying applications manually, GitHub Actions enabled me to automatically validate source code, run tests, package the application, and deploy new versions to AWS.

One of the most important lessons I learned is that an effective CI/CD pipeline should not only execute successfully but also be secure, maintainable, and capable of detecting issues early in the development process. Using GitHub Secrets or OpenID Connect (OIDC) significantly improves security by protecting AWS credentials and reducing the risk of exposing sensitive information.