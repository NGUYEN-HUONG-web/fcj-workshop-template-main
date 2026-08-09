---
title: "Self-Assessment"
date: 2026-08-09
weight: 6
chapter: false
pre: "<b>6. </b>"
---


During the **First Cloud AI Journey – AWS Workforce Bootcamp**, I strengthened my cloud computing knowledge, learned how to build a Retrieval-Augmented Generation (RAG) application, and applied what I learned to the project **“Deploying the Kotaemon RAG Chat System on AWS.”**

Through worklogs, blog posts, technical events, and group project activities, I gradually developed a more structured approach to learning and completing technical tasks.

In addition to deploying the application, I considered several important operational requirements:

- Data persistence.
- Access control.
- Data backup and recovery.
- Resource monitoring.
- Cost control.
- Protection of sensitive information.
- Clear presentation of technical evidence.

The following sections provide an objective assessment of my performance during the program.

## 1. Knowledge and Skills Gained

### 1.1 Technical Knowledge

After completing the learning activities and project implementation, I gained knowledge in the following areas:

- Understanding standard Hybrid RAG, including document chunking, embedding generation, hybrid retrieval, and citation-based answer generation.
- Distinguishing the roles of the **Kotaemon application/framework**, **Gemini chat model**, and **Gemini embedding model**.
- Understanding how Amazon EC2 provides the server environment for the application.
- Understanding how Amazon EBS provides persistent storage for EC2.
- Understanding how Amazon S3 stores backup data.
- Understanding how IAM roles grant AWS permissions to EC2 instances.
- Understanding how Security Groups control network traffic.
- Using Amazon CloudWatch to monitor EC2 metrics.
- Using AWS Budgets to help control project costs.
- Understanding how multiple AWS services work together in a demonstration architecture.
- Recognizing the difference between a **demo-ready MVP** and a **production-ready system**.
- Understanding the importance of HTTPS, secret management, logging, backups, and scalability.

### 1.2 Hands-on Skills

During project implementation, I practiced the following skills:

- Using Git to manage and synchronize source code.
- Using Docker to package and run the application.
- Using PowerShell on Windows.
- Using Ubuntu Bash on an EC2 instance.
- Building a Docker image for Kotaemon.
- Starting and managing Docker containers.
- Mapping ports to make the application externally accessible.
- Checking container status and logs.
- Using a bind mount on the root EBS volume.
- Separating application data from the container lifecycle.
- Backing up application data to Amazon S3.
- Using an IAM role instead of long-term access keys on EC2.
- Monitoring EC2 metrics with Amazon CloudWatch.
- Configuring AWS Budgets to monitor costs.
- Writing Hugo documentation in Vietnamese and English.
- Presenting deployment procedures as clear, sequential steps.
- Checking documentation errors with Hugo build.
- Collecting screenshots and command output as technical evidence.

### 1.3 Professional Skills

In addition to technical knowledge, I improved the following professional skills:

- Researching documentation independently when encountering new problems.
- Comparing multiple sources before reaching a conclusion.
- Troubleshooting one system layer at a time instead of changing several components simultaneously.
- Collaborating with other team members.
- Sharing progress and aligning on common project content.
- Writing reports with a clearer structure.
- Presenting architecture and explaining technical decisions.
- Paying closer attention to schedules and project progress.
- Handling API keys and AWS information more carefully.
- Reviewing screenshots before sharing them.
- Receiving feedback and revising my work accordingly.

## 2. Self-Assessment Table

| No. | Criteria | Comments | Good | Fair | Average |
|:---:|---|---|:---:|:---:|:---:|
| 1 | **AWS and RAG knowledge** | I understand and can apply the main components, but I need to learn more about high-availability architecture and advanced security. | ☐ | ✅ | ☐ |
| 2 | **Ability to learn** | I can independently read documentation, experiment, and adjust when working with new technologies. | ✅ | ☐ | ☐ |
| 3 | **Sense of responsibility** | I completed assigned tasks and paid attention to the accuracy of the report. | ✅ | ☐ | ☐ |
| 4 | **Proactiveness** | I proactively investigated problems and proposed solutions, although I occasionally needed more time to identify the best option. | ✅ | ☐ | ☐ |
| 5 | **Teamwork** | I coordinated with team members, shared information, and helped complete the team’s shared content. | ✅ | ☐ | ☐ |
| 6 | **Communication and presentation** | I improved my ability to explain technical topics but still need to be more concise and confident during presentations. | ☐ | ✅ | ☐ |
| 7 | **Problem-solving** | I learned to troubleshoot system layers and use evidence, but I need more experience with complex incidents. | ✅ | ☐ | ☐ |
| 8 | **Time management** | I tracked progress through worklogs but need to allocate time for testing and collecting evidence earlier. | ☐ | ✅ | ☐ |
| 9 | **Overall completion** | I completed a demo-ready MVP and workshop documentation, although several items still require further validation. | ✅ | ☐ | ☐ |

