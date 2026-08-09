---
title: "Project"
date: 2026-08-04
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# AI Learning Assistant Platform

### An Intelligent Document-Based Learning Assistant Platform Deployed on AWS

# AI Learning Assistant Platform

### An Intelligent Document-Based Learning Assistant Platform Deployed on AWS

# Part 1. Project Introduction

# Project Team Information

| No. | Full Name | Student ID | Role |
|:---:|---|---|---|
| 1 | Nguyễn Thị Thu Hường | 3122411079 | Team Leader |
| 2 | Trần Quốc Bảo | 3122411015 | Team Member |
| 3 | Nguyễn Ngọc Thúy Vy | 3122411256 | Team Member |

# Part 2. Project Overviews

## 1.1 Background

In recent years, the rapid advancement of **Artificial Intelligence (AI)** and **Large Language Models (LLMs)** has created significant opportunities for educational applications. AI systems are no longer limited to information retrieval but are also capable of interacting with users through natural language, helping improve learning efficiency and reduce the time required to search for educational resources.

However, most existing AI chatbots primarily rely on knowledge acquired during model training. When users ask questions related to textbooks, lecture slides, or private learning materials, the AI may generate inaccurate responses or fail to reflect the actual content of those documents. This phenomenon is commonly referred to as **AI Hallucination**, which reduces the reliability of AI systems in educational environments.

In practice, students and lecturers often manage a large collection of learning resources, including textbooks, lecture notes, reference materials, laboratory manuals, and research papers. Searching for specific information across these documents is time-consuming and negatively affects learning and research productivity.

To address these challenges, the **AI Learning Assistant Platform** was developed as an intelligent learning assistant that enables users to upload documents, build a **Knowledge Base**, and interact with AI using natural language. The platform applies **Retrieval-Augmented Generation (RAG)** to retrieve relevant information from uploaded documents before generating responses, thereby improving answer accuracy and significantly reducing AI hallucinations.

The entire platform is deployed on **Amazon Web Services (AWS)** using **Docker Compose** on **Amazon EC2**. It also integrates **GitHub Actions**, **Amazon ECR**, and **Amazon CloudWatch** to automate deployment, monitor system performance, and simplify operational management.

---

## 1.2 Objectives

The project aims to develop an intelligent learning assistant platform that enables students and lecturers to utilize educational materials more effectively through Generative AI and cloud computing technologies.

### Functional Objectives

- Develop the **AI Learning Assistant Platform** based on FastGPT.
- Enable users to upload and manage learning materials.
- Build a **Knowledge Base** from user-provided documents.
- Apply **Retrieval-Augmented Generation (RAG)** to answer questions based on document content.
- Provide AI-powered features such as AI Chat, Summary, Quiz, and Flashcards.
- Store conversation history and learning records.

### Technical Objectives

- Deploy the platform on **Amazon Web Services (AWS)**.
- Containerize the entire application using **Docker Compose**.
- Use **Amazon EC2** as the application hosting environment.
- Store data using **MongoDB**, **PostgreSQL (pgvector)**, and **MinIO**.
- Implement a **CI/CD** pipeline using **GitHub Actions** and **Amazon ECR**.
- Monitor system performance using **Amazon CloudWatch**.
- Apply security best practices through **AWS IAM**, **Security Groups**, and environment variable management.

---

## 1.3 Project Scope

The project focuses on developing a **Minimum Viable Product (MVP)** of the AI Learning Assistant Platform with core features that support learning and academic research.

### Functional Scope

- User authentication and account management.
- Course and Knowledge Base management.
- Learning material upload.
- RAG-based AI Chat.
- Document summarization.
- Quiz generation.
- Flashcard generation.
- Conversation history management.

### Deployment Scope

The platform is deployed on **Amazon EC2** using a **Production Lite** architecture. All application components are managed through **Docker Compose**, including:

- Nginx
- Frontend (Next.js/React)
- Backend (FastGPT Customized)
- MongoDB
- PostgreSQL + pgvector
- MinIO

In addition, the platform integrates several AWS services to support deployment and operations:

