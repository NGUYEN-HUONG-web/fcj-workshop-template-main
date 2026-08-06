---
title: "Week 8 Worklog"
date: 2026-08-10
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Week 8 Objectives

* Complete and deploy the final project on AWS.
* Verify all system functionalities and end-to-end workflows.
* Configure Monitoring, Logging, and Alerting.
* Review security settings and optimize AWS costs.
* Complete the Worklog, Proposal, Workshop documentation, and Internship Report.
* Summarize the knowledge and experience gained throughout the internship.

### Tasks Performed This Week

| Day | Tasks | Start Date | Completion Date | References |
| --- | --- | --- | --- | --- |
| **Monday** | - Complete the remaining project features.<br>- Verify connectivity between the Frontend, Backend, Database, and AWS services.<br>- Standardize environment variables and configuration settings.<br>- Update the system architecture diagram. | 10/08/2026 | 10/08/2026 | |
| **Tuesday** | - Deploy the final application using a CI/CD pipeline.<br>- Verify Docker images stored in Amazon ECR.<br>- Check container status, application endpoints, and database connectivity.<br>- Perform functional testing after deployment. | 11/08/2026 | 11/08/2026 | <https://docs.github.com/actions> |
| **Wednesday** | - Configure Amazon CloudWatch Logs and Metrics.<br>- Create dashboards to monitor CPU, memory, network traffic, and application errors.<br>- Configure CloudWatch Alarms with Amazon SNS notifications.<br>- Analyze logs to identify and resolve application issues. | 12/08/2026 | 12/08/2026 | <https://000008.awsstudygroup.com/> |
| **Thursday** | - Use AWS Cost Explorer to analyze service costs.<br>- Review IAM policies, Security Groups, and Amazon S3 Bucket Policies.<br>- Identify unused AWS resources.<br>- Optimize costs by adjusting configurations and scheduling automatic Start/Stop operations. | 13/08/2026 | 13/08/2026 | <https://docs.aws.amazon.com/cost-management/> |
| **Friday** | - Finalize the Worklog, Proposal, Blog, and Workshop documentation.<br>- Add screenshots, architecture diagrams, and code snippets.<br>- Clean up unused AWS resources.<br>- Summarize the knowledge, skills, and experience gained during the eight-week internship. | 14/08/2026 | 14/08/2026 | |

### Achievements

#### Project Completion

* Successfully completed and deployed the final project on AWS.
* Verified the end-to-end communication between all system components.
* Standardized the deployment process using Docker and a CI/CD pipeline.
* Updated the system architecture diagram and deployment documentation.

#### Monitoring and Operations

* Collected application metrics and logs using Amazon CloudWatch.
* Built monitoring dashboards to visualize system health.
* Configured CloudWatch Alarms with Amazon SNS notifications.
* Used log analysis to troubleshoot and resolve application issues.

#### Security and Cost Optimization

* Reviewed IAM policies following the Principle of Least Privilege.
* Audited open ports in Security Groups.
* Verified Amazon S3 Public Access settings and Bucket Policies.
* Used AWS Cost Explorer to identify cost-generating services.
* Stopped or removed unused AWS resources.
* Applied automated Start/Stop schedules for Amazon EC2 and Amazon RDS when appropriate.

#### Documentation Completion

* Completed the eight-week internship Worklog.
* Finalized the project Proposal and Workshop documentation.
* Added screenshots, architecture diagrams, and code snippets.
* Summarized the knowledge gained and evaluated the overall internship experience.

### Challenges and Solutions

| Challenges | Solutions |
| --- | --- |
| The newly deployed application did not function correctly. | Verified Docker image tags, environment variables, application endpoints, and CloudWatch Logs to identify and resolve deployment issues. |
| AWS costs continued to increase after completing the workshops. | Used AWS Cost Explorer to analyze costs by service and Region, then stopped or deleted unnecessary running resources. |
| Security Groups contained overly permissive inbound rules. | Restricted access to only the required ports and limited traffic sources based on the principle of least privilege. |
| Documentation lacked consistency and sufficient screenshots. | Reviewed each deployment step, added screenshots, improved annotations, and updated architecture diagrams. |

---

### Weekly Reflection

During the final week of my internship, I applied the knowledge and skills acquired throughout the program to complete, deploy, and operate a cloud-based application on AWS. This experience strengthened my understanding of how AWS services—including Compute, Storage, Database, Networking, Security, Containers, and Monitoring—work together to support a production-ready system.

I realized that successfully deploying an application is only the first step. A reliable cloud solution also requires continuous monitoring, proper security practices, regular maintenance, and ongoing cost optimization. The unexpected AWS charges caused by an unattended Amazon RDS instance provided a valuable real-world lesson about responsible cloud resource management.

After completing the eight-week internship, I significantly improved my AWS knowledge, cloud infrastructure deployment skills, containerization experience, CI/CD implementation, and troubleshooting capabilities. These experiences have established a strong foundation for pursuing a career in Cloud Computing, DevOps, and AWS-based application development.