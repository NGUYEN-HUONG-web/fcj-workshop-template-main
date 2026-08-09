---
title: "System Architecture"
date: 2026-08-09
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

# 5.2 System Architecture

## 5.2.1 Architecture overview

The AI Learning Assistant uses a **Client–Server** and layered architecture combined with **Retrieval-Augmented Generation (RAG)**. The application is containerized with Docker and deployed to Amazon EC2 through Docker Compose.

| Layer | Components | Responsibility |
|---|---|---|
| Client | Next.js, React, browser | Learning paths, lessons, AI Chat, documents, quizzes, flashcards, history |
| Application | Nginx, Frontend, Backend | Request routing, business logic, and APIs |
| AI & Data | RAG, MongoDB, PostgreSQL/pgvector, Redis, MinIO | Document processing, semantic retrieval, conversations, and storage |
| Infrastructure | VPC, EC2, EBS, S3, IAM, Security Group, Elastic IP | Runtime, persistence, networking, and access control |
| DevOps & Monitoring | GitHub Actions, ECR, CloudWatch, SNS, Lambda, EventBridge, Budgets | Delivery, observability, automation, and cost control |

```text
User → Public IP / FE_DOMAIN → Nginx Reverse Proxy
                                     ↓
                            AI Learning Assistant
                            ├── MongoDB
                            ├── PostgreSQL + pgvector
                            ├── Redis
                            ├── MinIO
                            └── Code Sandbox
```

> **Figure 5.2.1 – Overall AI Learning Assistant architecture**

![Overall system architecture](/images/3.1.d.x.png)

## 5.2.2 AWS deployment architecture

The Production Lite environment is deployed in **US East (N. Virginia) – `us-east-1`**. EC2 resides in a VPC Public Subnet and uses an Elastic IP. The Security Group exposes only trusted SSH access and required HTTP/HTTPS traffic. Databases communicate through the internal Docker network and are not publicly exposed.

Amazon EBS stores Docker volumes, while Amazon S3 stores backups and long-term objects.

```text
Developer → GitHub → GitHub Actions → Amazon ECR
                                         ↓
                                EC2 / Docker Compose
```

> **Figure 5.2.2 – AWS deployment architecture**

![AWS deployment architecture](/images/3.2.d.s.png)

### AWS services

| Service | Role |
|---|---|
| VPC, Public Subnet, Internet Gateway | Isolated network and Internet connectivity |
| Elastic IP | Stable public endpoint |
| EC2 | Docker Compose runtime |
| EBS | Persistent volumes and application data |
| S3 | Database and document backups |
| ECR | Versioned Docker images |
| IAM and Security Group | Least-privilege access and network control |
| CloudWatch, Alarm, SNS | Metrics, logs, alarms, and notifications |
| Lambda and EventBridge | Scheduled EC2 start and stop |
| AWS Budgets | Cost monitoring and notifications |

## 5.2.3 Data architecture

| Component | Stored data | Purpose |
|---|---|---|
| MongoDB | Users, conversations, workflows, configuration, metadata | Operational document data |
| PostgreSQL + pgvector | Embeddings and vectors | Semantic Search and RAG |
| Redis | Cache, sessions, queues | Performance and background coordination |
| MinIO | Original uploaded documents | Application object storage |
| EBS | Docker volumes | Persistence after EC2 restart |
| S3 | Backups and retained objects | Durable recovery storage |

> **Figure 5.2.3 – Database and storage design**

![Database design](/images/3.3.pr.drawio.png)

## 5.2.4 RAG workflow

1. The user uploads a learning document.
2. The backend validates and extracts its content.
3. Content is divided into chunks.
4. An embedding model converts each chunk into a vector.
5. pgvector stores vectors, MongoDB stores metadata, and MinIO stores the original file.
6. The user submits a question.
7. The backend generates a query embedding.
8. Semantic Search retrieves relevant chunks.
9. The backend combines the question, context, and instructions into a prompt.
10. The LLM generates a grounded response and sources when supported.

> **Figure 5.2.4 – Retrieval-Augmented Generation workflow**

![RAG workflow](/images/3.4.p.r.png)

## 5.2.5 Operations architecture

```text
CloudWatch Agent → Dashboard → Alarm → SNS
EventBridge Scheduler → Lambda → Start/Stop EC2
AWS Budgets → Actual and forecast cost alerts
```

> **📷 Insert evidence here:** Operations diagram covering CloudWatch, SNS, Lambda, EventBridge, and AWS Budgets.  
> File: `/images/5-Workshop/5.2-Architecture/operations-architecture.png`
<!-- ![Monitoring and automation architecture](/images/5-Workshop/5.2-Architecture/operations-architecture.png) -->

## 5.2.6 Technology stack

| Group | Technology |
|---|---|
| Frontend | Next.js, React, TypeScript |
| Backend | Customized FastGPT, Node.js |
| AI | Google Gemini or OpenAI, RAG |
| Data | MongoDB, PostgreSQL/pgvector, Redis, MinIO, S3 |
| Delivery | Docker, Docker Compose, GitHub Actions, ECR |
| AWS runtime | VPC, EC2, EBS, Elastic IP |
| Operations | CloudWatch, SNS, Lambda, EventBridge, Budgets |

## 5.2.7 Architecture assessment

The single-EC2 design reduces cost and complexity for the MVP. Docker isolates services; EBS and S3 protect state; CI/CD controls versions; CloudWatch adds visibility; and scheduled operations reduce idle cost. Its main limitation is the single point of failure. A future version can adopt managed databases, multiple Availability Zones, a Load Balancer, Auto Scaling, and managed secret storage.

