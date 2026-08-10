---
title: "5.2 Kiến trúc hệ thống"
date: 2026-08-09
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

## 5.2.1 Tổng quan kiến trúc

AI Learning Assistant Platform sử dụng kiến trúc **Client–Server**, kết hợp **Retrieval-Augmented Generation (RAG)** và được triển khai trên AWS. Toàn bộ ứng dụng được container hóa bằng Docker và vận hành trên Amazon EC2 thông qua Docker Compose.

Hệ thống được chia thành năm lớp để dễ phát triển, bảo trì và triển khai:

| Lớp | Thành phần | Trách nhiệm |
|---|---|---|
| Client Layer | Next.js, React, trình duyệt | Hiển thị lộ trình, bài học, AI Chat, tài liệu, bài luyện tập, thẻ nhớ và lịch sử học tập |
| Application Layer | Nginx, Frontend, Backend | Tiếp nhận request, xử lý nghiệp vụ và cung cấp API |
| AI & Data Layer | RAG, MongoDB, PostgreSQL/pgvector, Redis, MinIO | Xử lý tài liệu, tìm kiếm ngữ nghĩa, hội thoại và lưu dữ liệu |
| Infrastructure Layer | VPC, EC2, EBS, S3, IAM, Security Group, Elastic IP | Cung cấp hạ tầng chạy, lưu trữ và kiểm soát truy cập |
| DevOps & Monitoring Layer | GitHub Actions, ECR, CloudWatch, SNS, Lambda, EventBridge, Budgets | Build, triển khai, giám sát, cảnh báo, tự động hóa và quản lý chi phí |

Luồng truy cập chính:

```text
Người dùng
   ↓ HTTP/HTTPS
Public IP / FE_DOMAIN
   ↓
Nginx Reverse Proxy
   ├── Frontend
   └── Backend / AI Learning Assistant
          ├── MongoDB
          ├── PostgreSQL + pgvector
          ├── Redis
          ├── MinIO
          └── Code Sandbox
```

> **Hình 5.2.1 – Kiến trúc tổng thể AI Learning Assistant Platform**

![Kiến trúc tổng thể AI Learning Assistant Platform](/images/3.1.d.x.png)

## 5.2.2 Kiến trúc triển khai trên AWS

Hệ thống được triển khai theo mô hình **Production Lite** tại Region **US East (N. Virginia) – `us-east-1`**. Amazon EC2 nằm trong Public Subnet của VPC và được gắn Elastic IP để người dùng truy cập ổn định bằng HTTP/HTTPS.

Security Group chỉ cho phép các cổng cần thiết:

| Cổng | Giao thức | Mục đích | Phạm vi đề xuất |
|---|---|---|---|
| 22 | SSH | Quản trị EC2 khi cần | IP quản trị tin cậy |
| 80 | HTTP | Truy cập website hoặc chuyển hướng HTTPS | Internet |
| 443 | HTTPS | Truy cập website an toàn | Internet |

MongoDB, PostgreSQL, Redis và MinIO giao tiếp qua Docker network nội bộ, không mở trực tiếp ra Internet. Amazon EBS lưu Docker volume và dữ liệu bền vững. Amazon S3 lưu bản sao lưu database và tài liệu cần giữ dài hạn.

Luồng triển khai:

```text
Developer → GitHub Repository → GitHub Actions
                                    ↓
                              Build Docker Image
                                    ↓
                               Amazon ECR
                                    ↓
                         Amazon EC2 / Docker Compose
```

> **Hình 5.2.2 – Kiến trúc triển khai AI Learning Assistant trên AWS**

![Kiến trúc triển khai AWS](/images/3.2.d.s.png)

### Dịch vụ AWS sử dụng

| Dịch vụ | Vai trò trong hệ thống |
|---|---|
| Amazon VPC | Cung cấp mạng cô lập cho tài nguyên |
| Public Subnet | Chứa EC2 và cho phép kết nối Internet |
| Internet Gateway | Kết nối VPC với Internet |
| Elastic IP | Cung cấp địa chỉ IP công khai ổn định |
| Amazon EC2 | Chạy toàn bộ Docker Compose stack |
| Amazon EBS | Lưu Docker volume và dữ liệu ứng dụng |
| Amazon S3 | Lưu backup và object dài hạn |
| Amazon ECR | Lưu Docker image theo phiên bản |
| AWS IAM | Quản lý role và quyền theo Least Privilege |
| Security Group | Kiểm soát lưu lượng vào/ra EC2 |
| Amazon CloudWatch | Thu thập metric và log |
| CloudWatch Alarm | Theo dõi ngưỡng và phát hiện bất thường |
| Amazon SNS | Gửi cảnh báo đến email đã xác nhận |
| AWS Lambda | Gọi API Start/Stop EC2 |
| Amazon EventBridge | Kích hoạt Lambda theo lịch |
| AWS Budgets | Theo dõi và cảnh báo chi phí |

## 5.2.3 Kiến trúc dữ liệu

Nền tảng áp dụng mô hình lưu trữ lai để mỗi loại dữ liệu được xử lý bởi công nghệ phù hợp.