- Amazon EBS
- Amazon S3
- Amazon ECR
- Amazon CloudWatch
- AWS IAM
- Security Group
- AWS Budgets

---

## 1.4 Solution Overview

AI Learning Assistant Platform is an intelligent learning platform that enables users to retrieve knowledge from educational documents using Artificial Intelligence.

After users upload their learning materials, the backend automatically processes the documents by extracting content, performing document chunking, generating vector embeddings, and storing them in the **Knowledge Base**. When a user submits a question, the platform applies **Retrieval-Augmented Generation (RAG)** to retrieve the most relevant document chunks from **PostgreSQL with pgvector** before combining them with the user's query to create the context for the Large Language Model.

This approach enables the platform to generate responses that are grounded in the user's learning materials while significantly reducing AI hallucinations compared with traditional AI chatbots.

The entire application is deployed on **Amazon Web Services (AWS)** using Docker Compose. The deployment workflow is automated through **GitHub Actions** and **Amazon ECR**, while **Amazon CloudWatch** is used to monitor system performance and operational status.

---

### Table 1.1. Project Overview

| Item | Description |
|------|-------------|
| Project Name | AI Learning Assistant Platform |
| Project Type | Intelligent Learning Assistant Platform |
| Target Users | Students and Lecturers |
| Development Platform | FastGPT (Customized) |
| AI Technologies | Large Language Models (LLMs), Retrieval-Augmented Generation (RAG) |
| Cloud Platform | Amazon Web Services (AWS) |
| AWS Services | Amazon EC2, Amazon EBS, Amazon S3, Amazon ECR, Amazon CloudWatch, AWS IAM, AWS Budgets |
| Database | MongoDB, PostgreSQL + pgvector |
| Object Storage | MinIO |
| Containerization | Docker, Docker Compose |
| CI/CD | GitHub Actions + Amazon ECR |
| Monitoring | Amazon CloudWatch |
| Deployment Architecture | Production Lite on Amazon EC2 |

# Part 2. Problem Analysis and Proposed Solution

## 2.1 Problem Statement

In today's educational environment, students and lecturers often use a wide variety of learning resources, including textbooks, lecture slides, reference materials, laboratory manuals, and research papers. As the amount of educational content continues to grow, locating specific information becomes increasingly time-consuming and negatively impacts learning efficiency.

Although modern AI chatbots are capable of answering questions using natural language, most of them rely primarily on knowledge acquired during model training. As a result, they cannot accurately utilize users' private learning materials and may generate responses that are unrelated to the uploaded documents or inconsistent with the intended context.

This limitation often leads to **AI Hallucination**, where the model produces incorrect or unsupported information. Consequently, conventional AI chatbots are not well suited for educational scenarios that require responses grounded in specific learning materials.

Therefore, there is a need for an intelligent solution that enables AI to understand and retrieve information directly from user-provided educational documents, allowing learners to access accurate information quickly while improving the reliability of AI-generated responses.

---

## 2.2 Proposed Solution

To address these challenges, this project proposes the development of the **AI Learning Assistant Platform** based on the **Retrieval-Augmented Generation (RAG)** framework.

Unlike traditional AI chatbots, the platform allows users to upload learning materials and automatically build a **Knowledge Base**. When a user submits a question, the system first retrieves the most relevant document fragments from the Knowledge Base before sending them to the Large Language Model (LLM) to generate the final response.

By combining document retrieval with generative AI, the platform is able to:

- Answer questions based on users' learning materials.
- Significantly reduce AI hallucinations.
- Provide references to the source documents used in the response.
- Improve the accuracy and reliability of AI-generated answers.

In addition to AI-powered question answering, the platform also provides several learning support features, including:

- Learning material management.
- Document summarization.
- Quiz generation.
- Flashcard generation.
- Learning and conversation history management.

---

## 2.3 System Workflow

The overall workflow of the platform consists of the following steps:

1. Users upload learning materials to the platform.
2. The system extracts and processes the document content.
3. The document is divided into smaller chunks.
4. Vector embeddings are generated for each chunk.
5. The embeddings are stored in the vector database.
6. Users submit questions using natural language.
7. The system retrieves the most relevant document chunks from the Knowledge Base.
8. The retrieved content is provided to the Large Language Model (LLM) as contextual information.
9. The AI generates a response based on the retrieved knowledge and returns the answer together with the corresponding references.

