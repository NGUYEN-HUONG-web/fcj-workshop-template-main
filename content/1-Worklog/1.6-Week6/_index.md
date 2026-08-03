---
title: "Week 6 Worklog"
date: 2026-07-27
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Week 6 Objectives

* Understand the fundamentals of containers and the differences between containers and virtual machines.
* Package applications using Docker.
* Manage Docker images with Amazon Elastic Container Registry (Amazon ECR).
* Learn about Amazon Elastic Container Service (Amazon ECS) and AWS Fargate.
* Explore Kubernetes and Amazon Elastic Kubernetes Service (Amazon EKS).
* Deploy containerized applications on AWS.

### Tasks Completed During the Week

| Day | Tasks | Start Date | Completion Date | Reference Materials |
| --- | --- | --- | --- | --- |
| **2** | - Learned about Docker Images, Containers, Dockerfiles, Registries, Volumes, and Networks.<br>- Installed Docker Desktop.<br>- Practiced using `docker pull`, `docker run`, `docker ps`, `docker logs`, and `docker exec`.<br>- Compared container technology with traditional virtual machines. | 27/07/2026 | 27/07/2026 | <https://docs.docker.com/get-started/> |
| **3** | - Wrote Dockerfiles for both backend and frontend applications.<br>- Used Multi-stage Builds to reduce Docker image size.<br>- Built and ran containers locally.<br>- Learned Docker Compose and the use of environment variables. | 28/07/2026 | 28/07/2026 | <https://docs.docker.com/build/building/multi-stage/> |
| **4** | - Created an Amazon ECR repository.<br>- Logged in to Amazon ECR using the AWS CLI.<br>- Tagged and pushed Docker images to Amazon ECR.<br>- Enabled Image Scanning and reviewed detected vulnerabilities. | 29/07/2026 | 29/07/2026 | <https://docs.aws.amazon.com/AmazonECR/latest/userguide/getting-started-cli.html> |
| **5** | - Learned about ECS Clusters, Task Definitions, Tasks, and Services.<br>- Compared Amazon ECS on EC2 with AWS Fargate.<br>- Created a Task Definition using a Docker image stored in Amazon ECR.<br>- Deployed an ECS Service and reviewed container logs. | 30/07/2026 | 30/07/2026 | <https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html> |
| **6** | - Studied Kubernetes architecture, including the Control Plane, Worker Nodes, Pods, Deployments, and Services.<br>- Practiced using `kubectl` and Kubernetes YAML manifests.<br>- Learned about Amazon EKS, Managed Node Groups, and EKS Pod Identity.<br>- Deployed a sample application and verified Pod status. | 31/07/2026 | 31/07/2026 | <https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html> |

### Achievements

* Clearly understood the differences between containers and virtual machines.
* Successfully wrote Dockerfiles and packaged applications as Docker images.
* Used Multi-stage Builds to optimize Docker image size.
* Managed multiple containers using Docker Compose.
* Created an Amazon ECR repository and successfully pushed Docker images.
* Understood the architecture of Amazon ECS, including Clusters, Task Definitions, and Services.
* Learned the roles of Pods, Deployments, and Services in Kubernetes.
* Gained hands-on experience with Amazon EKS and Managed Node Groups.
* Became familiar with essential Docker commands, Amazon ECR operations, and basic `kubectl` commands.

### Challenges and Solutions

| Challenges | Solutions |
| --- | --- |
| Docker images were too large. | Reduced image size by using smaller base images and implementing Multi-stage Builds. |
| Unable to push Docker images to Amazon ECR. | Verified the AWS Region, IAM permissions, and repeated the Amazon ECR login process. |
| Containers stopped immediately after startup. | Checked `docker logs`, verified environment variables, and reviewed the `ENTRYPOINT` configuration. |
| Kubernetes Pods remained in the `ImagePullBackOff` state. | Verified the image URI, image tag, and Amazon ECR access permissions. |
| Kubernetes Services were inaccessible. | Reviewed Labels, Selectors, Port, and TargetPort configurations to ensure they matched correctly. |

---

### Weekly Reflection

Week 6 provided me with a solid understanding of how containerization standardizes application development and deployment. Docker ensures that applications run consistently across local development environments and AWS cloud infrastructure, reducing deployment issues caused by environmental differences.

I also learned how Amazon ECR serves as a secure container image registry, while Amazon ECS and Amazon EKS offer two different approaches to container orchestration. Although Kubernetes is a powerful and flexible platform, it introduces additional complexity. Understanding core concepts such as Pods, Deployments, Services, and resource status monitoring is essential for effectively managing containerized applications in production environments.