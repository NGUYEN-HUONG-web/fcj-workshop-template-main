---
title: "Prerequisites"
date: 2026-08-05
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

# Prerequisites

## Objective

In this section, we will prepare the required AWS account, development tools, and working environment before deploying the **AI Learning Assistant Platform** on **Amazon Web Services (AWS)**.

After completing this section, you will have everything required to deploy the platform on Amazon EC2 in the following chapters.

---

## Requirements

Before starting the workshop, ensure that the following accounts and tools are available.

| Component | Description |
|-----------|-------------|
| AWS Account | An AWS account with permission to deploy AWS resources |
| IAM User | An IAM user with permissions to manage Amazon EC2, Amazon ECR, Amazon S3, and Amazon CloudWatch |
| GitHub Account | Stores the AI Learning Assistant Platform source code |
| AWS CLI | Manages AWS resources from the command line |
| Git | Downloads and manages the project source code |
| SSH Client | Connects to Amazon EC2 (Terminal or MobaXterm) |

---

## Prepare Your AWS Account

Sign in to the **AWS Management Console** and select the **US East (N. Virginia) – us-east-1** Region.

Make sure you are using an **IAM User** instead of the AWS Root account to deploy AWS resources.

> **Figure 5.2.1. AWS Management Console**

![Figure 5.2.1](/images/5.2.1.png)

---

## Prepare the GitHub Repository

The source code of the **AI Learning Assistant Platform** is stored in a GitHub repository.

This repository will be used to deploy the application and configure the CI/CD pipeline with GitHub Actions.

> **Figure 5.2.2. GitHub Repository**

![Figure 5.2.2](/images/5.2.2.png)

---

## Verify AWS CLI

Verify that AWS CLI has been installed successfully.

```bash
aws --version
```

Then verify your AWS account:

```bash
aws sts get-caller-identity
```

If the commands return your **AWS Account ID** and **ARN**, AWS CLI has been configured successfully.

> **Figure 5.2.3. AWS CLI Verification**

![Figure 5.2.3](/images/5.2.3.png)

---

## Verify Git

Check the installed Git version:

```bash
git --version
```

Git will be used to clone the project source code from GitHub to the Amazon EC2 instance.

> **Figure 5.2.4. Git Verification**

![Figure 5.2.4](/images/5.2.4.png)

---

## AWS Services Used

The following AWS services will be used throughout this workshop.

| AWS Service | Purpose |
|-------------|---------|
| Amazon EC2 | Host the AI Learning Assistant Platform |
| Amazon EBS | Provide persistent storage |
| Amazon ECR | Store Docker images |
| Amazon S3 | Store backup data |
| Amazon CloudWatch | Monitor system performance |
| AWS IAM | Manage access permissions |
| Security Group | Control network access |
| AWS Budgets | Monitor and control AWS costs |

---

## Expected Outcome

After completing this section, you will have:

- An AWS account ready for deployment.
- An IAM user with sufficient permissions to manage AWS resources.
- A GitHub repository containing the project source code.
- A properly configured AWS CLI and Git environment.
- Everything required to deploy Amazon EC2 in the next section.