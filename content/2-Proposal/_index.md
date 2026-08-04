---
title: "Proposal"
date: 2026-08-04
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# AI Learning Assistant Platform

## An Intelligent Document-Based Learning Assistant Platform Deployed on AWS

# Part 1. Project Introduction

## 1.1 Background

The rapid advancement of **Artificial Intelligence (AI)**, particularly **Large Language Models (LLMs)**, has significantly transformed the education sector. AI-powered systems are capable of assisting learners in searching for information, explaining concepts, and interacting with learning materials through natural language, thereby improving learning efficiency.

However, most existing AI chatbots rely solely on pre-trained knowledge and are unable to accurately answer questions related to users' personal learning materials. Without sufficient contextual information, AI models may generate inaccurate responses or provide information that is not consistent with the uploaded documents.

In practice, students often work with various learning resources, including textbooks, lecture slides, reference materials, and laboratory manuals. As the volume of these documents continues to grow, locating relevant information becomes increasingly time-consuming and negatively impacts learning efficiency.

To address these challenges, this project proposes the **AI Learning Assistant Platform**, an intelligent learning assistant that enables users to effectively interact with their learning materials using **Retrieval-Augmented Generation (RAG)** technology. The platform is developed based on **FastGPT** and deployed on **Amazon Web Services (AWS)** to ensure scalability, high availability, and security.

---

## 1.2 Objectives

The primary objective of this project is to develop an intelligent learning assistant platform that enables learners to access and utilize knowledge from educational documents efficiently.

The main objectives include:

- Develop an AI Learning Assistant based on the **Retrieval-Augmented Generation (RAG)** framework.
- Enable users to upload and manage learning materials.
- Build a semantic **Knowledge Base** for information retrieval.
- Allow AI to answer questions based on user-provided documents.
- Provide learning support features, including lesson summarization, quiz generation, and flashcard creation.
- Deploy the platform on **Amazon Web Services (AWS)** using a cloud-native architecture.

---

## 1.3 Solution Overview

The **AI Learning Assistant Platform** is an intelligent educational platform that allows users to upload learning materials and interact with an AI assistant using natural language.

After documents are uploaded, the system automatically processes the content, performs text chunking, generates vector embeddings, and constructs a **Knowledge Base**. When a user submits a question, the platform applies the **Retrieval-Augmented Generation (RAG)** framework to retrieve the most relevant document fragments, which are then provided as contextual information to the AI model for generating accurate and document-grounded responses.

In addition to question answering, the platform supports document management, lesson summarization, quiz generation, flashcard creation, and learning history management. The entire system is containerized using Docker and deployed on AWS, providing a scalable and maintainable foundation for future development.

### Project Overview

| Item | Description |
|------|-------------|
| Project Name | AI Learning Assistant Platform |
| Project Type | Intelligent Learning Assistant Platform |
| Target Users | Students and Instructors |
| Development Platform | FastGPT (Customized) |
| AI Technologies | Retrieval-Augmented Generation (RAG), Knowledge Base, Embedding |
| Cloud Platform | Amazon Web Services (AWS) |
| AWS Services | Amazon EC2, Amazon S3, Amazon CloudWatch |
| Database | MongoDB, PostgreSQL |
| Deployment Method | Docker Compose |
# Part 2. Problem Analysis and Proposed Solution

## 2.1 Problem Statement

In today's educational environment, students frequently rely on various learning resources such as textbooks, lecture slides, reference materials, and laboratory manuals. As the volume of these resources continues to increase, locating specific information becomes increasingly time-consuming, which negatively affects learning efficiency.

Although modern AI chatbots are capable of answering a wide range of questions using natural language, most of them rely solely on pre-trained knowledge. Consequently, they cannot accurately utilize users' personal learning materials and may generate responses that are irrelevant, inconsistent with the uploaded documents, or entirely unsupported by the provided content.

Therefore, there is a growing need for an intelligent solution that enables AI to understand and retrieve information directly from users' learning materials, allowing learners to access accurate information more efficiently.

> **Figure 2.1. Current Challenges in AI-Assisted Learning**

![Figure 2.1](/images/2.1.pr.png)

---

## 2.2 Proposed Solution