## 3. Strengths

### 3.1 Ability to Learn

I can independently research new technologies and apply what I learn to practical problems.

When I encounter an unfamiliar topic, I try to:

- Consult official documentation.
- Compare multiple sources.
- Test one step at a time.
- Record the results.
- Adjust the solution when necessary.

### 3.2 Sense of Responsibility

I make an effort to complete assigned tasks and take responsibility for the quality of my work.

When preparing documentation, I check:

- Content accuracy.
- Markdown structure.
- Image paths.
- Hugo build errors.
- Sensitive information in screenshots.
- Consistency between Vietnamese and English versions.

### 3.3 Proactiveness

When deployment problems occur, I investigate the cause instead of waiting for instructions.

My troubleshooting process includes checking:

- EC2 instance status.
- Network connectivity.
- Security Group rules.
- Docker containers.
- Service ports.
- Application logs.
- IAM permissions.
- Data status.
- Access to Amazon S3.

### 3.4 Teamwork

I can coordinate with team members, share progress, and help complete shared project content.

I listen to feedback, communicate problems, and adjust my assigned work to support the team’s common goals.

## 4. Areas for Improvement

### 4.1 Cloud and DevOps Knowledge

I need to deepen my knowledge in the following areas:

- HTTPS and TLS certificates.
- Domain management.
- Secret management.
- Centralized logging.
- Deployment automation.
- Automated backups.
- Monitoring and alerting.
- High availability.
- Auto Scaling.
- Load Balancers.
- Scalable architecture.

### 4.2 RAG Quality Evaluation

My current evaluation process still relies mainly on a small number of manually tested questions.

I need to develop a quantitative evaluation method that includes:

- A test question dataset.
- Expected answers.
- Retrieval accuracy.
- Relevance.
- Citation accuracy.
- Faithfulness to source documents.
- Unsupported-answer rate.
- Response time.

### 4.3 Data Testing

I need to complete persistence and restore testing with clear evidence.

The testing process should demonstrate:

1. Data status before stopping the container.
2. Data location on EBS.
3. Data status after restarting the container.
4. Backup results in Amazon S3.
5. Restore results from the backup.
6. A comparison of data before and after restoration.

### 4.4 Time Management

I need to improve my ability to estimate how long tasks will take.

In future projects, I will allocate dedicated time for:

- Research.
- Implementation.
- Testing.
- Troubleshooting.
- Evidence collection.
- Documentation.
- Content review.
- Presentation preparation.

### 4.5 Communication and Presentation

I need to communicate more concisely, clearly, and confidently.

When I encounter an issue, I should proactively:

- Report the problem early.
- Provide relevant logs or evidence.
- Explain the checks already performed.
- State the expected result.
- Propose possible solutions.
- Ask for support when necessary.

### 4.6 Information Security

I need to continue developing secure habits when working with cloud systems.

Before sharing content, I should review and redact:

- AWS account IDs.
- API keys.
- Access Key IDs.
- Secret Access Keys.
- Session tokens.
- Internal IP addresses or domains.
- Login information.
- Personal data.
- Sensitive information in logs.

If an API key is exposed, I should deactivate it and generate a new key instead of continuing to use it.

## 5. Improvement Plan

In the next stage, I plan to:

1. Study AWS security practices in greater depth.
2. Learn how to use AWS Secrets Manager and Systems Manager Parameter Store.
3. Configure HTTPS for the application.
4. Complete the backup and restore process.
5. Build a test suite for the RAG system.
6. Evaluate retrieval and generation quality.
7. Improve logging and monitoring.
8. Learn Infrastructure as Code.
9. Practice deployment automation.
10. Improve my presentation skills.
11. Communicate problems earlier.
12. Continue recording progress through worklogs.

## 6. Self-Assessment Conclusion

I believe I made clear progress in my AWS knowledge, deployment skills, and approach to system operations.

The most important outcome was not only completing a working demonstration but also understanding the limitations of the current architecture and identifying an appropriate improvement roadmap.

Through this project, I learned that a functioning RAG system is not necessarily production-ready. A production-ready system also requires security, monitoring, backups, testing, scalability, and well-defined operational procedures.

I plan to continue developing my knowledge in:

- Cloud security.
- Automation.
- System monitoring.
- RAG quality evaluation.
- Software testing.
- Scalable architecture.
- Communication and teamwork.

The **First Cloud AI Journey – AWS Workforce Bootcamp** helped me connect theoretical knowledge with real implementation experience. This experience provides an important foundation for continuing to develop my cloud, AI, and DevOps skills.

> I will continue learning, proactively address my areas for improvement, and work toward building AI systems that are secure, reliable, and valuable in real-world applications.