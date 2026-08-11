---
title: "5.6. CI/CD with GitHub Actions and ECR"
date: 2026-08-09
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

## Pipeline objective

The pipeline creates a repeatable, traceable delivery process. Every successful build produces a versioned image in Amazon ECR instead of rebuilding directly on the server.

## ECR preparation

Create a private ECR repository, enable image scanning when appropriate, and define a lifecycle policy to remove obsolete images. Grant the workflow only the permissions required to push images.

![Docker image và tag trong Amazon ECR](/images/5-Workshop/5.6-CICD-ECR/ecr-images.png)
## GitHub Actions workflow

A typical workflow performs:

1. Source checkout.
2. Dependency or source validation.
3. Authentication to AWS with short-lived credentials or OIDC.
4. Login to Amazon ECR.
5. Docker image build.
6. Tagging with commit SHA and/or release tag.
7. Push to ECR.
8. Optional EC2 deployment when explicitly implemented.

Store configuration in GitHub Secrets or Variables. Prefer OIDC over long-lived AWS access keys.

![GitHub Actions build và push image thành công](/images/5-Workshop/5.6-CICD-ECR/github-actions-success.png)
## Deployment verification

Confirm that the workflow is successful, the expected tag and digest exist in ECR, and EC2 runs the intended image version. If deployment fails, keep the previous known-good tag available for rollback.

![Image tag đang được triển khai trên EC2](/images/5-Workshop/5.6-CICD-ECR/deployed-image-tag.png)