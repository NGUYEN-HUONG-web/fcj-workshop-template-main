---
title: "Workshop"
date: 2026-08-09
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Deploying an AI Learning Assistant on AWS

## Workshop overview

This workshop demonstrates how to deploy and operate an **AI Learning Assistant**, customized from FastGPT, on **Amazon EC2**. The platform supports AWS learning paths, document-grounded conversations, quizzes, flashcards, and learning-history tracking.

The application runs as a Docker Compose stack containing the AI Learning Assistant, MongoDB, PostgreSQL with pgvector, Redis, MinIO, Code Sandbox, and Nginx Reverse Proxy. AWS services provide image storage, backup, monitoring, alerting, automation, and cost control.

After completing this workshop, you will understand how to:

- Deploy a containerized Generative AI application on Amazon EC2.
- Build and store Docker images with GitHub Actions and Amazon ECR.
- Use MongoDB, PostgreSQL with pgvector, Redis, MinIO, and Amazon S3.
- Monitor EC2 with CloudWatch Agent, dashboards, alarms, and Amazon SNS.
- Schedule EC2 start and stop operations with Lambda and EventBridge.
- Monitor project spending with AWS Budgets.
- Validate AI chat, document processing, quizzes, and learning features.

## Solution architecture

```text
User
  ↓
Public IP / FE_DOMAIN
  ↓
Nginx Reverse Proxy
  ↓
AI Learning Assistant
  ├── MongoDB
  ├── PostgreSQL + pgvector
  ├── Redis
  ├── MinIO
  ├── Amazon S3
  └── Code Sandbox
```

```text
GitHub Actions → Amazon ECR → Amazon EC2 → Docker Compose
CloudWatch Agent → Dashboard → Alarm → Amazon SNS
EventBridge → Lambda → Start/Stop Amazon EC2
AWS Budgets → Cost notification
```

| Component | Responsibility |
|---|---|
| Nginx Reverse Proxy | Routes external requests to the application. |
| MongoDB | Stores users, workflows, configuration, and conversation history. |
| PostgreSQL + pgvector | Stores embeddings and supports semantic retrieval for RAG. |
| Redis | Supports caching, queues, and background tasks. |
| MinIO | Provides S3-compatible storage directly to the application. |
| Amazon S3 | Provides backup or long-term object storage. |
| Code Sandbox | Executes generated code in an isolated environment. |
| Amazon ECR | Stores versioned application images. |
| CloudWatch and SNS | Provide monitoring, alarms, and notifications. |
| Lambda and EventBridge | Automate scheduled EC2 operations. |
| AWS Budgets | Tracks project spending and thresholds. |

## Prerequisites

- An AWS account with access to EC2, ECR, S3, CloudWatch, SNS, Lambda, EventBridge, IAM, and AWS Budgets.
- A GitHub repository with the application, Dockerfile, Docker Compose file, and workflow.
- An EC2 key pair and a least-privilege Security Group.
- Docker and Docker Compose installed on EC2.
- Secure application variables and AI model credentials.
- A confirmed SNS subscription.
- A tested sample document and prepared demo questions.

> Never expose access keys, API keys, `.env` files, database passwords, SSH private keys, connection strings, account IDs, billing data, or sensitive documents.

## Deployment procedure

### 1. Verify Amazon EC2

Open **EC2 → Instances**, select the correct Region, and confirm that the instance is `Running` with `2/2 passed` status checks. Verify that the configured Public IPv4 address or domain is reachable and that the Security Group exposes only required ports.

```bash
docker --version
docker compose version
```

### 2. Start the Docker Compose stack

```bash
docker compose pull
docker compose up -d
docker compose ps
```

All required containers should be `Up` or healthy. Inspect a failed service with:

```bash
docker compose logs --tail=100 <service-name>
```

### 3. Verify Amazon ECR and GitHub Actions

In Amazon ECR, confirm the expected image tag, digest, and latest push time. In GitHub Actions, open the latest successful workflow and verify the implemented stages: source validation, AWS authentication, image build, tagging, and push to ECR. Only describe automatic EC2 deployment when the workflow actually implements it.

### 4. Verify object storage

Confirm the project bucket and expected objects in Amazon S3 without opening sensitive data. In this architecture, MinIO serves application files directly, while Amazon S3 supports backup or long-term storage and reduces dependency on the EC2 root volume.

## Monitoring and automation

### CloudWatch and SNS

CloudWatch Agent sends configured operating-system metrics from EC2. The dashboard displays metrics such as CPU, memory, disk, and network usage. CloudWatch alarms publish state changes to an SNS topic so a confirmed subscriber can receive notifications.

### Lambda and EventBridge

EventBridge invokes Lambda functions on a schedule. Lambda calls the EC2 API to start the server before expected use and stop it during idle periods, reducing unnecessary runtime cost.

### AWS Budgets

AWS Budgets tracks project spending and sends notifications when actual or forecast cost approaches a configured threshold.

## Workshop contents

1. [Introduction](5.1-workshop-overview/)
2. [System architecture](5.2-prerequiste/)
3. [Environment deployment](5.3-environment-deployment/)
4. [Prerequisites and local setup](5.4-local-setup/)
5. [Deploy EC2 and Docker Compose](5.5-ec2-docker/)
6. [CI/CD with GitHub Actions and ECR](5.6-cicd-ecr/)
7. [Storage with MinIO and Amazon S3](5.7-storage/)
8. [Monitoring with CloudWatch and SNS](5.8-monitoring/)
9. [Automation and cost optimization](5.9-automation-cost/)
10. [Cleanup and future development](5.10-testing-demo/)

## Conclusion

This workshop demonstrates a production-lite Generative AI platform on AWS. Docker Compose provides a repeatable application stack; GitHub Actions and ECR support versioned delivery; CloudWatch and SNS provide operational visibility; Lambda, EventBridge, and AWS Budgets support cost control; and the application delivers document-grounded AI assistance with practical learning features.