This workflow enables the platform to generate responses grounded in user-provided learning materials rather than relying solely on the pretrained knowledge of the language model.

> **Figure 2.1. Retrieval-Augmented Generation (RAG) Workflow of AI Learning Assistant Platform.**

![Figure 2.1](/images/h3bl3.png)

---

## 2.4 Benefits of the Proposed Solution

Applying the Retrieval-Augmented Generation (RAG) framework to the AI Learning Assistant Platform provides several advantages for both learners and instructors.

The key benefits include:

- Quickly retrieving information from learning materials.
- Improving response accuracy by utilizing document-based knowledge.
- Reducing AI hallucinations through contextual document retrieval.
- Saving time when studying and reviewing course materials.
- Providing an intelligent, flexible, and scalable learning platform on Amazon Web Services (AWS).

Beyond educational applications, the proposed solution can also be extended to universities, training organizations, and enterprises that require intelligent document-based question-answering systems for internal knowledge management.
# Part 3. System Design and Architecture

## 3.1 Overall System Architecture

AI Learning Assistant Platform is built using a **Client–Server** architecture combined with the **Retrieval-Augmented Generation (RAG)** approach and deployed on **Amazon Web Services (AWS)** to provide an intelligent learning platform capable of document management, semantic search, and AI-assisted learning.

The system follows a **Layered Architecture**, where each layer is responsible for a specific function. This architecture improves scalability, maintainability, and simplifies cloud deployment. The entire application is containerized using Docker and deployed on Amazon EC2 with Docker Compose.

The system architecture consists of five main layers:

- **Client Layer:** Students and lecturers access the platform through a web browser using HTTP or HTTPS. The user interface is developed with Next.js and React, providing features such as course management, document upload, AI Chat, Summary, Quiz, Flashcards, and learning history.

- **Application Layer:** The application is deployed on **Amazon EC2** as a collection of **Docker Containers** managed by **Docker Compose**, including Nginx, Frontend, Backend, MongoDB, PostgreSQL with pgvector, and MinIO. Nginx functions as a reverse proxy, routing incoming requests to the appropriate services.

- **AI & Data Layer:** The backend handles AI Chat, Retrieval-Augmented Generation (RAG), Knowledge Base management, document processing, and semantic search. **PostgreSQL with pgvector** stores vector embeddings, MongoDB manages user information, conversations, and system configurations, while MinIO stores uploaded learning materials.

- **Infrastructure Layer:** The system is deployed on Amazon Web Services (AWS). Amazon EC2 provides the application runtime environment, Amazon EBS stores Docker volumes and persistent data, and Amazon S3 stores backup files. AWS IAM manages access permissions, Security Groups control network traffic, and Elastic IP provides a static public IP address for external access.

- **DevOps & Monitoring Layer:** GitHub Actions and Amazon ECR support the CI/CD pipeline. Whenever source code is updated in the GitHub repository, Docker images are automatically built and pushed to Amazon ECR before being deployed to Amazon EC2. Amazon CloudWatch collects logs and metrics, CloudWatch Alarm sends notifications when issues occur, and AWS Budgets monitors AWS spending.

The architecture follows a **Production Lite** approach, making it suitable for the MVP stage while still satisfying deployment, security, monitoring, backup, and automation requirements on AWS.

> **Figure 3.1. Overall Architecture of AI Learning Assistant Platform.**

![Figure 3.1](/images/3.1.d.x.png)

---

## 3.2 AWS Deployment Architecture

AI Learning Assistant Platform is deployed on **Amazon Web Services (AWS)** in the **US East (N. Virginia) – us-east-1** Region.

The entire system is deployed inside an **Amazon VPC**. The Amazon EC2 instance is located in a **Public Subnet** and associated with an **Elastic IP**, allowing users to access the application through HTTP or HTTPS. A Security Group is configured to allow only the required ports, including SSH (22), HTTP (80), and HTTPS (443), while blocking unauthorized access.

