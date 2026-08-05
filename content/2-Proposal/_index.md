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

> **Figure 2.1. Workflow of the AI Learning Assistant Platform Using Retrieval-Augmented Generation (RAG)**

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

The **AI Learning Assistant Platform** is designed using a **Client–Server architecture** combined with the **Retrieval-Augmented Generation (RAG)** framework and deployed on **Amazon Web Services (AWS)** to provide an intelligent learning platform capable of document management, semantic search, and AI-assisted learning.

The system architecture is divided into five main layers:

- **Client Layer:** Students and instructors access the platform through a web browser using HTTP or HTTPS protocols.
- **Application Layer:** The entire application is deployed on **Amazon EC2** as **Docker containers** managed by **Docker Compose**, including Nginx, Frontend, Backend, MongoDB, PostgreSQL with pgvector, MinIO, and Redis.
- **AI & Data Layer:** The backend handles AI Chat, Retrieval-Augmented Generation (RAG), Knowledge Base management, document processing, and semantic search. **PostgreSQL with pgvector** stores vector embeddings, while **MongoDB** manages user information, conversations, and system configuration.
- **Infrastructure Layer:** **Amazon EBS** provides persistent storage for Docker volumes and application data. **Amazon S3** is used to store backups and archived learning documents.
- **DevOps & Monitoring Layer:** **GitHub Actions** and **Amazon ECR** automate the CI/CD pipeline, while **Amazon CloudWatch**, **CloudWatch Alarm**, **Amazon SNS**, and **AWS Budgets** provide monitoring, alerting, and cost management.

The architecture follows a **Production Lite** approach, making it suitable for an MVP while still providing essential capabilities for deployment, security, monitoring, backup, and automation on AWS.

> **Figure 3.1. Overall Architecture of the AI Learning Assistant Platform.**

![Figure 3.1](/images/3.1.d.x.png)

---

## 3.2 AWS Deployment Architecture

The AI Learning Assistant Platform is deployed on **Amazon Web Services (AWS)** in the **US East (N. Virginia) – us-east-1** Region.

Users access the system through an **Elastic IP** or a custom domain using HTTP or HTTPS. All incoming traffic is filtered by **AWS Security Group** before reaching the Amazon EC2 instance.

Inside the EC2 instance, **Docker Compose** manages the application containers, including **Nginx**, **Frontend**, **Backend**, **MongoDB**, **PostgreSQL with pgvector**, **MinIO**, and **Redis**. **Amazon EBS** provides persistent storage for Docker volumes and application data.

To improve data reliability, MongoDB, PostgreSQL, and MinIO are periodically backed up to **Amazon S3**. **Amazon CloudWatch** together with **CloudWatch Alarm** monitors system performance and generates alerts when predefined thresholds are exceeded. **Amazon SNS** delivers email notifications for critical events.

The deployment process is automated through **GitHub Actions** and **Amazon ECR**. Whenever new code is pushed to the GitHub repository, GitHub Actions automatically builds Docker images, pushes them to Amazon ECR, and deploys the latest version to Amazon EC2.

### AWS Services Used

| AWS Service | Purpose |
|-------------|---------|
| Amazon EC2 | Hosts the entire AI Learning Assistant Platform |
| Amazon EBS | Provides persistent storage for Docker volumes and application data |
| Amazon S3 | Stores backups of MongoDB, PostgreSQL, and learning documents |
| Amazon ECR | Stores and manages Docker container images |
| Amazon CloudWatch | Monitors system metrics, logs, and dashboards |
| CloudWatch Alarm | Triggers alerts based on CPU, memory, disk, and service health |
| Amazon SNS | Sends email notifications for monitoring alerts |
| AWS IAM | Manages authentication and authorization for AWS resources |
| Security Group | Controls inbound and outbound network access to EC2 |
| AWS Budgets | Monitors AWS spending and generates budget alerts |

The current architecture is optimized for internship projects and MVP deployments. Running the application on a single Amazon EC2 instance minimizes operational costs while maintaining scalability through Docker containers, CI/CD automation, and AWS management services.

> **Figure 3.2. AWS Deployment Architecture of the AI Learning Assistant Platform.**

![Figure 3.2](/images/3.2.d.s.png)

---

## 3.3 Database Design

The platform uses multiple storage components to satisfy the requirements of user data management, semantic retrieval, and document storage.

