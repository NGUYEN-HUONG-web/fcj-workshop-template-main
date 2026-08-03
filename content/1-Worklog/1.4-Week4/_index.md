---
title: "Week 4 Worklog"
date: 2026-07-13
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives

* Build a High Availability WordPress architecture on AWS.
* Learn server and database migration strategies to AWS.
* Practice using AWS Schema Conversion Tool (AWS SCT) and AWS Database Migration Service (AWS DMS).
* Understand the differences between Full Load and Change Data Capture (CDC).
* Explore AWS DataSync, AWS Application Migration Service (MGN), and AWS Outposts.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| **2** | - Designed a High Availability architecture for WordPress.<br>- Identified the roles of Application Load Balancer, Auto Scaling Group, Amazon RDS Multi-AZ, Amazon S3, and Amazon CloudFront.<br>- Prepared the VPC, Public Subnets, Private Subnets, and Security Groups for deployment. | 13/07/2026 | 13/07/2026 | <https://000006.awsstudygroup.com/> |
| **3** | - Installed WordPress on Amazon EC2.<br>- Connected WordPress to Amazon RDS.<br>- Created a Launch Template, Target Group, and Application Load Balancer (ALB).<br>- Configured an Auto Scaling Group across two Availability Zones.<br>- Tested the fault tolerance of the architecture. | 14/07/2026 | 14/07/2026 | <https://000006.awsstudygroup.com/> |
| **4** | - Learned about VM Import/Export and supported virtual machine formats.<br>- Prepared an Amazon S3 Bucket and IAM Role for migration tasks.<br>- Studied the process of importing existing virtual machines and converting them into Amazon Machine Images (AMIs). | 15/07/2026 | 15/07/2026 | <https://docs.aws.amazon.com/vm-import/latest/userguide/what-is-vmimport.html> |
| **5** | - Installed AWS Schema Conversion Tool (AWS SCT).<br>- Assessed database schema compatibility.<br>- Created an AWS DMS Replication Instance, Source Endpoint, and Target Endpoint.<br>- Practiced Full Load and Change Data Capture (CDC) migrations. | 16/07/2026 | 16/07/2026 | <https://docs.aws.amazon.com/dms/> |
| **6** | - Explored AWS DataSync, AWS Application Migration Service (MGN), and AWS Outposts.<br>- Compared migration services based on different data types and workloads.<br>- Verified migrated data after the migration process.<br>- Reviewed and summarized the knowledge gained during Week 4. | 17/07/2026 | 17/07/2026 | <https://aws.amazon.com/cloud-data-migration/> |

### Achievements

* Designed a High Availability architecture for a WordPress application.
* Successfully deployed WordPress using Amazon EC2, Application Load Balancer, Auto Scaling Group, and Amazon RDS.
* Understood how Amazon CloudFront improves content delivery and reduces application load.
* Learned the VM Import/Export workflow for migrating virtual machines to AWS.
* Used AWS Schema Conversion Tool (AWS SCT) to assess and convert database schemas.
* Understood the roles of Replication Instances and Endpoints in AWS Database Migration Service (AWS DMS).
* Distinguished between Full Load and Change Data Capture (CDC) migration strategies.
* Understood the use cases of AWS DataSync, AWS Application Migration Service (MGN), and AWS Outposts.

### Challenges and Solutions

| Challenges | Solutions |
| --- | --- |
| WordPress could not connect to Amazon RDS. | Verified the database endpoint, login credentials, and Security Group rules for port 3306. |
| Targets behind the Application Load Balancer were marked as **Unhealthy**. | Checked the Health Check path, HTTP port configuration, and web server status. |
| AWS DMS Endpoint Test failed. | Verified the Route Table, Security Group configuration, database credentials, and IAM permissions. |
| Some database objects were not fully compatible after schema conversion. | Reviewed the AWS SCT Assessment Report and manually modified incompatible database objects. |

---

### Weekly Reflection

Week 4 allowed me to integrate my knowledge of compute, networking, databases, and load balancing into a complete cloud architecture. I realized that High Availability must be designed across both the application layer and the database layer to ensure reliability and fault tolerance.

The migration labs also demonstrated that migrating systems to AWS involves much more than simply copying data. A successful migration requires compatibility assessments, secure connectivity, data integrity validation, and careful planning to minimize downtime throughout the migration process.