Inside the EC2 instance, Docker Compose manages all application containers, including Nginx, Frontend, Backend, MongoDB, PostgreSQL with pgvector, and MinIO. These containers communicate through an internal Docker network to ensure secure data exchange. Amazon EBS provides persistent storage for Docker volumes and application data.

To improve data durability, MongoDB, PostgreSQL, and MinIO are backed up regularly to **Amazon S3**. **Amazon CloudWatch** together with **CloudWatch Alarm** monitors system performance, collects logs, and sends alerts whenever abnormal conditions are detected.

The deployment process is fully automated using **GitHub Actions** and **Amazon ECR**. Whenever source code is pushed to the GitHub repository, GitHub Actions automatically builds Docker images, pushes them to Amazon ECR, and deploys the latest version to Amazon EC2.

### Table 3.1. AWS Services Used

| AWS Service | Purpose | Reason for Selection |
|-------------|---------|----------------------|
| Amazon VPC | Provides an isolated network environment | Improves security through network isolation |
| Public Subnet | Hosts the Amazon EC2 instance | Enables Internet access |
| Internet Gateway | Connects the VPC to the Internet | Allows users to access the application |
| Elastic IP | Provides a static public IP address | Simplifies access and domain configuration |
| Amazon EC2 | Hosts the AI Learning Assistant Platform | Easy deployment, management, and scalability |
| Amazon EBS | Stores Docker volumes and persistent data | Prevents data loss after EC2 restarts |
| Amazon S3 | Stores backups of MongoDB, PostgreSQL, and learning materials | Highly durable, cost-effective, and scalable |
| Amazon ECR | Stores Docker images | Seamless integration with GitHub Actions and EC2 |
| Amazon CloudWatch | Collects metrics and logs | Enables real-time performance monitoring |
| CloudWatch Alarm | Sends alerts when issues occur | Supports early issue detection |
| Amazon SNS | Sends email notifications | Automatically notifies administrators |
| AWS IAM | Manages IAM users and permissions | Enforces the Least Privilege principle |
| Security Group | Controls network access | Protects EC2 from unauthorized access |
| AWS Budgets | Tracks AWS costs and spending | Helps control cloud expenses |

The current architecture is optimized for internship projects and the MVP stage. Deploying the application on a single Amazon EC2 instance minimizes operational costs while maintaining scalability through Docker containers, CI/CD automation, and AWS management services.

> **Figure 3.2. AWS Deployment Architecture of AI Learning Assistant Platform.**

![Figure 3.2](/images/3.2.d.s.png)

---

## 3.3 Database Design

The system adopts a hybrid storage architecture combining relational databases, NoSQL databases, and object storage to optimize performance for different types of data.

### Table 3.2. Storage Components

| Component | Purpose |
|------------|---------|
| MongoDB | Stores user information, conversations, Knowledge Base data, and system configurations |
| PostgreSQL + pgvector | Stores vector embeddings for Semantic Search and Retrieval-Augmented Generation |
| MinIO | Stores uploaded learning materials |
| Amazon S3 | Stores backups of MongoDB, PostgreSQL, and learning materials |
| Amazon EBS | Stores Docker volumes and persistent application data |

MongoDB stores the platform's operational data, PostgreSQL with pgvector stores vector embeddings for semantic retrieval, MinIO stores users' original learning materials, and Amazon S3 is used for backup to ensure reliable data recovery.

MongoDB, PostgreSQL, and MinIO operate exclusively within the internal Docker network and are not directly exposed to the Internet, enhancing overall system security.

> **Figure 3.3. Database Design of the System.**

![Figure 3.3](/images/3.3.pr.drawio.png)

---

## 3.4 System Workflow

After a user uploads learning materials, AI Learning Assistant Platform executes the Retrieval-Augmented Generation (RAG) workflow through the following steps:

1. The user uploads learning materials to the platform.
2. The backend extracts the document content.
3. The document is divided into smaller chunks.
4. Vector embeddings are generated for each chunk.
5. Embeddings are stored in PostgreSQL with pgvector, while metadata is stored in MongoDB.
6. The user submits a question through the AI Chat interface.
7. The backend generates an embedding for the query and performs semantic search in the vector database.
8. Relevant document chunks are retrieved and combined with the user's question to create a prompt.
9. The prompt is sent to a Large Language Model (LLM).
10. The AI generates an answer based on the retrieved context and returns the response together with reference sources.