| Component | Purpose |
|-----------|---------|
| MongoDB | Stores user accounts, conversations, Knowledge Base metadata, and system configuration |
| PostgreSQL + pgvector | Stores vector embeddings for semantic search and Retrieval-Augmented Generation |
| MinIO | Stores learning documents uploaded by users |
| Amazon S3 | Stores backups of databases and uploaded learning documents |
| Amazon EBS | Provides persistent storage for Docker volumes and application data |

MongoDB, PostgreSQL, and MinIO operate within the internal Docker network and are not directly exposed to the public Internet, improving the overall security of the system.

> **Figure 3.3. Database Architecture of the AI Learning Assistant Platform.**

![Figure 3.3](/images/3.3.pr.drawio.png)

---

## 3.4 System Workflow

After a user uploads a learning document, the AI Learning Assistant Platform performs the Retrieval-Augmented Generation (RAG) workflow as follows:

1. The user uploads a learning document.
2. The backend extracts the document content.
3. The document is divided into smaller chunks.
4. Vector embeddings are generated for each chunk.
5. The embeddings are stored in PostgreSQL with pgvector, while metadata is stored in MongoDB.
6. The user submits a question through the AI Chat interface.
7. The backend generates an embedding for the question and performs semantic search against the vector database.
8. Relevant document chunks are retrieved and combined with the user's question to construct a prompt.
9. The prompt is sent to the Large Language Model (LLM).
10. The AI generates an answer based on the retrieved context and returns the response together with reference sources.

This workflow significantly reduces hallucination, improves response accuracy, and enables the AI model to answer questions based on user-provided learning materials.

> **Figure 3.4. Retrieval-Augmented Generation (RAG) Workflow of the AI Learning Assistant Platform.**

![Figure 3.4](/images/3.4.p.r.png)

---

## 3.5 Technologies Used

| Component | Technology |
|-----------|------------|
| Frontend | Next.js, React, TypeScript |
| Backend | FastGPT (Customized) |
| AI Model | Large Language Models (LLMs) |
| AI Framework | Retrieval-Augmented Generation (RAG) |
| Database | MongoDB, PostgreSQL with pgvector |
| Object Storage | MinIO |
| Containerization | Docker, Docker Compose |
| Version Control | GitHub |
| CI/CD | GitHub Actions |
| Container Registry | Amazon ECR |
| Cloud Platform | Amazon Web Services (AWS) |
| Monitoring | Amazon CloudWatch, CloudWatch Alarm |
| Backup Storage | Amazon S3 |
| Persistent Storage | Amazon EBS |
| Cost Management | AWS Budgets |

# Part 4. Deployment and Testing

## 4.1 Deployment Environment

The AI Learning Assistant Platform is deployed on **Amazon Web Services (AWS)** in the **US East (N. Virginia) – us-east-1** Region.

The application runs on an **Amazon EC2** instance using **Docker Compose**. The deployment includes **Nginx**, **Frontend (Next.js/React)**, **Backend (FastGPT Customized)**, **MongoDB**, **PostgreSQL with pgvector**, and **MinIO**.

Supporting AWS services include **Amazon EBS** for persistent storage, **Amazon S3** for backups, **Amazon ECR** for Docker image management, **GitHub Actions** for CI/CD, **Amazon CloudWatch** for monitoring, **AWS IAM**, **Security Group**, and **AWS Budgets**.

### Deployment Environment

| Component | Technology / Service |
|------------|----------------------|
| Cloud Platform | Amazon Web Services (AWS) |
| Region | us-east-1 |
| Compute | Amazon EC2 |
| Storage | Amazon EBS |
| Container | Docker, Docker Compose |
| Reverse Proxy | Nginx |
| Database | MongoDB, PostgreSQL + pgvector |
| Object Storage | MinIO |
| Container Registry | Amazon ECR |
| CI/CD | GitHub Actions |
| Monitoring | Amazon CloudWatch |
| Backup | Amazon S3 |
| Security | AWS IAM, Security Group |
| Cost Monitoring | AWS Budgets |

> **Figure 4.1. Deployment Environment of the AI Learning Assistant Platform on AWS.**

![Figure 4.1](/images/4.1.d.x.png)

---

## 4.2 Deployment Process

The deployment workflow consists of the following steps:

