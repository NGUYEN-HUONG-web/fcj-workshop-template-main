---
title: "5.9. Automation and Cost Optimization"
date: 2026-08-09
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

## Scheduled EC2 operations

Create separate Lambda functions or one parameterized function for EC2 start and stop operations. Grant the execution role only the required EC2 permissions for the target instance.

EventBridge Scheduler invokes the functions at defined times:

```text
EventBridge schedule → Lambda → EC2 StartInstances/StopInstances
```

Set the correct time zone, configure retries, and test each function manually before enabling the schedule. Remember that stopping EC2 does not remove EBS, Elastic IP, S3, or other continuing charges.

## AWS Budgets

Create a monthly cost budget and define notification thresholds for actual and forecast spending. Send alerts to a monitored address and review cost allocation regularly.

## Cost structure

Actual prices depend on the Region, instance size, storage volume, traffic, retention, and usage duration. Record the current values from AWS Pricing Calculator or the Billing console before submitting the report.

| Cost group | Main charging factor | Control method |
|---|---|---|
| Amazon EC2 | Instance type and running hours | Right-size and schedule Start/Stop |
| Amazon EBS | Provisioned volume and snapshots | Remove unused volumes and snapshots |
| Amazon ECR | Stored image size and data transfer | Lifecycle policy for old images |
| Amazon S3 | Storage, requests, and transfer | Lifecycle rules and retention policy |
| CloudWatch | Custom metrics, logs, dashboards, alarms | Collect only required data and limit retention |
| Data transfer | Outbound Internet traffic | Monitor usage and avoid unnecessary downloads |

The monthly estimate must be treated as a planning value, not a fixed invoice. Compare the estimate with Cost Explorer and AWS Budgets during operation.

## Additional optimization measures

- Select an EC2 size based on measured CPU and memory usage.
- Stop non-production workloads during idle periods.
- Remove unused EBS snapshots, Elastic IPs, and old ECR images.
- Apply S3 and ECR lifecycle policies.
- Limit CloudWatch log retention to the required duration.
- Review Cost Explorer and budget alerts before scaling resources.

## Verification

Confirm Lambda execution results, EventBridge next invocation times, EC2 state changes, budget thresholds, and notification delivery without exposing account or billing details.

## Evidence images to add

1. Lambda functions used to start and stop EC2.
2. Successful Lambda test result or CloudWatch execution log.
3. EventBridge schedules, time zone, and next invocation time.
4. AWS Budget amount, thresholds, and current status.
5. Cost Explorer overview with account and billing details concealed.

<!-- Suggested directory: /static/images/5-Workshop/5.9-Automation-Cost/ -->
