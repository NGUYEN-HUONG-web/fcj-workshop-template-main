---
title: "5.1 Introduction"
date: 2026-08-09
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

## 5.1.1 Background

The rapid development of artificial intelligence, large language models, and cloud computing has created new opportunities in education. AI can support information retrieval, explain concepts, guide learners, generate review questions, and interact with users through natural language.

In practice, students and instructors work with textbooks, slides, laboratory guides, reference materials, and research papers. As the volume of material grows, locating a specific piece of information becomes time-consuming and reduces learning efficiency.

Conventional AI chatbots mainly rely on knowledge acquired during training. They do not automatically understand a user's private documents and can produce inaccurate or unsupported answers, a problem commonly known as **AI hallucination**.
## 5.1.2 Problem statement

The project addresses the following requirements:

- Centralize learning materials on one platform.
- Retrieve information by meaning instead of exact keyword matching.
- Generate answers grounded in user-provided documents.
- Reduce unsupported information and improve source traceability.
- Combine theory, question answering, practice, and progress tracking.
- Deploy the system on AWS at a cost appropriate for an internship project.

## 5.1.3 Proposed solution

The **AI Learning Assistant Platform** is an intelligent learning platform customized from FastGPT and built around **Retrieval-Augmented Generation (RAG)**.

When a user uploads a document, the system extracts its content, divides it into smaller chunks, creates vector embeddings, and builds a Knowledge Base. When the user asks a question, the system retrieves relevant chunks, adds them to the context, and sends the resulting prompt to a large language model to generate an answer.

Compared with a conventional chatbot, the solution offers three key differences:

1. Answers are grounded in the user's own documents.
2. Semantic Search finds relevant content even when a question does not contain the document's exact keywords.
3. A Knowledge Base can be reused across conversations and learning features.

Hình 5.1: Trang chính AI Learning Assistant sau khi đăng nhập.  

![Trang chính AI Learning Assistant sau khi đăng nhập](/images/hinh5.1-wshop.png)

## 5.1.4 Project objectives

### Functional objectives

- Manage AWS learning paths, subjects, and lesson content.
- Upload and manage learning documents.
- Build a Knowledge Base from uploaded documents.
- Provide Explain, Guide, and Exam Practice assistant modes.
- Support multi-turn conversations while preserving context.
- Summarize documents and generate review questions.
- Provide quizzes, flashcards, and learning-history tracking.
- Display references when supported by the selected workflow.

### Technical objectives

- Containerize the application with Docker and Docker Compose.
- Deploy the system on Amazon EC2.
- Store versioned container images in Amazon ECR.
- Automate image builds with GitHub Actions.
- Use MongoDB, PostgreSQL/pgvector, Redis, and MinIO for their designated roles.
- Back up essential data to Amazon S3.
- Monitor the system with CloudWatch, alarms, and SNS.
- Schedule EC2 start and stop operations with Lambda and EventBridge.
- Track expenditure with AWS Budgets.


![Hình5.1.1 Lộ trình ](/images/5.1.1.wrokshop.png)
![Hình5.1.2 Trợ lý AI ](/images/hinh5.1-wshop.png)
![Hình5.1.3 Trợ lý tài liệu (trợ lý bài học) ](/images/hinh5.1.3.wrokshop.png)
![Hình5.1.4 Bài luyện tập ](/images/hinh5.1.4.workshop.png)
![Hình5.1.5 Thẻ nhớ mặt trước ](/images/5.1.5.workshomt.png)
![Hình5.1.5 Thẻ nhớ mặt sau ](/images/hinh1.1.5bworkshop.png)
## 5.1.5 Project scope

### Functional scope

The workshop focuses on an MVP containing the essential learning functions: content management, RAG-based AI question answering, document reading, quizzes, flashcards, and activity history.

### Deployment scope

The system uses a **Production Lite** model on one Amazon EC2 instance. Application services run through Docker Compose; EBS provides persistent volumes; ECR stores container images; S3 stores backups; CloudWatch supplies monitoring; and Lambda with EventBridge supports operational automation.

### Current exclusions

- Multi-Availability-Zone high availability.
- Auto Scaling and large-scale container orchestration.
- Fully managed databases for every data component.
- Multi-Region disaster recovery.
- Advanced learning analytics and a complete instructor dashboard.

These capabilities are reserved for future development after the MVP stage.

## 5.1.6 Process overview

Learner flow:

```text
Sign in
   ↓
Select a learning path or subject
   ↓
Open a lesson or upload a document
   ↓
Ask the AI assistant a question
   ↓
Receive a Knowledge Base-grounded answer
   ↓
Review with quizzes and flashcards
   ↓
Track learning history
```

System operations flow:

```text
Source code → GitHub Actions → Amazon ECR → Amazon EC2

User → Nginx → AI Learning Assistant → Data and AI services

CloudWatch → Alarm → SNS

EventBridge → Lambda → Start/Stop EC2
```

![System workflow from the learner to the learning functions and AWS services](/images/5.1.6ws.png)

## 5.1.7 Solution value

For learners, the platform reduces time spent searching for information, provides contextual explanations, and combines study, question answering, and practice in a unified workflow.

For administrators, the container-based architecture clearly separates service responsibilities, while AWS provides deployment infrastructure, storage, monitoring, alerts, automation, and cost control.

The solution can later be adapted for schools, training centers, or enterprises that need an intelligent question-answering system grounded in internal documents.