The workflow consists of two major phases:

- **Knowledge Base Construction:** Includes document upload, document processing, chunking, embedding generation, and data storage.
- **AI Chat:** Includes semantic search, prompt engineering, and answer generation using a Large Language Model.

Separating these two phases enables the platform to reuse the Knowledge Base across multiple conversations, reducing processing time and improving retrieval efficiency.

> **Figure 3.4. Retrieval-Augmented Generation (RAG) Workflow of AI Learning Assistant Platform.**

![Figure 3.4](/images/3.4.p.r.png)

---

## 3.5 Technologies Used

### Table 3.3. Technologies Used in the System

| Component | Technology |
|------------|------------|
| Frontend | Next.js, React, TypeScript |
| Backend | FastGPT (Customized), Node.js |
| AI Model | Google Gemini / OpenAI (LLMs) |
| AI Framework | Retrieval-Augmented Generation (RAG) |
| Database | MongoDB, PostgreSQL + pgvector |
| Object Storage | MinIO |
| Reverse Proxy | Nginx |
| Containerization | Docker, Docker Compose |
| Version Control | GitHub |
| CI/CD | GitHub Actions |
| Container Registry | Amazon ECR |
| Cloud Platform | Amazon EC2, Amazon EBS, Amazon S3 |
| Monitoring | Amazon CloudWatch, CloudWatch Alarm |
| Security | AWS IAM, Security Group |
| Cost Management | AWS Budgets |

# Part 4. Deployment and Testing

## 4.1 Deployment Environment

AI Learning Assistant Platform is deployed on **Amazon Web Services (AWS)** in the **US East (N. Virginia) – us-east-1** Region using a **Production Lite** architecture.

The entire system is deployed within an **Amazon VPC**, where an **Amazon EC2** instance is placed in a **Public Subnet** and associated with an **Elastic IP**, allowing users to access the application over HTTP or HTTPS. A **Security Group** is configured to allow only the required service ports, including SSH (22), HTTP (80), and HTTPS (443), ensuring secure access to the system.

The application is containerized using **Docker** and managed by **Docker Compose**, consisting of **Nginx**, **Frontend (Next.js/React)**, **Backend (FastGPT Customized)**, **MongoDB**, **PostgreSQL with pgvector**, and **MinIO**. All containers communicate through an internal Docker network to ensure secure and reliable service communication.

The platform utilizes **Amazon EBS** for persistent storage, **Amazon S3** for backup storage, **Amazon ECR** for Docker image management, **GitHub Actions** for CI/CD automation, **Amazon CloudWatch** for system monitoring, together with **AWS IAM**, **Security Group**, and **AWS Budgets** for security and cost management.

### Deployment Environment Configuration

| Component | Technology / Service |
|------------|----------------------|
| Cloud Platform | Amazon Web Services (AWS) |
| Region | us-east-1 (N. Virginia) |
| Network | Amazon VPC, Public Subnet |
| Compute | Amazon EC2 |
| Public IP | Elastic IP |
| Persistent Storage | Amazon EBS |
| Containerization | Docker, Docker Compose |
| Reverse Proxy | Nginx |
| Frontend | Next.js, React |
| Backend | FastGPT (Customized) |
| Database | MongoDB, PostgreSQL + pgvector |
| Object Storage | MinIO |
| Container Registry | Amazon ECR |
| CI/CD | GitHub Actions |
| Monitoring | Amazon CloudWatch |
| Backup Storage | Amazon S3 |
| Security | AWS IAM, Security Group |
| Cost Monitoring | AWS Budgets |

> **Figure 4.1. Deployment Environment of AI Learning Assistant Platform on AWS.**

![Figure 4.1](/images/4.1.d.x.png)

---

## 4.2 System Deployment Process

The deployment process is carried out through the following steps:

