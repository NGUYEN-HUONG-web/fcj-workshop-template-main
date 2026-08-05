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

The AI Learning Assistant Platform is built using a **Client–Server architecture** combined with the **Retrieval-Augmented Generation (RAG)** framework and deployed on **Amazon Web Services (AWS)**.

The system architecture consists of the following main layers:

- **Client Layer:** Users access the platform through a web browser.
- **Application Layer:** The application is deployed on an **Amazon EC2** instance using **Docker Compose**, including Nginx, Frontend, Backend, MongoDB, PostgreSQL, and MinIO.
- **AI & Data Layer:** The backend handles AI chat, Retrieval-Augmented Generation (RAG), Knowledge Base management, and document processing. **PostgreSQL with pgvector** provides semantic vector retrieval, while **MongoDB** stores application data and system configurations.

> **Figure 3.1. Overall architecture of the AI Learning Assistant Platform.**
![Figure 3.1](/images/3.1.d.x.png)

---

## 3.2 AWS Deployment Architecture

The system is deployed on **Amazon Web Services (AWS)** using **Docker Compose** running on an **Amazon EC2** instance.

The primary AWS services used in the deployment are summarized below.

| AWS Service | Purpose |
|-------------|---------|
| Amazon EC2 | Hosts the entire application and Docker containers |
| Amazon EBS | Stores Docker volumes and persistent application data |
| Amazon S3 | Stores and backs up learning documents |
| Amazon CloudWatch | Monitors system performance, logs, and resource utilization |
| AWS IAM | Manages access control and permissions |
| Security Group | Controls inbound and outbound network traffic |

> **Figure 3.2. AWS deployment architecture of the system.**
![Figure 3.2](/static/images/3.2.d.s.png)

---

## 3.3 Database Design

The platform utilizes multiple storage components to support structured data management, semantic retrieval, and document storage.

| Component | Purpose |
|-----------|---------|
| MongoDB | Stores users, conversations, knowledge bases, and system configurations |
| PostgreSQL + pgvector | Stores vector embeddings for Retrieval-Augmented Generation (RAG) |
| MinIO | Stores learning documents uploaded by users |
| Amazon S3 | Stores backup data and archived learning documents |

> **Figure 3.3. Database architecture of the system.**
![Figure 3.3](/images/3.3.pr.drawio.png)

---

## 3.4 System Workflow

After a user uploads a learning document, the system performs the following process:

1. Extract document content.
2. Split the document into smaller chunks.
3. Generate embeddings for each chunk.
4. Store the processed data in the Knowledge Base.
5. Receive a user's question.
6. Retrieve the most relevant document chunks.
7. Generate an answer using the AI model and return the response to the user.

> **Figure 3.4. Workflow of the AI Learning Assistant Platform using Retrieval-Augmented Generation (RAG).**
![Figure 3.4](/images/3.4.p.r.png)

---

## 3.5 Technologies Used

| Component | Technology |
|-----------|------------|
| Frontend | Next.js, React, TypeScript |
| Backend | FastGPT (Customized) |
| AI Model | Large Language Models (LLMs) |
| AI Framework | Retrieval-Augmented Generation (RAG) |
| Database | MongoDB, PostgreSQL + pgvector |
| Object Storage | MinIO, Amazon S3 |
| Containerization | Docker, Docker Compose |
| Cloud Platform | Amazon Web Services (AWS) |

# Part 4. Deployment and Testing

## 4.1 Deployment Environment

The AI Learning Assistant Platform is deployed on **Amazon Web Services (AWS)** in the **US East (N. Virginia) Region (us-east-1)**. The entire application is containerized using **Docker** and orchestrated with **Docker Compose** on a single **Amazon EC2** instance.

The deployment architecture includes **Nginx**, **Frontend (Next.js/React)**, **AI Learning Assistant Backend (FastGPT Customized)**, **MongoDB**, **PostgreSQL with pgvector**, and **MinIO**. In addition, **Amazon S3** is used for backup storage, **Amazon CloudWatch** monitors system performance and availability, while **AWS IAM** and **Security Groups** provide access control and network security.

### Deployment Environment Configuration

| Component | Technology |
|-----------|------------|
| Cloud Platform | Amazon Web Services (AWS) |
| Region | us-east-1 |
| Compute | Amazon EC2 |
| Container Orchestration | Docker Compose |
| Reverse Proxy | Nginx |
| Backend | FastGPT (Customized) |
| Frontend | Next.js / React |
| Database | MongoDB |
| Vector Database | PostgreSQL + pgvector |
| Object Storage | MinIO |
| Backup Storage | Amazon S3 |
| Monitoring | Amazon CloudWatch |
| Security | AWS IAM, Security Groups |

