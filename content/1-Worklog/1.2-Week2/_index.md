---
title: "Week 2 Worklog"
date: 2026-06-29
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Week 2 Objectives

* Learn and gain hands-on experience with Amazon S3, Amazon EC2, and Amazon RDS.
* Deploy a static website using Amazon S3.
* Launch Linux and Windows servers on Amazon EC2.
* Create a MySQL database using Amazon RDS.
* Understand High Availability architecture using Application Load Balancer and Auto Scaling Group.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| **2** | - Learned about Amazon S3, Buckets, Objects, Object Keys, and Storage Classes.<br>- Created an S3 Bucket and practiced uploading, downloading, copying, and deleting objects.<br>- Enabled S3 Versioning and restored previous object versions.<br>- Studied Cross-Region Replication (CRR). | 29/06/2026 | 29/06/2026 | <https://000057.awsstudygroup.com/> |
| **3** | - Configured S3 Static Website Hosting.<br>- Uploaded HTML, CSS, JavaScript, and image files.<br>- Configured a Bucket Policy to allow public website access.<br>- Learned about Amazon CloudFront and the role of Content Delivery Networks (CDNs) in content distribution. | 30/06/2026 | 30/06/2026 | <https://000057.awsstudygroup.com/> |
| **4** | - Studied Amazon Machine Images (AMIs), Instance Types, Key Pairs, Security Groups, and Amazon EBS.<br>- Launched Amazon Linux and Windows Server EC2 instances.<br>- Connected to the servers using SSH and Remote Desktop Protocol (RDP).<br>- Installed a LAMP stack on Linux and XAMPP on Windows.<br>- Deployed a sample website on EC2. | 01/07/2026 | 01/07/2026 | <https://000004.awsstudygroup.com/> |
| **5** | - Learned about Amazon RDS and its supported database engines.<br>- Created an Amazon RDS MySQL instance, a DB Subnet Group, and a Security Group.<br>- Connected an EC2 instance to RDS through port 3306.<br>- Explored Automated Backups, Snapshots, Read Replicas, and Multi-AZ deployments. | 02/07/2026 | 02/07/2026 | <https://000005.awsstudygroup.com/> |
| **6** | - Created a Launch Template based on the EC2 configuration.<br>- Created a Target Group and an Application Load Balancer (ALB).<br>- Deployed an Auto Scaling Group (ASG) across multiple Availability Zones.<br>- Verified Health Checks and traffic distribution.<br>- Tested Auto Scaling by modifying the Desired Capacity. | 03/07/2026 | 03/07/2026 | <https://000006.awsstudygroup.com/> |

### Achievements

* Successfully created and managed Amazon S3 Buckets.
* Deployed a static website using Amazon S3 Static Website Hosting.
* Understood S3 Versioning, Bucket Policies, and Cross-Region Replication.
* Successfully launched and connected to both Linux and Windows EC2 instances.
* Installed LAMP and XAMPP environments for application deployment.
* Created an Amazon RDS MySQL database and established connectivity from EC2.
* Understood the differences between RDS Snapshots, Automated Backups, Read Replicas, and Multi-AZ deployments.
* Built a High Availability architecture using an Application Load Balancer and an Auto Scaling Group across multiple Availability Zones.

### Challenges and Solutions

| Challenges | Solutions |
| --- | --- |
| The S3 website returned a `403 Forbidden` error. | Verified Block Public Access settings, Bucket Policy configuration, and the `s3:GetObject` permission. |
| Unable to connect to EC2 via SSH. | Checked the Key Pair, Public IPv4 address, Route Table, and Security Group inbound rule for port 22. |
| EC2 could not connect to the RDS database. | Verified the RDS endpoint and allowed the EC2 Security Group to access port 3306. |
| The Target Group showed an **Unhealthy** status. | Checked the Health Check path, application port, and EC2 Security Group configuration. |

---

### Weekly Reflection

During Week 2, I gained practical experience integrating storage, compute, and database services to deploy a complete application on AWS. Rather than learning each service independently, I developed a clearer understanding of how Amazon S3, Amazon EC2, and Amazon RDS work together within a cloud architecture.

Working with the Application Load Balancer and Auto Scaling Group also helped me understand the importance of High Availability. A production-ready system should not rely on a single server but should instead be distributed across multiple Availability Zones to improve fault tolerance, scalability, and overall reliability.