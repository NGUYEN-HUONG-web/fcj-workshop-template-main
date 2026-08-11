---
title: "5.8. Monitoring with CloudWatch and SNS"
date: 2026-08-09
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

## Monitoring objective

Monitoring must reveal infrastructure pressure and application failures before they become prolonged outages. The workshop uses native EC2 metrics together with CloudWatch Agent metrics.

## CloudWatch Agent

Attach an IAM role that permits metric and log delivery. Configure only metrics that are needed, such as memory utilization, disk utilization, swap, and selected log files. Start the agent and verify that new data reaches the correct Region.
![CloudWatch Agent đang hoạt động trên EC2](/images/5-Workshop/5.8-Monitoring/cloudwatch-agent-status.png)
## Dashboard

Create a dashboard containing the metrics actually collected:

- EC2 CPU utilization and instance status.
- Memory and disk utilization from CloudWatch Agent.
- Network traffic.
- Application or Nginx logs when log collection is configured.
![CloudWatch Dashboard của hệ thống](/images/5-Workshop/5.8-Monitoring/cloudwatch-dashboard.png)
## Alarm and notification flow

Create alarms for meaningful thresholds and evaluation periods. Publish alarm state changes to an SNS topic, confirm the email subscription, and test the notification flow safely.
![CloudWatch Alarm và trạng thái hiện tại](/images/5-Workshop/5.8-Monitoring/cloudwatch-alarm.png)

![SNS subscription ở trạng thái Confirmed](/images/5-Workshop/5.8-Monitoring/sns-subscription.png)
```text
Metric → CloudWatch Alarm → SNS Topic → Confirmed subscriber
```

## Operational verification

Confirm dashboard data is recent, alarm state is explainable, missing-data behavior is configured, and sensitive email addresses are concealed in public evidence.