> **Figure 4.1. Deployment environment of the AI Learning Assistant Platform on AWS.**
![Figure 4.1](/images/4.1.d.x.png)

---

## 4.2 System Deployment Process

The deployment process consists of the following steps:

1. Provision and configure **Amazon EC2**, **Security Groups**, and an **Elastic IP**.
2. Install **Docker** and **Docker Compose** on the EC2 instance.
3. Clone the project source code from GitHub and configure environment variables.
4. Start the Docker containers, including **Nginx**, **Frontend**, **Backend**, **MongoDB**, **PostgreSQL**, and **MinIO**.
5. Configure **Amazon S3** for backup storage and **Amazon CloudWatch** for monitoring.
6. Verify service status and configure **Nginx** as the reverse proxy.
7. Access the application through a web browser for validation and production deployment.

> **Figure 4.2. Deployment workflow of the AI Learning Assistant Platform on AWS.**
![Figure 4.2](/images/4.2.d.x..png)

---

## 4.3 System Testing

After deployment, the system was tested to evaluate the stability and functionality of its core features.

| Function | Result |
|----------|--------|
| User Authentication and Login | Passed |
| Course Management | Passed |
| Learning Document Upload | Passed |
| Knowledge Base Generation | Passed |
| AI Chat (RAG) | Passed |
| Lesson Summary | Passed |
| Quiz Generation | Passed |
| Flashcard Generation | Passed |
| Learning History Management | Passed |

The testing results demonstrate that the system operates reliably. All Docker containers run successfully, and the major platform functionalities perform as expected.

---

## 4.4 Monitoring and Operations

During system operation, **Amazon CloudWatch** is used to monitor application performance, resource utilization, and service availability.

The monitored metrics include:

- CPU Utilization
- Memory Usage
- Disk Usage
- Network Traffic
- Docker Container Logs
- Service Health Status

Furthermore, application data and learning documents are periodically backed up to **Amazon S3** to ensure disaster recovery capability, improve data durability, and maintain overall system reliability.

# Part 5. Security, Cost Analysis, and Risk Management

## 5.1 System Security

The AI Learning Assistant Platform stores user accounts, learning materials, and conversation histories. Therefore, security is considered one of the most important aspects of deploying the system on Amazon Web Services (AWS).

The primary security measures include:

- Using **AWS Identity and Access Management (IAM)** to manage access permissions based on the principle of least privilege.
- Configuring **Security Groups** to restrict inbound traffic and allow access only through required ports.
- Using **HTTPS** to encrypt communication between users and the platform.
- Avoiding hardcoded API keys, passwords, or other sensitive credentials in the source code.
- Managing credentials through **AWS Secrets Manager** or environment variables.
- Using **AWS Key Management Service (AWS KMS)** for data encryption when required.
- Configuring **Amazon S3** with restricted access policies for learning documents and backup data.
- Keeping MongoDB, PostgreSQL, and other internal services inaccessible from the public Internet.
- Monitoring application logs and system activities using **Amazon CloudWatch** to detect abnormal behavior.

---

## 5.2 Estimated Deployment Cost

The AI Learning Assistant Platform is deployed as a Minimum Viable Product (MVP) on Amazon Web Services (AWS), focusing on cost efficiency while maintaining acceptable performance and scalability.

During the initial deployment phase, the entire system is hosted on a single Amazon EC2 instance using Docker Compose, together with AWS storage, monitoring, and security services.

The table below presents the estimated monthly operating cost.

### Table 5.1. Estimated Monthly Deployment Cost

| No. | AWS Service | Estimated Configuration | Purpose | Estimated Cost (USD/Month) |
|:--:|-------------|-------------------------|---------|---------------------------:|
| 1 | Amazon EC2 | t3.large (2 vCPU, 8 GB RAM) | Hosting AI Learning Assistant, Nginx, MongoDB, PostgreSQL, and MinIO | 60 |
| 2 | Amazon EBS | 50 GB (gp3) | Docker volumes and persistent storage | 4 |
| 3 | Amazon S3 | 50 GB | Learning documents and backup storage | 2 |
| 4 | Amazon CloudWatch | Metrics, Logs, Alarms | Monitoring and system alerts | 5 |
| 5 | Elastic IP | One Public IP | Public Internet access | 0* |
| 6 | Data Transfer | Approximately 100 GB/month | Internet traffic | 8 |
| 7 | Google Gemini API / OpenAI API | Based on API requests | AI inference and response generation | 15–50 |

