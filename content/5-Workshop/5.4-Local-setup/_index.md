---
title: "Prerequisites and Local Setup"
date: 2026-08-09
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

# 5.4 Prerequisites and Local Setup

## Prerequisites

- Git and a GitHub account.
- Docker Engine or Docker Desktop with Docker Compose.
- At least 8 GB RAM and sufficient free disk space for images and volumes.
- A supported browser.
- Application environment variables and valid AI model credentials.
- Optional AWS CLI for testing AWS access locally.

## Clone and configure the project

```bash
git clone <repository-url>
cd <repository-directory>
cp .env.example .env
```

Open `.env` and configure values according to the project documentation. Use strong, unique passwords and do not expose the file.

## Start the local stack

```bash
docker compose pull
docker compose up -d
docker compose ps
```

Wait until the required application, MongoDB, PostgreSQL/pgvector, Redis, MinIO, Code Sandbox, and Nginx containers are running.

## Validate locally

1. Open the configured frontend URL.
2. Sign in or create a test account.
3. Open a learning path and lesson.
4. Ask the AI assistant a prepared question.
5. Upload a non-sensitive sample document.
6. Confirm that data remains available after container restart.

## Troubleshooting

```bash
docker compose logs --tail=100 <service-name>
docker compose restart <service-name>
docker system df
```

Check port conflicts, invalid variables, insufficient memory, unhealthy dependencies, and model API connectivity before moving to AWS.

## Evidence images to add

1. Docker and Docker Compose version commands.
2. `docker compose ps` showing local services running.
3. Local application login or home page.
4. Successful local AI response and sample document upload.

<!-- Suggested files: docker-version.png, local-containers.png, local-home.png, local-ai-response.png -->
