---
title: "Week 8 Worklog"
date: 2026-08-10
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives

* Complete and deploy the final project on AWS.
* Verify all system functions and end-to-end workflows.
* Configure monitoring, logging, and alerting.
* Review security settings and optimize AWS costs.
* Complete the Worklog, Proposal, Workshop, and internship report.
* Summarize the knowledge and skills gained throughout the internship.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| **2** | - Completed the remaining project features.<br>- Verified connectivity between the frontend, backend, database, and AWS services.<br>- Standardized environment variables and application configuration.<br>- Updated the system architecture diagram. | 10/08/2026 | 10/08/2026 | |
| **3** | - Deployed the final application using the CI/CD pipeline.<br>- Verified Docker images stored in Amazon ECR.<br>- Checked container status, service endpoints, and database connectivity.<br>- Performed functional testing after deployment. | 11/08/2026 | 11/08/2026 | <https://docs.github.com/actions> |
| **4** | - Configured Amazon CloudWatch Logs and Metrics.<br>- Created dashboards to monitor CPU, memory, network traffic, and application errors.<br>- Configured CloudWatch Alarms and Amazon SNS notifications.<br>- Analyzed logs to identify and resolve application issues. | 12/08/2026 | 12/08/2026 | <https://000008.awsstudygroup.com/> |
| **5** | - Used AWS Cost Explorer to analyze service costs.<br>- Reviewed IAM policies, Security Groups, and S3 Bucket Policies.<br>- Identified unused AWS resources.<br>- Optimized infrastructure by adjusting configurations and scheduling automatic start/stop operations. | 13/08/2026 | 13/08/2026 | <https://docs.aws.amazon.com/cost-management/> |
| **6** | - Completed the Worklog, Proposal, Blog, and Workshop documentation.<br>- Added screenshots, architecture diagrams, and code snippets.<br>- Removed unused AWS resources.<br>- Summarized the knowledge, technical skills, and practical experience gained throughout the eight-week internship. | 14/08/2026 | 14/08/2026 | |

### Achievements

#### Final Project Completion

* Successfully completed and deployed the final project on AWS.
* Verified the communication flow between all system components.
* Used Docker and a CI/CD pipeline to standardize the deployment process.
* Updated the system architecture and deployment documentation.

#### Monitoring and Operations

* Collected application metrics and logs using Amazon CloudWatch.
* Built centralized dashboards to monitor system health.
* Configured CloudWatch Alarms with Amazon SNS notifications.
* Used log analysis to identify and troubleshoot application issues.

#### Security and Cost Optimization

* Reviewed IAM policies based on the Principle of Least Privilege.
* Audited Security Group rules and removed unnecessary open ports.
* Verified S3 Public Access settings and Bucket Policies.
* Used AWS Cost Explorer to identify services generating costs.
* Stopped or deleted unused AWS resources.
* Applied automated start/stop schedules for Amazon EC2 and Amazon RDS when appropriate.

#### Documentation Completion

* Completed the Worklog covering all eight internship weeks.
* Finalized the project Proposal and Workshop documentation.
* Added screenshots, architecture diagrams, and code snippets.
* Summarized the knowledge gained and conducted a self-evaluation of the internship experience.

### Challenges and Solutions

| Challenges | Solutions |
| --- | --- |
| The newly deployed application did not function correctly. | Verified the Docker image tag, environment variables, service endpoints, and CloudWatch Logs to identify the root cause. |
| AWS costs continued to increase after completing hands-on labs. | Used AWS Cost Explorer to review costs by service and Region, then stopped or removed unnecessary running resources. |
| Security Groups allowed overly broad network access. | Restricted inbound rules to only the required ports and trusted source IP addresses. |
| Documentation lacked consistency or supporting images. | Reviewed each deployment step and added screenshots, explanations, and updated architecture diagrams. |

---

### Weekly Reflection

During the final week of the internship, I applied the knowledge gained throughout the program to complete, deploy, and operate a cloud-based application on AWS. This experience strengthened my understanding of how Compute, Storage, Database, Networking, Security, Container, and Monitoring services work together to support a production-ready system.

I realized that successfully deploying an application is only the first step. A reliable cloud solution must also be continuously monitored, secured with appropriate access controls, and regularly optimized for cost efficiency. My experience with an Amazon RDS instance that continued running unexpectedly reinforced the importance of responsible cloud resource management and proactive cost monitoring.

After eight weeks of internship training, I significantly strengthened my AWS knowledge and improved my practical skills in infrastructure deployment, containerization, CI/CD automation, cloud monitoring, and troubleshooting. This internship has provided a solid foundation for my future career in Cloud Computing, DevOps, and AWS application development.