| | | | **Estimated Total Cost** | **94–129 USD/Month** |

> **Note**
>
> - The above costs are estimated for the **US East (N. Virginia) Region (us-east-1)** and may vary depending on AWS pricing.
> - Elastic IP does not incur additional charges when attached to a running EC2 instance.
> - AI model costs depend on the number of requests and processed tokens.

### Cost Evaluation

For an expected workload of **5–20 concurrent users**, the estimated monthly operating cost ranges from **94 to 129 USD**. Amazon EC2 and Large Language Model (LLM) API services represent the largest portion of the overall infrastructure cost.

Deploying the platform on a single EC2 instance using Docker Compose significantly reduces infrastructure expenses during the MVP stage while still providing all essential system functionalities.

### Cost Optimization Strategies

To minimize operational expenses, the platform adopts the following approaches:

- Deploy all services on a single Amazon EC2 instance during the MVP phase.
- Monitor costs using **AWS Budgets** and **AWS Billing Alerts**.
- Optimize EC2 resource utilization through **Amazon CloudWatch** monitoring.
- Stop or remove unused cloud resources after testing.
- Store backup data in Amazon S3 instead of maintaining multiple copies on EC2.
- Limit AI requests and token consumption to control LLM API costs.
- Scale the architecture to **Amazon ECS**, **Application Load Balancer**, and **Auto Scaling** when user demand increases without significantly changing the overall system architecture.

# Part 6. Evaluation and Future Development

## 6.1 Evaluation Based on the AWS Well-Architected Framework

The AI Learning Assistant Platform is evaluated according to the principles of the **AWS Well-Architected Framework** to ensure operational excellence, security, reliability, performance efficiency, and cost optimization.

### Table 6.1. Evaluation Based on the AWS Well-Architected Framework

| Pillar | Implementation in the Project |
|---------|-------------------------------|
| Operational Excellence | Deployed using Docker Compose, source code managed with GitHub, and monitored through Amazon CloudWatch. |
| Security | Uses AWS IAM, Security Groups, HTTPS, AWS Secrets Manager, and AWS KMS to protect infrastructure and data. |
| Reliability | Performs data backup with Amazon S3, monitors system health using CloudWatch, and applies Docker Restart Policies to improve service availability. |
| Performance Efficiency | Uses PostgreSQL with pgvector for semantic search and Retrieval-Augmented Generation (RAG) to improve AI response quality. |
| Cost Optimization | Deploys all services on a single Amazon EC2 instance during the MVP stage and monitors expenses using AWS Budgets and Billing Alerts. |
| Sustainability | The architecture can be extended to Amazon ECS, Auto Scaling, and Application Load Balancer as the user base grows. |

Overall, the platform satisfies the fundamental recommendations of the AWS Well-Architected Framework for deploying an AI-powered application on AWS. The current architecture is well suited for the MVP stage while remaining scalable for future expansion.

> **Figure 6.1. Evaluation of the AI Learning Assistant Platform Based on the AWS Well-Architected Framework**

![Figure 6.1](/images/6.1.p.r.png)

---

## 6.2 Future Development

The AI Learning Assistant Platform can be further enhanced to improve system performance, scalability, and user experience.

The main future development directions include:

- Migrating from Docker Compose to Amazon ECS or Amazon EKS for better scalability.
- Deploying an Application Load Balancer together with Auto Scaling to support a larger number of concurrent users.
- Expanding the Knowledge Base to cover more academic subjects and user groups.
- Integrating additional AI models such as Amazon Bedrock, Google Gemini, and OpenAI.
- Introducing advanced AI features including Mind Map generation, AI Tutor, Speech-to-Text, and Text-to-Speech.
- Developing native mobile applications for Android and iOS.
- Optimizing the Retrieval-Augmented Generation (RAG) pipeline to improve response speed and accuracy.
- Enhancing monitoring, alerting, automated backup, and disaster recovery mechanisms to improve system reliability.

With its current architecture, the AI Learning Assistant Platform provides a solid foundation for future expansion and is capable of supporting a significantly larger number of users on Amazon Web Services.

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
