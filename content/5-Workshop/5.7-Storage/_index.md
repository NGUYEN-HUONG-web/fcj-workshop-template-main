---
title: "5.7. Storage with MinIO and Amazon S3"
date: 2026-08-09
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

## Storage design

The platform uses multiple storage technologies because application data has different access patterns.

| Storage | Data type | Purpose |
|---|---|---|
| MongoDB | Documents and metadata | Users, workflows, configuration, conversations |
| PostgreSQL + pgvector | Relational and vector data | Embeddings, semantic retrieval, RAG |
| Redis | Temporary in-memory data | Cache, queues, background coordination |
| MinIO | Application objects | Uploaded files through an S3-compatible API |
| Amazon S3 | Durable AWS objects | Backup or long-term retention |

## MinIO configuration

Configure a private bucket, endpoint, access credentials, and persistent Docker volume. Keep the management console private. Test upload, download, and application access with a non-sensitive document.
![MinIO bucket và object](/images/5-Workshop/5.7-Storage/mino.png) 
## Amazon S3 configuration

Create a private bucket with Block Public Access enabled. Use encryption, versioning, and lifecycle rules according to retention requirements. Grant EC2 access through an IAM role and least-privilege bucket policy.
![Cấu hình bảo mật và versioning của Amazon S3](/images/5-Workshop/5.7-Storage/s3-bucket-settings.png)
## Backup and recovery

Define which MinIO objects, database exports, and configuration artifacts are copied to S3. Schedule backups, record retention, and test restoration rather than assuming that uploaded objects are recoverable.
![Danh sách object sao lưu trên Amazon S3](/images/5-Workshop/5.7-Storage/s3-backup-objects.png)
## Verification

- Application uploads and reads a sample file.
- Objects persist after container restart.
- Expected backup objects appear in S3.
- Unauthorized public access is denied.
- A sample recovery procedure succeeds.


