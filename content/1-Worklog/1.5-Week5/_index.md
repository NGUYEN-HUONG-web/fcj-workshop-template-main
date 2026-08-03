---
title: "Week 5 Worklog"
date: 2026-07-20
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Week 5 Objectives

* Understand the concept of Infrastructure as Code (IaC) and the benefits of infrastructure automation.
* Learn the structure of AWS CloudFormation templates.
* Deploy AWS infrastructure using YAML templates.
* Practice updating CloudFormation stacks with Change Sets.
* Automate the start and stop of AWS resources to optimize cloud costs.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| **2** | - Learned the fundamentals of Infrastructure as Code (IaC) and declarative configuration.<br>- Compared manual infrastructure deployment with AWS CloudFormation.<br>- Became familiar with YAML and JSON syntax.<br>- Studied the lifecycle of an AWS CloudFormation Stack. | 20/07/2026 | 20/07/2026 | <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html> |
| **3** | - Learned the purpose of Parameters, Resources, Outputs, Mappings, and Conditions in CloudFormation templates.<br>- Wrote a template to provision a VPC, Public Subnet, Internet Gateway, and Route Table.<br>- Validated the template syntax and verified resource dependencies. | 21/07/2026 | 21/07/2026 | <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html> |
| **4** | - Added a Security Group, IAM Role, and EC2 instance to the template.<br>- Used User Data to automatically install and configure a web server.<br>- Validated the template using the AWS CLI.<br>- Deployed the stack and monitored Stack Events during provisioning. | 22/07/2026 | 22/07/2026 | <https://docs.aws.amazon.com/cli/latest/reference/cloudformation/> |
| **5** | - Created a Change Set to preview infrastructure updates.<br>- Modified the EC2 Instance Type and Security Group configuration.<br>- Explored Stack Rollback, Drift Detection, and Nested Stacks.<br>- Verified the deployed resources after the update. | 23/07/2026 | 23/07/2026 | <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks.html> |
| **6** | - Developed an AWS Lambda function to automatically start and stop Amazon RDS or EC2 instances.<br>- Created an Amazon EventBridge schedule to trigger the Lambda function.<br>- Verified execution results using Amazon CloudWatch Logs.<br>- Deleted the CloudFormation Stack and cleaned up AWS resources after completing the lab. | 24/07/2026 | 24/07/2026 | <https://docs.aws.amazon.com/eventbridge/> |

### Achievements

* Understood the advantages of Infrastructure as Code (IaC) for infrastructure management.
* Successfully wrote AWS CloudFormation templates using YAML.
* Automated the deployment of a VPC, Subnet, Route Table, Security Group, and EC2 instance.
* Used Parameters and Outputs to improve template flexibility and reusability.
* Configured EC2 instances automatically with User Data during deployment.
* Learned how to monitor Stack Events and troubleshoot Stack Rollback issues.
* Used Change Sets to preview infrastructure changes before deployment.
* Automated the start and stop of AWS resources using Amazon EventBridge and AWS Lambda.

### Challenges and Solutions

| Challenges | Solutions |
| --- | --- |
| CloudFormation template contained YAML syntax errors. | Checked indentation, spacing, and validated the template using the `validate-template` command. |
| The CloudFormation Stack entered the **ROLLBACK** state. | Reviewed the Stack Events to identify the first resource that failed during deployment. |
| Dependent resources were not created in the correct order. | Used `Ref`, `GetAtt`, and `DependsOn` to define resource relationships and dependencies. |
| The Lambda function did not have permission to start or stop AWS resources. | Attached the appropriate IAM policy to the Lambda execution role. |

---

### Weekly Reflection

Week 5 helped me understand how infrastructure can be managed in the same way as application source code. AWS CloudFormation enables consistent, repeatable deployments while reducing configuration errors caused by manual provisioning.

I also implemented an automated solution using Amazon EventBridge and AWS Lambda to start and stop AWS resources outside working hours, helping reduce unnecessary cloud costs. This exercise was especially valuable after learning from my previous experience that leaving an Amazon RDS instance running unintentionally could continuously increase AWS expenses.