| Thành phần | Dữ liệu lưu trữ | Vai trò |
|---|---|---|
| MongoDB | Người dùng, hội thoại, workflow, cấu hình, metadata Knowledge Base | Dữ liệu nghiệp vụ dạng document |
| PostgreSQL + pgvector | Embedding và dữ liệu vector | Semantic Search và RAG |
| Redis | Cache, session, hàng đợi, tác vụ nền | Tăng tốc và điều phối xử lý |
| MinIO | File tài liệu gốc do người dùng tải lên | Object storage tương thích S3 API |
| Amazon EBS | Docker volume và dữ liệu bền vững trên EC2 | Duy trì dữ liệu sau khi restart instance |
| Amazon S3 | Backup MongoDB, PostgreSQL, MinIO và tài liệu | Độ bền cao và hỗ trợ khôi phục |

Các database chỉ hoạt động trong Docker network nội bộ. Ứng dụng truy cập chúng qua service name, không qua Public IP.

> **Hình 5.2.3 – Thiết kế lưu trữ và cơ sở dữ liệu**

![Thiết kế cơ sở dữ liệu](/images/3.3.pr.drawio.png)

## 5.2.4 Luồng xử lý RAG

Quy trình xây dựng Knowledge Base và trả lời câu hỏi gồm:

1. Người dùng tải tài liệu học tập lên hệ thống.
2. Backend kiểm tra định dạng và trích xuất nội dung.
3. Nội dung được chia thành các đoạn nhỏ (chunk).
4. Embedding model chuyển mỗi chunk thành vector.
5. Vector được lưu trong PostgreSQL/pgvector; metadata lưu trong MongoDB; file gốc lưu trên MinIO.
6. Người dùng gửi câu hỏi qua giao diện AI Chat.
7. Backend tạo embedding cho câu hỏi.
8. pgvector thực hiện semantic search và trả về các chunk liên quan.
9. Backend ghép câu hỏi, ngữ cảnh truy xuất và chỉ dẫn thành prompt gửi cho LLM.
10. Mô hình tạo câu trả lời dựa trên ngữ cảnh và trả kèm nguồn khi workflow hỗ trợ.

Quy trình được chia thành hai pha:

- **Knowledge Base Construction:** upload, extraction, chunking, embedding và lưu trữ.
- **AI Chat:** tạo query embedding, retrieval, prompt construction và answer generation.

Việc tách hai pha cho phép tái sử dụng Knowledge Base trong nhiều cuộc hội thoại và giảm thời gian xử lý.

> **Hình 5.2.4 – Luồng Retrieval-Augmented Generation**

![Luồng xử lý RAG](/images/3.4.p.r.png)

## 5.2.5 Kiến trúc vận hành và tự động hóa

```text
CloudWatch Agent → CloudWatch Dashboard → Alarm → SNS

EventBridge Scheduler → Lambda → EC2 StartInstances / StopInstances

AWS Budgets → Cảnh báo chi phí thực tế và dự báo
```

- CloudWatch Agent thu thập metric bộ nhớ, ổ đĩa và log từ EC2.
- Dashboard tập hợp dữ liệu vận hành tại một nơi.
- Alarm gửi trạng thái bất thường đến SNS.
- EventBridge và Lambda giảm số giờ chạy EC2 khi hệ thống không sử dụng.
- AWS Budgets giúp phát hiện sớm nguy cơ vượt ngân sách.

> **📷 Chèn ảnh tại đây:** Sơ đồ vận hành gồm CloudWatch, SNS, Lambda, EventBridge và AWS Budgets.  
> File: `/images/5-Workshop/5.2-Architecture/operations-architecture.png`
<!-- ![Kiến trúc giám sát và tự động hóa](/images/5-Workshop/5.2-Architecture/operations-architecture.png) -->

## 5.2.6 Công nghệ sử dụng

| Nhóm | Công nghệ |
|---|---|
| Frontend | Next.js, React, TypeScript |
| Backend | FastGPT tùy biến, Node.js |
| AI | Google Gemini hoặc OpenAI, RAG |
| Database | MongoDB, PostgreSQL + pgvector, Redis |
| Object Storage | MinIO, Amazon S3 |
| Reverse Proxy | Nginx |
| Container | Docker, Docker Compose |
| CI/CD | GitHub, GitHub Actions, Amazon ECR |
| AWS Runtime | Amazon EC2, EBS, VPC, Elastic IP |
| Monitoring | CloudWatch, CloudWatch Alarm, SNS |
| Automation | Lambda, EventBridge |
| Security và Cost | IAM, Security Group, AWS Budgets |

## 5.2.7 Đánh giá kiến trúc

Mô hình một EC2 giúp giảm độ phức tạp và chi phí cho giai đoạn MVP. Docker tách biệt dịch vụ; EBS và S3 bảo vệ dữ liệu; CI/CD giúp kiểm soát phiên bản; CloudWatch tăng khả năng quan sát; Lambda và EventBridge giảm chi phí nhàn rỗi.

Hạn chế chính là EC2 vẫn là single point of failure. Khi hệ thống phát triển, có thể chuyển database sang dịch vụ managed, triển khai nhiều Availability Zone, bổ sung Load Balancer, Auto Scaling và dịch vụ quản lý secret.