To address the limitations of traditional AI chatbots, this project proposes the development of the **AI Learning Assistant Platform** based on the **Retrieval-Augmented Generation (RAG)** framework.

Unlike conventional AI systems, the proposed platform allows users to upload their learning materials to build a personalized **Knowledge Base**. When a user submits a question, the system first retrieves the most relevant document fragments from the Knowledge Base before sending the retrieved context to the Large Language Model (LLM) to generate a grounded response.

As a result, the platform provides several advantages:

- Generate responses based on users' learning materials.
- Reduce AI hallucinations by incorporating retrieved contextual information.
- Provide source references for generated answers.
- Improve the accuracy and reliability of AI-generated responses.

In addition to question answering, the platform also provides several learning support features, including:

- Learning document management.
- Lesson summarization.
- Automatic quiz generation.
- Flashcard generation for revision.
- Learning and conversation history management.

---

## 2.3 System Workflow

The overall workflow of the AI Learning Assistant Platform consists of the following steps:

1. The user uploads learning materials to the platform.
2. The system extracts and preprocesses the document content.
3. The content is divided into smaller text chunks.
4. Vector embeddings are generated and stored in the Vector Database.
5. The user submits a question using natural language.
6. The system retrieves the most relevant document chunks from the Knowledge Base.
7. The retrieved context is provided to the Large Language Model (LLM) to generate an accurate response.
8. The final response, together with its corresponding source references, is presented to the user.

> **Figure 2.2. Workflow of the AI Learning Assistant Platform Using Retrieval-Augmented Generation (RAG)**

![Retrieval-Augmented Generation Workflow](/images/h3bl3.png)

---

## 2.4 Benefits of the Proposed Solution

The adoption of the Retrieval-Augmented Generation (RAG) framework provides several significant benefits for the AI Learning Assistant Platform:

- Rapid information retrieval from learning materials.
- Improved answer accuracy through document-grounded responses.
- Reduced AI hallucinations by leveraging retrieved contextual information.
- Increased learning efficiency and reduced study time.
- A scalable, flexible, and cloud-native learning environment deployed on Amazon Web Services (AWS).

The proposed solution is suitable not only for students and instructors but can also be extended to educational institutions and organizations that require intelligent document-based question-answering systems.
# Part 3. System Design and Architecture

## 3.1 Overall System Architecture

The AI Learning Assistant Platform is designed using a **Client–Server architecture** integrated with the **Retrieval-Augmented Generation (RAG)** framework. The system consists of three primary components:

- **Frontend:** Provides a web-based user interface for document management and AI-assisted learning.
- **Backend:** Handles business logic, user management, document processing, and AI service orchestration.
- **Knowledge Base & AI:** Stores learning resources, performs semantic retrieval, and generates context-aware responses using Large Language Models (LLMs).

> **Figure 3.1. Overall Architecture of the AI Learning Assistant Platform**

![Figure 3.1](/images/3.1.pr.png)

---

## 3.2 AWS Deployment Architecture

The platform is deployed on **Amazon Web Services (AWS)** using **Docker Compose** to simplify deployment and management.

The primary AWS services utilized in the system include:

| AWS Service | Purpose |
|-------------|---------|
| Amazon EC2 | Hosts the application and Docker containers |
| Amazon EBS | Provides persistent storage for application data |
| Amazon S3 | Stores and backs up learning documents |
| Amazon CloudWatch | Monitors system performance and operational metrics |
| AWS IAM | Manages authentication and access control |
| Security Group | Controls inbound and outbound network traffic |

> **Figure 3.2. AWS Deployment Architecture of the AI Learning Assistant Platform**

![Hình 3.2](/images/3.2.p.r.s.png)

---

## 3.3 Database Design

The platform adopts a hybrid database architecture by combining **MongoDB** and **PostgreSQL** to support different data management requirements.

- **MongoDB** stores application data, including users, courses, conversations, and learning history.
- **PostgreSQL** stores metadata and supports data processing for information retrieval.

The main data entities include:

- Users
- Courses
- Learning Documents
- Knowledge Base
- Conversations
- Learning History

> **Figure 3.3. Database Schema of the AI Learning Assistant Platform**

![Figure 3.3](/images/3.3.pr.drawio.png)