1. Provision and configure AWS infrastructure, including **Amazon VPC**, **Public Subnet**, **Internet Gateway**, **Security Group**, **Elastic IP**, and **Amazon EC2**.
2. Create an **IAM User** and assign permissions following the **Least Privilege** principle for deployment and system administration.
3. Install **Docker** and **Docker Compose** on the Amazon EC2 instance.
4. Configure environment variables and Docker Compose for all application services.
5. Push the application source code to the **GitHub Repository**.
6. **GitHub Actions** automatically builds Docker images and pushes them to **Amazon ECR**.
7. Amazon EC2 pulls the latest Docker images from Amazon ECR and starts the containers using **Docker Compose**.
8. **Amazon CloudWatch** collects metrics and logs to monitor the operational status of the platform.
9. MongoDB, PostgreSQL, and MinIO data are backed up periodically to **Amazon S3** to ensure data recovery.

This deployment workflow automates the release process, minimizes manual operations, and ensures that the platform can be updated efficiently whenever a new version is available.

> **Figure 4.2. Deployment Workflow of AI Learning Assistant Platform on AWS.**

![Figure 4.2](/images/4.2.d.x..png)

---

## 4.3 System Testing

After successful deployment, the platform was tested to evaluate its stability, functionality, and compatibility across all major components.

### Test Results

| Function | Test Description | Result |
|-----------|------------------|--------|
| User Authentication | Verify user login and authorization | Successful |
| Course Management | Create, update, and manage courses | Successful |
| Learning Material Upload | Upload learning materials to the platform | Successful |
| Knowledge Base | Process documents and generate vector embeddings | Successful |
| AI Chat (RAG) | Answer questions based on uploaded documents | Successful |
| Summary | Generate document summaries | Successful |
| Quiz | Generate quiz questions | Successful |
| Flashcard | Generate flashcards from learning materials | Successful |
| Docker Compose | Start and manage application containers | Successful |
| GitHub Actions | Build Docker images | Successful |
| Amazon ECR | Push and pull Docker images | Successful |
| Amazon CloudWatch | Collect logs and performance metrics | Successful |

The testing results demonstrate that all Docker containers operate reliably, the core platform features function correctly, and the Retrieval-Augmented Generation (RAG) pipeline accurately generates responses based on uploaded learning materials.

> **Figure 4.3. System Testing Results of AI Learning Assistant Platform.**

![Figure 4.3](/images/4.3.d.x.png)

---

## 4.4 Monitoring and Operations

During system operation, **Amazon CloudWatch** is used to monitor the performance and operational status of the platform. CloudWatch collects metrics and logs from Amazon EC2 and Docker containers, enabling continuous monitoring and early issue detection.

The monitored metrics include:

- CPU Utilization
- Memory Usage
- Disk Usage
- Network Traffic
- Docker Container Logs
- System Status Check

**CloudWatch Alarm** is configured to send notifications whenever predefined thresholds are exceeded. Alerts are delivered through **Amazon SNS**, allowing administrators to respond promptly and maintain system availability.

In addition, MongoDB, PostgreSQL, and learning materials are backed up regularly to **Amazon S3** to ensure data durability and disaster recovery. **AWS Budgets** is used to monitor AWS spending and generate alerts whenever resource usage exceeds the predefined budget.

### Monitoring Scope

| Component | Monitoring Scope |
|------------|------------------|
| Amazon EC2 | CPU, Memory, Disk, Network |
| Docker Containers | Container status and logs |
| MongoDB | Storage utilization and database connections |
| PostgreSQL | Query performance and storage utilization |
| MinIO | Object storage capacity |
| Amazon CloudWatch | Metrics, Logs, and Alarms |
| Amazon S3 | Backup status |
| AWS Budgets | AWS cost monitoring |

# Part 5. Security and Cost Optimization

## 5.1 System Security

AI Learning Assistant Platform stores user accounts, learning materials, Knowledge Base data, and conversation history. Therefore, multiple security measures are implemented to ensure the confidentiality, integrity, and availability of data when deploying the system on **Amazon Web Services (AWS)**.

The security measures implemented include:

