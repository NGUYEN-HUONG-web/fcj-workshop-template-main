---
title: "Deploy EC2 and Docker Compose"
date: 2026-08-09
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

# 5.5 Deploy EC2 and Docker Compose

## Create the EC2 instance

Launch an EC2 instance with a supported Linux AMI, appropriate instance type, sufficient EBS storage, an IAM role, a key pair when SSH is used, and a least-privilege Security Group. Record the selected Region and instance ID.

## Install the runtime

Connect through SSH or Session Manager, update the operating system, and install Docker Engine, the Compose plugin, Git, and CloudWatch Agent. Add the deployment user to the Docker group only when required.

## Deploy the stack

Clone the deployment configuration, create the protected `.env`, authenticate to ECR when using private images, and run:

```bash
docker compose pull
docker compose up -d
docker compose ps
```

## Configure Nginx

Nginx Reverse Proxy receives requests from the Public IP or `FE_DOMAIN` and forwards them to the application. Configure HTTPS when a domain and certificate are available. Do not expose MongoDB, PostgreSQL, Redis, or MinIO management ports publicly.

## Verification

- EC2 state is `Running`.
- Status checks show `2/2 passed`.
- Required containers are `Up` or healthy.
- Website loads from the configured public address.
- Application logs contain no recurring critical errors.
- Data volumes are mounted correctly.

## Evidence images to add

1. EC2 in `Running` state with `2/2 passed` status checks.
2. EC2 details with sensitive identifiers concealed.
3. Security Group inbound rules.
4. Terminal showing Docker installation and running containers.
5. Website accessed through Public IP or the configured domain.

<!-- Suggested directory: /static/images/5-Workshop/5.5-EC2-Docker/ -->