---

## 3.4 System Workflow

After users upload learning materials, the system performs the following workflow:

1. Extract textual content from uploaded documents.
2. Split the content into smaller text chunks.
3. Generate vector embeddings for each text chunk.
4. Store the embeddings in the Knowledge Base.
5. Receive a natural language query from the user.
6. Retrieve the most relevant document chunks through semantic search.
7. Generate a context-aware response using the Large Language Model (LLM).

> **Figure 3.4. Retrieval-Augmented Generation (RAG) Workflow of the AI Learning Assistant Platform**

![Figure 3.4](/images/3.4.p.r.png)

---

## 3.5 Technology Stack

| Component | Technology |
|------------|------------|
| Frontend | Next.js, React, TypeScript |
| Backend | FastGPT (Customized) |
| Artificial Intelligence | Large Language Models (LLMs) |
| AI Framework | Retrieval-Augmented Generation (RAG) |
| Database | MongoDB, PostgreSQL |
| Object Storage | MinIO / Amazon S3 |
| Containerization | Docker, Docker Compose |
| Cloud Platform | Amazon Web Services (AWS) |
# Part 4. Deployment and System Evaluation

## 4.1 Deployment Environment

The AI Learning Assistant Platform is deployed on **Amazon Web Services (AWS)** in the **US East (N. Virginia) Region (us-east-1)**. The entire application is containerized using **Docker** and managed through **Docker Compose** on a single Amazon EC2 instance.

The deployment architecture consists of several core components, including the Frontend, AI Learning Assistant Backend (FastGPT), MongoDB, PostgreSQL with pgvector, MinIO, and Nginx. In addition, **Amazon S3** is used for document storage and backup, **Amazon CloudWatch** provides monitoring and logging capabilities, and **AWS Identity and Access Management (IAM)** is responsible for authentication and access control.

### Deployment Environment Configuration

| Component | Technology |
|------------|------------|
| Cloud Platform | Amazon Web Services (AWS) |
| AWS Region | us-east-1 (US East - N. Virginia) |
| Compute Service | Amazon EC2 |
| Container Platform | Docker Compose |
| Reverse Proxy | Nginx |
| Backend Framework | FastGPT (Customized) |
| Frontend Framework | Next.js / React |
| Database | MongoDB |
| Vector Database | PostgreSQL + pgvector |
| Object Storage | MinIO |
| Backup Storage | Amazon S3 |
| Monitoring | Amazon CloudWatch |
| Security | AWS IAM, Security Groups |

> **Figure 4.1. Deployment Environment of the AI Learning Assistant Platform on AWS**
![Figure 4.1](/images/3.4.p.r.png)
---

## 4.2 Deployment Workflow

The deployment process consists of the following steps:

1. Provision and configure an Amazon EC2 instance.
2. Install Docker and Docker Compose.
3. Clone the project source code from GitHub.
4. Configure environment variables.
5. Launch application containers using Docker Compose.
6. Verify the operational status of all services.
7. Configure Nginx and AWS Security Groups.
8. Access and validate the application through a web browser.

> **Figure 4.2. Deployment Workflow of the AI Learning Assistant Platform**
![Figure 4.2](/static/images/4.2.p.r.png)
---

## 4.3 System Testing

After deployment, the system was tested to evaluate the functionality and stability of its core features.

| Function | Result |
|----------|--------|
| User Authentication | Passed |
| Course Creation | Passed |
| Document Upload | Passed |
| Knowledge Base Construction | Passed |
| AI Chat (RAG) | Passed |
| Learning Summary | Passed |
| Quiz Generation | Passed |
| Flashcard Generation | Passed |
| Conversation History | Passed |

The testing results demonstrate that the platform operates reliably and successfully satisfies all functional requirements defined for the project.

---

## 4.4 Monitoring and Operations

During system operation, **Amazon CloudWatch** is used to monitor system performance, resource utilization, and service availability.

The primary monitoring metrics include:

- CPU Utilization
- Memory Usage
- Disk Utilization
- Network Traffic
- Docker Container Logs
- Service Health Status

In addition, learning documents are periodically backed up to **Amazon S3** to ensure data durability and support disaster recovery in case of system failures.