- Using an **IAM User** instead of the Root User for system deployment and administration.
- Applying the **Least Privilege** principle through **AWS IAM**, granting only the minimum permissions required for each user and service.
- Enabling **Multi-Factor Authentication (MFA)** for AWS administrator accounts to strengthen account security.
- Configuring **Security Groups** to allow only the required service ports, including SSH (22), HTTP (80), and HTTPS (443).
- Using **HTTPS** to encrypt data transmitted between users and the system.
- Storing API keys and configuration information in **Environment Variables** rather than directly in the source code.
- Restricting MongoDB, PostgreSQL, and MinIO to the internal **Docker Network**, preventing direct access from the Internet.
- Limiting access to **Amazon S3**, allowing only authorized users and services to access backup data.
- Using **Amazon CloudWatch** and **CloudWatch Alarm** to monitor system status and detect operational issues at an early stage.
- Monitoring AWS resource usage through **AWS Budgets** to prevent unexpected cloud expenses.

These security measures enable the platform to satisfy the fundamental security requirements for AWS deployment while minimizing the risks of unauthorized access, data leakage, and data loss.

---

## 5.2 Estimated Deployment Cost

AI Learning Assistant Platform is deployed using a **Production Lite** architecture that focuses on minimizing operational costs while maintaining stable performance, scalability, and the requirements of the Minimum Viable Product (MVP).

### Table 5.1. Estimated Deployment Cost

| AWS Service | Purpose | Estimated Cost (USD/Month) |
|--------------|---------|---------------------------:|
| Amazon EC2 (t3.large) | Application Hosting | 60 |
| Amazon EBS (50 GB) | Persistent Storage | 4 |
| Amazon S3 | Backup Storage | 2 |
| Amazon ECR | Docker Image Registry | 1 |
| Amazon CloudWatch | Monitoring and Logging | 3 |
| Data Transfer | Internet Traffic | 8 |
| Google Gemini / OpenAI API | AI Processing | 15–50 |
| **Estimated Total** | | **93–128 USD/Month** |

### Cost Optimization Strategies

To reduce operational costs, the platform applies the following optimization strategies:

- Deploy all application services on a single **Amazon EC2** instance during the MVP stage.
- Monitor AWS resource usage using **AWS Budgets**.
- Store backup data on **Amazon S3** instead of maintaining multiple copies on the EC2 instance.
- Remove unused AWS resources after testing is completed.
- Optimize AI model requests to reduce token consumption and API costs.
- Scale to **Application Load Balancer (ALB)** and **Amazon ECS** only when the number of users increases.
---

# Part 6. Evaluation and Future Development

## 6.1 Evaluation Based on the AWS Well-Architected Framework

AI Learning Assistant Platform is evaluated based on the six pillars of the **AWS Well-Architected Framework** to ensure that the system meets the requirements for operational excellence, security, reliability, performance efficiency, cost optimization, and sustainability.

### Table 6.1. System Evaluation

| Pillar | Implementation |
|---------|----------------|
| Operational Excellence | Docker Compose, GitHub Actions, Amazon CloudWatch |
| Security | AWS IAM, Security Group, HTTPS, Environment Variables |
| Reliability | Amazon S3 Backup, Docker Restart Policy, CloudWatch Alarm |
| Performance Efficiency | PostgreSQL + pgvector, Retrieval-Augmented Generation (RAG) |
| Cost Optimization | Amazon EC2, AWS Budgets, Amazon CloudWatch |
| Sustainability | The architecture can be extended to Amazon ECS and Application Load Balancer |

The evaluation results indicate that AI Learning Assistant Platform satisfies the fundamental principles of the AWS Well-Architected Framework for a Generative AI application deployed on AWS. The current architecture is well suited for the Minimum Viable Product (MVP) stage while remaining scalable for future growth as user demand increases.

> **Figure 6.1. Evaluation of AI Learning Assistant Platform Based on the AWS Well-Architected Framework.**

![Figure 6.1](/images/6.1.p.r.png)

---

## 6.2 Future Development

In the future, the platform can be enhanced in the following directions:

