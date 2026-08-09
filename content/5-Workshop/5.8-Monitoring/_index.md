---
title: "Monitoring with CloudWatch and SNS"
date: 2026-08-09
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

# 5.8 Monitoring with CloudWatch and Amazon SNS

## Monitoring objective

Monitoring must reveal infrastructure pressure and application failures before they become prolonged outages. The workshop uses native EC2 metrics together with CloudWatch Agent metrics.

## CloudWatch Agent

Attach an IAM role that permits metric and log delivery. Configure only metrics that are needed, such as memory utilization, disk utilization, swap, and selected log files. Start the agent and verify that new data reaches the correct Region.

## Dashboard

Create a dashboard containing the metrics actually collected:

- EC2 CPU utilization and instance status.
- Memory and disk utilization from CloudWatch Agent.
- Network traffic.
- Application or Nginx logs when log collection is configured.

## Alarm and notification flow

Create alarms for meaningful thresholds and evaluation periods. Publish alarm state changes to an SNS topic, confirm the email subscription, and test the notification flow safely.

```text
Metric → CloudWatch Alarm → SNS Topic → Confirmed subscriber
```

## Operational verification

Confirm dashboard data is recent, alarm state is explainable, missing-data behavior is configured, and sensitive email addresses are concealed in public evidence.

## Evidence images to add

1. CloudWatch Agent status on EC2.
2. CloudWatch Dashboard with CPU, memory, disk, or network data.
3. Alarm name, threshold, and current state.
4. SNS topic and `Confirmed` subscription with email concealed.
5. Sample alert email with personal information hidden.

<!-- Suggested directory: /static/images/5-Workshop/5.8-Monitoring/ -->
