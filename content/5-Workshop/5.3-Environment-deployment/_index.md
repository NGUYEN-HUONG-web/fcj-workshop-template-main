---
title: "5.3. Environment Deployment"
date: 2026-08-09
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

## Objective

This section prepares the shared deployment environment used by the AI Learning Assistant. The target is a production-lite architecture that is simple enough for an internship project while preserving repeatability, security, monitoring, and recovery.

## Deployment environments

| Environment | Purpose | Main components |
|---|---|---|
| Local | Development and functional testing | Docker Desktop/Engine, Docker Compose, local browser |
| GitHub Actions | Automated build and delivery | Workflow runner, AWS authentication, Docker build |
| Amazon ECR | Container image registry | Versioned application images |
| Amazon EC2 | Runtime environment | Docker Compose stack, Nginx, CloudWatch Agent |
| Amazon S3 | AWS object storage | Backup or long-term data storage |

## AWS resource plan

Prepare a consistent naming convention for the EC2 instance, ECR repository, S3 bucket, IAM roles, CloudWatch resources, Lambda functions, EventBridge schedules, SNS topic, and budget. Use one AWS Region for all regional resources unless the design explicitly requires otherwise.

![AWS Region and main project resources](/images/5-Workshop/5.3-Environment/aws-region-resources.png)

## Network and access plan

1. Place the EC2 instance in a VPC subnet with outbound Internet access.
2. Allow SSH only from a trusted IP, or use Session Manager.
3. Allow HTTP/HTTPS traffic required by the website.
4. Keep database and cache ports private to the Docker network.
5. Assign IAM roles instead of storing permanent AWS keys on EC2.

## Environment variables

Create a local `.env` file from the project example and provide values for database credentials, Redis, MinIO, AI model configuration, application URL, and storage settings. Never commit `.env` to Git.

> **⚠️ Image not available:** Repository structure and sanitized `.env.example`.  
> File: `/images/5-Workshop/5.3-Environment/repository-environment.png`

## Expected result

The local, CI/CD, and AWS environments use compatible configuration; required resources are named consistently; and secrets are separated from source code.