- Deploy **Amazon ECS** or **Amazon EKS** to improve scalability and high availability.
- Implement **Application Load Balancer (ALB)** together with **Auto Scaling** to support a larger number of concurrent users.
- Expand the Knowledge Base to support additional subjects, faculties, and user groups.
- Integrate advanced AI models such as **Amazon Bedrock**, **Google Gemini**, or **OpenAI**.
- Develop additional AI-powered learning features, including AI Tutor, Mind Mapping, Speech-to-Text, and Text-to-Speech.
- Improve the monitoring, alerting, and backup mechanisms to enhance system reliability.
- Build a centralized monitoring dashboard using **Amazon CloudWatch Dashboard**.
- Strengthen system security by integrating **AWS WAF** and **AWS Shield** for Internet-facing deployments.

With the current architecture, AI Learning Assistant Platform effectively meets the requirements of the MVP stage and provides a solid foundation for future expansion as the system continues to grow.

---

# Part 7. Conclusion

## 7.1 Project Achievements

AI Learning Assistant Platform was developed to support learners in accessing and utilizing educational materials through Artificial Intelligence combined with **Retrieval-Augmented Generation (RAG)** technology. The platform enables users to upload documents, build a Knowledge Base, and interact with AI using natural language, thereby improving the accuracy of responses compared with traditional AI chatbots.

In addition to AI-powered question answering, the platform provides several learning support features, including document management, content summarization, quiz generation, flashcard creation, and conversation history management. The entire application is deployed on **Amazon Web Services (AWS)**, meeting essential requirements for performance, security, scalability, and system management.

Throughout the project, the following objectives were successfully achieved:

- Developed the AI Learning Assistant Platform based on FastGPT.
- Implemented Retrieval-Augmented Generation (RAG) to improve response accuracy.
- Deployed the application on Amazon EC2 using Docker Compose.
- Integrated MongoDB, PostgreSQL with pgvector, MinIO, and AWS services.
- Implemented a CI/CD pipeline using GitHub Actions and Amazon ECR.
- Established a monitoring system using Amazon CloudWatch.
- Implemented data backup using Amazon S3.
- Applied security best practices based on AWS recommendations.

---

## 7.2 Limitations

Although the project has achieved its primary objectives, several limitations remain:

- The current architecture relies on a single Amazon EC2 instance and does not yet support High Availability.
- Auto Scaling and Application Load Balancer have not been implemented.
- Multi-AZ deployment has not been configured for the database services.
- The quality of AI responses still depends on the quality and completeness of the uploaded learning materials.
- Mobile applications are not yet supported.
- Several advanced AI features are still under research and development.

---

## 7.3 Future Work

The AI Learning Assistant Platform will continue to be enhanced in the following directions:

- Deploy Amazon ECS or Amazon EKS to improve scalability and availability.
- Implement Application Load Balancer together with Auto Scaling to support higher user traffic.
- Integrate advanced AI models such as Amazon Bedrock, Google Gemini, and OpenAI.
- Expand AI-powered learning features, including AI Tutor, Mind Mapping, Speech-to-Text, and Text-to-Speech.
- Develop native mobile applications for Android and iOS.
- Optimize the Retrieval-Augmented Generation (RAG) pipeline to improve retrieval accuracy and response quality.
- Enhance backup and disaster recovery mechanisms.
- Strengthen monitoring and security based on AWS best practices.

These improvements will enable AI Learning Assistant Platform to evolve into a more comprehensive intelligent learning platform capable of serving a wider range of users and meeting the growing demands of modern education.

---

## 7.4 Conclusion

AI Learning Assistant Platform is an intelligent learning support solution built on the FastGPT platform and deployed on Amazon Web Services (AWS). By combining Retrieval-Augmented Generation (RAG) with a Knowledge Base, the system provides responses grounded in user-provided learning materials, improving learning efficiency while significantly reducing AI hallucinations.

The system architecture is designed with scalability and maintainability in mind, integrating Docker Compose, GitHub Actions, Amazon ECR, Amazon CloudWatch, and various AWS services to ensure reliable deployment, operation, and future expansion.

Beyond achieving the goal of building an intelligent learning assistant, this project also provided valuable hands-on experience in designing, deploying, monitoring, and operating a Generative AI application on Amazon Web Services. It establishes a solid foundation for future research and development of AI-powered educational systems.