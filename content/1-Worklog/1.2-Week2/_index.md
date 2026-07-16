---
title: "Week 2 Worklog"
date: 2026-06-26
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Week 2 Objectives:

* Develop practical skills in using AWS Cloud9 IDE and AWS CLI to manage AWS resources efficiently.
* Learn how to deploy and administer relational databases using Amazon RDS, including backup and recovery strategies.
* Understand High Availability and Scalability architectures by implementing Launch Templates, Application Load Balancer (ALB), and Auto Scaling Groups (ASG).


### Tasks to be carried out this week:
| Day | Task                                                                                                                                                                                                   | Start Date | Completion Date | Reference Material                        |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------- | --------------- | ----------------------------------------- |
| 2   | - Created an AWS Cloud9 development environment.<br>- Explored the Cloud9 interface and integrated terminal.<br>- Practiced Linux command-line operations and basic file management.<br>- Used AWS CLI to interact with AWS services and verified resource management through the command line.<br>- Cleaned up unused resources after completing the lab.                                                                                                   | 29/06/2026 | 29/06/2026      |<https://000049.awsstudygroup.com/>|
| 3   | - Explored Amazon S3 object storage services.<br>- Created and managed S3 buckets.<br>- Configured Static Website Hosting on Amazon S3.<br>- Managed Public Access Block settings and Bucket Policies.<br>- Improved website performance by integrating Amazon CloudFront.<br>- Enabled S3 Versioning and practiced Cross-Region Replication (CRR) for data protection.                                              | 30/06/2026 | 30/06/2026      | <https://000057.awsstudygroup.com/> |
| 4   | - Prepared the networking environment for Amazon RDS:<br>&emsp;+ Configured VPC.<br>&emsp;+ Configured Security Groups.<br>&emsp;+ Created a DB Subnet Group.<br>- Launched an EC2 instance for the application.<br>- Provisioned an Amazon RDS database instance.<br>- Connected the application running on EC2 to Amazon RDS.<br>- Performed database backup and restoration using snapshots and recovery features. | 01/07/2026 | 01/07/2026      | <https://000005.awsstudygroup.com/> |
| 5   | - Built a High Availability architecture.<br>- Prepared infrastructure components including EC2, RDS, and the web application.<br>- Created a Launch Template for standardized EC2 deployment.<br>- Configured an Application Load Balancer (ALB):<br>&emsp;+ Created Target Groups.<br>&emsp;+ Configured Listener Rules.<br>- Verified traffic distribution across multiple EC2 instances.                            | 02/07/2026 | 02/07/2026      |<https://000006.awsstudygroup.com/> |
| 6   | - Created an Auto Scaling Group (ASG) integrated with the Application Load Balancer.<br>- Tested multiple scaling strategies:<br>&emsp;+ Manual Scaling.<br>&emsp;+ Scheduled Scaling.<br>&emsp;+ Dynamic Scaling based on CloudWatch metrics.<br>&emsp;+ Predictive Scaling.<br>- Removed all deployed AWS resources after completing the practice environment.                                                                                     | 03/07/2026 | 03/07/2026      | < <https://000006.awsstudygroup.com/> |

---

### Week 2 Achievements:

#### AWS Cloud9 & AWS CLI

* Successfully configured AWS Cloud9 as a cloud-based development environment.
* Improved proficiency in using AWS CLI to manage AWS resources without relying solely on the AWS Management Console.
* Practiced creating, modifying, and deleting AWS resources through command-line operations.
* Gained experience working with Linux commands and scripting within Cloud9.

#### Storage & Content Delivery

* Successfully deployed a static website using Amazon S3.
* Configured Bucket Policies and Public Access settings to securely publish web content.
* Integrated Amazon CloudFront to improve global content delivery performance.
* Enabled S3 Versioning to protect object data from accidental deletion or modification.
* Implemented Cross-Region Replication (CRR) to improve data durability and disaster recovery capabilities.

#### Database Administration

* Successfully provisioned and configured an Amazon RDS database instance.
* Connected a web application hosted on Amazon EC2 to Amazon RDS.
* Practiced database administration tasks, including:
  * Database Snapshots
  * Backup Management
  * Point-in-Time Recovery (PITR)

* Configured Security Groups and DB Subnet Groups to provide secure database connectivity.

#### High Availability & Auto Scaling

* Designed and implemented a highly available web architecture using:
  * Launch Templates
  * Application Load Balancer (ALB)
  * Auto Scaling Groups (ASG)

* Configured multiple Auto Scaling strategies, including:
  * Manual Scaling
  * Scheduled Scaling
  * Dynamic Scaling
  * Predictive Scaling

* Verified load balancing behavior and application availability during scaling events.
* Developed a better understanding of AWS best practices for building scalable and fault-tolerant cloud applications.

---

### Weekly Reflection

During the second week of the internship, I expanded my practical knowledge of AWS by working with development tools, storage services, relational databases, and scalable cloud architectures. Using AWS Cloud9 and AWS CLI significantly improved my efficiency in managing cloud resources, while Amazon S3 and CloudFront provided valuable experience in hosting and delivering web content securely.

The hands-on deployment of Amazon RDS helped me understand managed database services and database recovery strategies. In addition, implementing Application Load Balancer and Auto Scaling Group gave me practical insight into designing highly available and scalable cloud systems. These activities strengthened both my technical skills and my understanding of AWS architectural best practices, preparing me for more advanced cloud solutions in the following weeks.
