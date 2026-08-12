---
title: "5.10. Cleanup and Future Development"
date: 2026-08-09
weight: 10
chapter: false
pre: " <b> 5.10. </b> "
---

## Resource cleanup

Clean up in dependency-aware order so resources are not left behind:

1. Export required application data and verify the final backup in Amazon S3.
2. Stop the Docker Compose stack and remove temporary containers, images, and unused volumes.
3. Stop or terminate EC2 according to the retention decision.
4. Release an unused Elastic IP and remove obsolete EBS volumes or snapshots.
5. Remove outdated ECR images or apply the repository lifecycle policy.
6. Delete temporary S3 objects or buckets only after confirming retention requirements.
7. Disable or delete EventBridge schedules and Lambda functions no longer required.
8. Delete unused CloudWatch alarms, dashboards, log groups, and SNS subscriptions.
9. Remove temporary IAM policies and roles after dependent resources are gone.
10. Review Billing, Cost Explorer, and Resource Explorer for remaining resources.

![Tài nguyên đã được dọn dẹp](/images/5.10.png)

## Handover

Record the deployed image tag, environment configuration version, backup location, monitoring resources, schedules, known limitations, and recovery procedure. Transfer secrets through an approved secure channel, never through the report or Git repository.

## Future development

- Move databases and object storage to managed AWS services where appropriate.
- Run the application across multiple Availability Zones behind an Application Load Balancer.
- Add Auto Scaling, container orchestration, and zero-downtime deployments.
- Use AWS Secrets Manager or Systems Manager Parameter Store for secret rotation.
- Add HTTPS with a custom domain, AWS Certificate Manager, and stronger edge protection.
- Improve RAG with document quality checks, hybrid search, reranking, citations, and evaluation datasets.
- Add role-based access control, audit logs, quotas, and content safety controls.
- Expand learning analytics, adaptive quizzes, personalized recommendations, and instructor dashboards.
- Add automated integration, security, load, backup, and disaster-recovery tests.
- Define infrastructure with code to reproduce the environment consistently.

These improvements should be prioritized using measured usage, reliability requirements, security risk, and available budget.
