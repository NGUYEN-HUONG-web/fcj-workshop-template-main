---
title: "Week 3 Worklog"
date: 2026-07-06
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Week 3 Objectives

* Implement monitoring and observability using Amazon CloudWatch.
* Configure CloudWatch Metrics, Logs, Alarms, and Dashboards.
* Learn about Hybrid DNS using Amazon Route 53 Resolver and Microsoft Active Directory.
* Practice AWS resource management using the AWS CLI.
* Write basic commands and scripts to automate cloud administration tasks.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| **2** | - Studied CloudWatch Metrics, Logs, and Namespaces.<br>- Monitored EC2 metrics including CPUUtilization, NetworkIn, NetworkOut, and StatusCheckFailed.<br>- Reviewed RDS metrics such as DatabaseConnections and FreeStorageSpace.<br>- Practiced querying logs using CloudWatch Logs Insights. | 06/07/2026 | 06/07/2026 | <https://000008.awsstudygroup.com/> |
| **3** | - Created CloudWatch Alarms for EC2 CPU utilization.<br>- Created an Amazon SNS Topic and Email Subscription.<br>- Configured email notifications when metrics exceeded defined thresholds.<br>- Built a CloudWatch Dashboard to monitor EC2 and RDS metrics in one place. | 07/07/2026 | 07/07/2026 | <https://000008.awsstudygroup.com/> |
| **4** | - Learned the fundamentals of DNS and Hybrid DNS architecture.<br>- Deployed Microsoft Active Directory and a Remote Desktop Gateway.<br>- Created a Route 53 Private Hosted Zone.<br>- Tested domain name resolution within the VPC. | 08/07/2026 | 08/07/2026 | <https://000010.awsstudygroup.com/> |
| **5** | - Created Route 53 Resolver Inbound and Outbound Endpoints.<br>- Configured Resolver Rules and associated them with the VPC.<br>- Verified DNS resolution between AWS resources and external systems in both directions. | 09/07/2026 | 09/07/2026 | <https://000010.awsstudygroup.com/> |
| **6** | - Installed and configured the AWS CLI.<br>- Verified AWS identity using `aws sts get-caller-identity`.<br>- Practiced AWS CLI commands for managing Amazon S3, IAM, EC2, and VPC resources.<br>- Wrote basic scripts to check, start, and stop EC2 instances.<br>- Reviewed and summarized the knowledge gained during Week 3. | 10/07/2026 | 10/07/2026 | <https://000011.awsstudygroup.com/> |

### Achievements

* Successfully monitored the operational metrics of Amazon EC2 and Amazon RDS.
* Created CloudWatch Alarms and received notifications through Amazon SNS.
* Built a centralized CloudWatch Dashboard for monitoring AWS resources.
* Used CloudWatch Logs Insights to query and analyze log data.
* Understood the role of Route 53 Resolver in a Hybrid DNS architecture.
* Distinguished between Resolver Inbound Endpoints and Outbound Endpoints.
* Installed and configured the AWS CLI for resource management.
* Wrote basic AWS CLI commands and scripts to monitor and manage EC2 and Amazon S3 resources.

### Challenges and Solutions

| Challenges | Solutions |
| --- | --- |
| CloudWatch Alarm remained in the `INSUFFICIENT_DATA` state. | Waited for sufficient monitoring data to be collected and verified the Alarm Period and Evaluation Period settings. |
| Amazon SNS email notifications were not received. | Confirmed the email subscription and checked the Spam/Junk folder. |
| Route 53 Resolver failed to resolve domain names. | Verified the Security Group rules, Resolver Rules, DNS server IP addresses, and VPC associations. |
| AWS CLI returned the `Unable to locate credentials` error. | Ran `aws configure` and verified the AWS Access Key, Secret Access Key, and default Region settings. |

---

### Weekly Reflection

Week 3 helped me understand the importance of monitoring and observability in cloud operations. Amazon CloudWatch not only provides real-time metrics but also enables proactive monitoring through alarms, centralized dashboards, and log analysis.

Hybrid DNS was the most challenging topic this week because it required integrating Microsoft Active Directory, Route 53 Resolver, and VPC networking. Meanwhile, the AWS CLI significantly improved the efficiency of repetitive administrative tasks, although it also emphasized the importance of proper IAM permissions and secure credential management.