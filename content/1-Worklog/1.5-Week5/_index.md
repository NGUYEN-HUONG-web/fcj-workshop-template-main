---
title: "Week 5 Worklog"
date: 2026-07-22
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives:

* Automate AWS operational tasks using AWS Lambda, Amazon EventBridge, and Slack notifications.
* Build advanced monitoring dashboards by integrating Grafana with Amazon CloudWatch.
* Learn resource governance through AWS Tags, Resource Groups, and Attribute-Based Access Control (ABAC).
* Explore AWS Systems Manager (SSM) for secure EC2 management without SSH.
* Understand Infrastructure as Code (IaC) by provisioning resources with AWS CloudFormation.

### Tasks to be carried out this week:

| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - **Operational Automation** <br>&emsp; + Create an AWS Lambda function (Python with boto3) to automatically start and stop EC2 instances on a schedule <br>&emsp; + Configure Amazon EventBridge to trigger Lambda functions <br>&emsp; + Integrate Slack Webhooks to receive automation notifications <br>&emsp; + Verify Lambda execution using Amazon CloudWatch Logs | 20/07/2026 | 20/07/2026 | <https://000022.awsstudygroup.com/> |
| 3 | - **Advanced Monitoring with Grafana** <br>&emsp; + Launch an Amazon EC2 instance and install Grafana Open Source <br>&emsp; + Configure Amazon CloudWatch as the monitoring data source <br>&emsp; + Build dashboards for CPU, Network, and Disk metrics <br>&emsp; + Customize dashboard panels to improve infrastructure observability | 21/07/2026 | 21/07/2026 | <https://000029.awsstudygroup.com/> |
| 4 | - **Resource Governance and IAM** <br>&emsp; + Apply standardized Tags such as Environment, Owner, and Cost Center <br>&emsp; + Create Resource Groups for easier resource management <br>&emsp; + Implement Attribute-Based Access Control (ABAC) using IAM policies <br>&emsp; + Restrict EC2 access based on matching resource tags | 22/07/2026 | 22/07/2026 | <https://000027.awsstudygroup.com/><br><https://000028.awsstudygroup.com/> |
| 5 | - **AWS Systems Manager** <br>&emsp; + Access EC2 instances securely with Session Manager instead of SSH <br>&emsp; + Configure Session Logs to Amazon S3 <br>&emsp; + Execute administrative commands across multiple EC2 instances using Run Command <br>&emsp; + Explore Patch Manager and compliance reporting | 23/07/2026 | 23/07/2026 | <https://000058.awsstudygroup.com/><br><https://000031.awsstudygroup.com/> |
| 6 | - **Infrastructure as Code (CloudFormation)** <br>&emsp; + Create CloudFormation templates using YAML or JSON <br>&emsp; + Provision Amazon VPC and EC2 resources using CloudFormation Stacks <br>&emsp; + Learn Parameters, Mappings, Resources, and Outputs <br>&emsp; + Perform Drift Detection to identify configuration changes | 24/07/2026 | 24/07/2026 | <https://000037.awsstudygroup.com/> |

### Week 5 Achievements:

* Successfully automated EC2 start and stop operations using AWS Lambda and Amazon EventBridge.
* Configured Slack notifications to receive real-time updates whenever automation tasks were executed.
* Reduced manual operational work through scheduled server management.

* Deployed Grafana on Amazon EC2 and integrated it with Amazon CloudWatch.
* Created interactive dashboards to monitor CPU utilization, network traffic, disk usage, and overall EC2 performance.
* Improved infrastructure visibility through customizable monitoring dashboards.

* Applied AWS Tags to organize resources by environment, ownership, and cost allocation.
* Created Resource Groups to simplify AWS resource management.
* Implemented Attribute-Based Access Control (ABAC) with IAM policies to manage EC2 access based on resource tags.

* Used AWS Systems Manager Session Manager to securely access EC2 instances without opening SSH ports.
* Configured session logging to Amazon S3 for auditing purposes.
* Executed remote administrative commands across multiple EC2 instances using Run Command.
* Learned how Patch Manager automates operating system updates and compliance checks.

* Developed reusable AWS CloudFormation templates for infrastructure deployment.
* Provisioned Amazon VPC and EC2 resources using CloudFormation Stacks.
* Understood the purpose of Parameters, Mappings, Resources, and Outputs in CloudFormation.
* Used Drift Detection to identify differences between deployed resources and CloudFormation templates.

### Week 5 Evaluation:

During Week 5, I strengthened my knowledge of AWS operations by learning how to automate routine administrative tasks with AWS Lambda and Amazon EventBridge. Integrating Slack notifications allowed me to monitor automated workflows more efficiently while reducing manual intervention.

I also gained practical experience deploying Grafana and connecting it with Amazon CloudWatch to create customized monitoring dashboards for AWS infrastructure. In addition, I learned best practices for organizing cloud resources with AWS Tags and Resource Groups, as well as implementing secure access control using the ABAC model in AWS IAM.

Finally, I explored AWS Systems Manager for secure server administration and gained hands-on experience with AWS CloudFormation. These activities improved my understanding of Infrastructure as Code and modern AWS operational practices for managing scalable and production-ready cloud environments.