1. Create and configure Amazon EC2.
2. Install Docker and Docker Compose.
3. Push source code to GitHub.
4. GitHub Actions builds Docker images.
5. Docker images are pushed to Amazon ECR.
6. Amazon EC2 pulls the latest images and starts containers using Docker Compose.
7. Amazon CloudWatch monitors system health.
8. MongoDB, PostgreSQL, and MinIO data are backed up to Amazon S3.

> **Figure 4.2. Deployment Workflow of the AI Learning Assistant Platform.**

![Figure 4.2](/images/4.2.d.x..png)

---

## 4.3 System Testing

| Test Item | Result |
|------------|--------|
| User Authentication | Passed |
| Course Management | Passed |
| Document Upload | Passed |
| Knowledge Base | Passed |
| AI Chat (RAG) | Passed |
| Summary | Passed |
| Quiz | Passed |
| Flashcard | Passed |
| Deployment & CI/CD | Passed |

The testing results indicate that the platform operates successfully, all Docker containers are running correctly, and the core system functions meet the project requirements.

---

## 4.4 Monitoring and Operations

The platform uses **Amazon CloudWatch** to monitor system performance and resource utilization.

The monitored metrics include:

- CPU Utilization
- Memory Usage
- Disk Usage
- Network Traffic
- Docker Container Logs

Application data and uploaded learning documents are backed up regularly to **Amazon S3**, while **AWS Budgets** is used to monitor AWS spending and notify administrators when budget thresholds are exceeded.

# Part 5. Security, Cost Optimization, and Future Development

## 5.1 System Security

The AI Learning Assistant Platform stores user accounts, learning materials, and conversation history. Therefore, security is an essential consideration throughout the AWS deployment.

The main security measures include:

- Using **AWS IAM** to manage access permissions based on the **Principle of Least Privilege**.
- Using **Security Groups** to control inbound access to the Amazon EC2 instance.
- Using **HTTPS** to encrypt communication between users and the platform.
- Storing API keys and configuration values in **Environment Variables** instead of hardcoding them into the source code.
- Restricting access to backup data stored in **Amazon S3**.
- Keeping MongoDB, PostgreSQL, and MinIO within the internal Docker network without direct Internet access.
- Using **Amazon CloudWatch** to monitor system status and detect abnormal activities.

---

## 5.2 Estimated Deployment Cost

The platform is deployed using a **Production Lite** architecture to balance performance, scalability, and operational cost.

### Table 5.1. Estimated Monthly Deployment Cost

| AWS Service | Purpose | Estimated Cost (USD/Month) |
|--------------|---------|---------------------------:|
| Amazon EC2 (t3.large) | Application Hosting | 60 |
| Amazon EBS (50 GB) | Persistent Storage | 4 |
| Amazon S3 | Backup Storage | 2 |
| Amazon ECR | Docker Image Registry | 1 |
| Amazon CloudWatch | Monitoring | 3 |
| Data Transfer | Internet Traffic | 8 |
| Google Gemini / OpenAI API | AI Processing | 15–50 |

| | **Estimated Total** | **93–128 USD/Month** |

### Cost Optimization

The platform applies several cost optimization strategies:

- Deploy all services on a single Amazon EC2 instance during the MVP phase.
- Monitor AWS spending using **AWS Budgets**.
- Store backups on **Amazon S3** instead of maintaining multiple copies on EC2.
- Remove unused AWS resources after testing.
- Optimize AI API requests to reduce token consumption.
- Scale to **Application Load Balancer** and **Amazon ECS** only when user demand increases.

---

# Part 6. Evaluation and Future Development

## 6.1 Evaluation Based on the AWS Well-Architected Framework

The AI Learning Assistant Platform is evaluated according to the principles of the **AWS Well-Architected Framework**.

### Table 6.1. System Evaluation

| Pillar | Implementation |
|---------|----------------|
| Operational Excellence | Docker Compose, GitHub Actions, Amazon CloudWatch |
| Security | AWS IAM, Security Group, HTTPS, Environment Variables |
| Reliability | Amazon S3 Backup, Docker Restart Policy, Amazon CloudWatch |
| Performance Efficiency | PostgreSQL + pgvector, Retrieval-Augmented Generation (RAG) |
| Cost Optimization | Amazon EC2, AWS Budgets, Amazon CloudWatch |
| Sustainability | The architecture can be extended to Amazon ECS and Application Load Balancer |

