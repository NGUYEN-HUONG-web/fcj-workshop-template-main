---
title: "Week 4 Worklog"
date: 2026-07-18
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Week 4 Objectives:

* Deploy a production-ready WordPress architecture on AWS with High Availability (HA) and Scalability.
* Learn how to configure Auto Scaling Group (ASG), Application Load Balancer (ALB), and Amazon CloudFront.
* Understand the Server Migration process using VM Import/Export.
* Perform heterogeneous Database Migration using AWS Schema Conversion Tool (SCT) and AWS Database Migration Service (DMS).
* Explore advanced AWS migration services such as AWS Migration Hub, AWS Application Migration Service (MGN), and AWS DataSync.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - **WordPress on AWS – Part 1** <br>&emsp; + Prepare VPC, Public/Private Subnets, and Security Groups <br>&emsp; + Deploy Amazon RDS Multi-AZ <br>&emsp; + Launch EC2 and install WordPress <br>&emsp; + Connect WordPress to Amazon RDS | 09/29/2025 | 09/29/2025 | <https://000021.awsstudygroup.com/> |
| 3 | - **WordPress on AWS – Part 2** <br>&emsp; + Create AMI from the configured EC2 instance <br>&emsp; + Configure Launch Template and Auto Scaling Group <br>&emsp; + Deploy Application Load Balancer <br>&emsp; + Integrate Amazon CloudFront <br>&emsp; + Perform RDS Snapshot & Restore <br>&emsp; + Clean up AWS resources | 09/30/2025 | 09/30/2025 | <https://000021.awsstudygroup.com/> |
| 4 | - **Server Migration (VM Import/Export)** <br>&emsp; + Prepare an On-Premises virtual machine <br>&emsp; + Upload VM image to Amazon S3 <br>&emsp; + Import VM as AMI and launch EC2 <br>&emsp; + Export EC2 back to VM image <br>&emsp; + Configure IAM Roles and S3 permissions | 10/01/2025 | 10/01/2025 | <https://000014.awsstudygroup.com/> |
| 5 | - **Database Migration** <br>&emsp; + Prepare source and target databases <br>&emsp; + Convert schema using AWS SCT <br>&emsp; + Configure AWS DMS Replication Instance <br>&emsp; + Create Endpoints and Migration Task <br>&emsp; + Perform Full Load and Change Data Capture (CDC) <br>&emsp; + Explore AWS DMS Serverless | 10/02/2025 | 10/02/2025 | <https://000043.awsstudygroup.com/> |
| 6 | - **Migration Monitoring & Advanced Services** <br>&emsp; + Monitor DMS using Amazon CloudWatch <br>&emsp; + Analyze Task Logs and Table Statistics <br>&emsp; + Troubleshoot migration issues <br>&emsp; + Learn AWS Migration Hub, AWS MGN, AWS DataSync, and Container Migration to Amazon EKS | 10/03/2025 | 10/03/2025 | <https://000043.awsstudygroup.com/> |

### Week 4 Achievements:

* Successfully deployed a highly available WordPress architecture using:
  * Amazon EC2
  * Amazon RDS Multi-AZ
  * Application Load Balancer (ALB)
  * Auto Scaling Group (ASG)
  * Amazon CloudFront

* Understood how Auto Scaling automatically adjusts the number of EC2 instances based on application demand.

* Configured Application Load Balancer to distribute incoming traffic across healthy EC2 instances.

* Improved website performance by integrating Amazon CloudFront as a Content Delivery Network (CDN).

* Practiced backup and disaster recovery using Amazon RDS Snapshots and Restore.

* Gained hands-on experience with VM Import/Export by:
  * Importing an On-Premises virtual machine into AWS
  * Creating an AMI from the imported VM
  * Launching EC2 from the imported image
  * Exporting EC2 back to a portable VM image

* Learned how to configure IAM Roles and Amazon S3 permissions required for secure migration.

* Performed heterogeneous database migration using:
  * AWS Schema Conversion Tool (SCT)
  * AWS Database Migration Service (DMS)

* Configured:
  * Replication Instance
  * Source & Target Endpoints
  * Migration Tasks
  * Full Load + Change Data Capture (CDC)

* Explored AWS DMS Serverless and understood how it automatically scales migration resources.

* Learned to monitor migration progress using:
  * Amazon CloudWatch Metrics
  * Table Statistics
  * Task Logs

* Explored advanced AWS migration services including:
  * AWS Migration Hub
  * AWS Application Migration Service (MGN)
  * AWS DataSync
  * Container Migration to Amazon EKS