Overall, the current architecture satisfies the fundamental principles of the AWS Well-Architected Framework for an AI application deployed on AWS. It is suitable for an MVP while remaining scalable for future development.

> **Figure 6.1. Evaluation of the AI Learning Assistant Platform Based on the AWS Well-Architected Framework.**

![Figure 6.1](/images/6.1.p.r.png)

---

## 6.2 Future Development

In the future, the AI Learning Assistant Platform can be enhanced in the following directions:

- Migrate from Docker Compose to **Amazon ECS** for better scalability.
- Deploy an **Application Load Balancer (ALB)** to distribute incoming traffic.
- Expand the Knowledge Base to support more subjects and users.
- Integrate additional AI models such as **Amazon Bedrock**, **Google Gemini**, or **OpenAI**.
- Introduce new AI features, including AI Tutor, Mind Map generation, Speech-to-Text, and Text-to-Speech.
- Enhance monitoring, alerting, and backup mechanisms to improve system reliability.

With its current architecture, the AI Learning Assistant Platform is well suited for MVP deployment and can be expanded to support larger workloads and more users on Amazon Web Services in the future.

# Part 7. Conclusion

## 7.1 Project Achievements

The AI Learning Assistant Platform was developed to help learners interact with educational resources through Artificial Intelligence combined with Retrieval-Augmented Generation (RAG).

The platform enables users to upload learning materials, build a personalized Knowledge Base, and communicate with the AI using natural language. This approach significantly improves response accuracy compared with traditional AI chatbots that rely solely on pre-trained knowledge.

In addition to AI-powered question answering, the platform provides several learning support features, including document management, lesson summarization, quiz generation, flashcard creation, and conversation history management.

The entire application is deployed on Amazon Web Services (AWS), meeting the fundamental requirements for performance, security, scalability, and system management.

The major achievements of this project include:

- Developing an AI Learning Assistant Platform based on FastGPT.
- Applying Retrieval-Augmented Generation (RAG) to improve AI response quality.
- Deploying the platform on Amazon EC2 using Docker Compose.
- Integrating MongoDB, PostgreSQL, MinIO, and AWS cloud services.
- Designing a scalable architecture suitable for the MVP stage.

---

## 7.2 Limitations

Although the project has achieved its primary objectives, several limitations remain:

- The current architecture relies on a single Amazon EC2 instance and therefore does not provide High Availability.
- Auto Scaling and Load Balancing have not yet been implemented.
- AI response quality still depends heavily on the quality of uploaded learning materials.
- Mobile applications and offline learning capabilities are not currently supported.
- Several advanced AI features are still under research and development.

---

## 7.3 Future Work

Future improvements to the AI Learning Assistant Platform include:

- Migrating to Amazon ECS or Amazon EKS to improve scalability.
- Deploying Application Load Balancer and Auto Scaling to support more concurrent users.
- Integrating additional AI models such as Amazon Bedrock, Google Gemini, and OpenAI.
- Adding advanced learning features including AI Tutor, Mind Map generation, Speech-to-Text, and Text-to-Speech.
- Developing Android and iOS mobile applications.
- Optimizing the Retrieval-Augmented Generation (RAG) pipeline to improve response speed and accuracy.
- Enhancing monitoring, backup, and disaster recovery mechanisms to increase system reliability.

These future enhancements will enable the platform to serve a broader range of users while better addressing the needs of modern intelligent education systems.

---

## 7.4 Conclusion

The AI Learning Assistant Platform is an intelligent learning support solution built on FastGPT and deployed on Amazon Web Services (AWS).

By combining Retrieval-Augmented Generation (RAG) with a Knowledge Base, the platform delivers responses grounded in user-provided learning materials, thereby improving answer accuracy and reducing AI hallucinations.

The platform is designed with a scalable architecture that can easily integrate additional AI models and AWS services in the future. Beyond achieving the objective of building an intelligent learning assistant, this project also establishes a practical foundation for further research and the application of Generative AI technologies in education.
Besides developing an intelligent learning platform, the project also demonstrates how to deploy a **Generative AI** application on **Amazon Web Services (AWS)** using **Docker Compose**, **Amazon EC2**, **Amazon S3**, **Amazon CloudWatch**, and AWS security services. This deployment architecture provides a scalable, secure, and maintainable foundation for future system enhancements and feature expansion.
