---
title: "Workshop"
date: 2026-08-09
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Triển khai AI Learning Assistant trên AWS

## Tổng quan Workshop

Workshop trình bày cách triển khai và vận hành **AI Learning Assistant**, nền tảng được tùy biến từ FastGPT và chạy trên **Amazon EC2**. Hệ thống hỗ trợ lộ trình học AWS, hỏi đáp dựa trên tài liệu, bài luyện tập, thẻ nhớ và lịch sử học tập.

Ứng dụng chạy bằng Docker Compose, gồm AI Learning Assistant, MongoDB, PostgreSQL với pgvector, Redis, MinIO, Code Sandbox và Nginx Reverse Proxy. Các dịch vụ AWS hỗ trợ lưu image, sao lưu, giám sát, cảnh báo, tự động hóa và quản lý chi phí.

Sau khi hoàn thành Workshop, bạn có thể:

- Triển khai ứng dụng Generative AI dạng container trên Amazon EC2.
- Build và lưu Docker image bằng GitHub Actions và Amazon ECR.
- Kết hợp MongoDB, PostgreSQL với pgvector, Redis, MinIO và Amazon S3.
- Giám sát EC2 bằng CloudWatch Agent, Dashboard, Alarm và Amazon SNS.
- Tự động bật/tắt EC2 bằng Lambda và EventBridge.
- Theo dõi chi phí dự án bằng AWS Budgets.
- Kiểm thử chat AI, xử lý tài liệu và các tính năng học tập.

## Kiến trúc giải pháp

```text
Người dùng
  ↓
Public IP / FE_DOMAIN
  ↓
Nginx Reverse Proxy
  ↓
AI Learning Assistant
  ├── MongoDB
  ├── PostgreSQL + pgvector
  ├── Redis
  ├── MinIO
  ├── Amazon S3
  └── Code Sandbox
```

```text
GitHub Actions → Amazon ECR → Amazon EC2 → Docker Compose
CloudWatch Agent → Dashboard → Alarm → Amazon SNS
EventBridge → Lambda → Start/Stop Amazon EC2
AWS Budgets → Cảnh báo chi phí
```

| Thành phần | Vai trò |
|---|---|
| Nginx Reverse Proxy | Chuyển request bên ngoài đến ứng dụng. |
| MongoDB | Lưu người dùng, workflow, cấu hình và lịch sử hội thoại. |
| PostgreSQL + pgvector | Lưu embedding và hỗ trợ tìm kiếm ngữ nghĩa cho RAG. |
| Redis | Hỗ trợ cache, hàng đợi và tác vụ nền. |
| MinIO | Cung cấp lưu trữ tương thích S3 trực tiếp cho ứng dụng. |
| Amazon S3 | Cung cấp sao lưu hoặc lưu trữ dài hạn. |
| Code Sandbox | Thực thi mã trong môi trường cô lập. |
| Amazon ECR | Lưu Docker image theo phiên bản. |
| CloudWatch và SNS | Giám sát, cảnh báo và gửi thông báo. |
| Lambda và EventBridge | Tự động bật/tắt EC2 theo lịch. |
| AWS Budgets | Theo dõi chi phí và các ngưỡng cảnh báo. |

## Điều kiện tiên quyết

- Tài khoản AWS có quyền sử dụng EC2, ECR, S3, CloudWatch, SNS, Lambda, EventBridge, IAM và AWS Budgets.
- GitHub repository chứa ứng dụng, Dockerfile, Docker Compose và workflow.
- EC2 key pair và Security Group theo nguyên tắc đặc quyền tối thiểu.
- Docker và Docker Compose đã được cài trên EC2.
- Biến môi trường và thông tin xác thực mô hình AI được lưu an toàn.
- SNS subscription đã ở trạng thái `Confirmed`.
- Tài liệu mẫu và câu hỏi demo đã được kiểm thử.

> Không công khai Access Key, API key, file `.env`, mật khẩu cơ sở dữ liệu, SSH private key, connection string, Account ID, dữ liệu thanh toán hoặc tài liệu nhạy cảm.

## Quy trình triển khai

### 1. Kiểm tra Amazon EC2

Mở **EC2 → Instances**, chọn đúng Region và xác nhận instance đang `Running`, status checks là `2/2 passed`. Kiểm tra Public IPv4 hoặc domain truy cập được và Security Group chỉ mở các cổng cần thiết.

```bash
docker --version
docker compose version
```

### 2. Khởi chạy Docker Compose

```bash
docker compose pull
docker compose up -d
docker compose ps
```

Các container cần thiết phải ở trạng thái `Up` hoặc healthy. Khi một dịch vụ lỗi, kiểm tra log:

```bash
docker compose logs --tail=100 <service-name>
```

### 3. Kiểm tra Amazon ECR và GitHub Actions

Trong Amazon ECR, kiểm tra image tag, digest và thời gian push gần nhất. Trong GitHub Actions, mở workflow thành công gần nhất và xác nhận các bước thực tế: kiểm tra mã nguồn, xác thực AWS, build image, gắn tag và push lên ECR. Chỉ mô tả tự động deploy EC2 nếu workflow đã có bước đó.

### 4. Kiểm tra object storage

Kiểm tra bucket và object của dự án trong Amazon S3 nhưng không mở dữ liệu nhạy cảm. Trong kiến trúc này, MinIO phục vụ file trực tiếp cho ứng dụng; Amazon S3 hỗ trợ sao lưu hoặc lưu trữ dài hạn, giúp giảm phụ thuộc vào ổ đĩa EC2.

## Giám sát và tự động hóa

### CloudWatch và SNS

CloudWatch Agent gửi các metric hệ điều hành đã cấu hình từ EC2. Dashboard hiển thị CPU, bộ nhớ, ổ đĩa hoặc mạng. CloudWatch Alarm gửi thay đổi trạng thái tới SNS topic để subscription đã xác nhận nhận được thông báo.

### Lambda và EventBridge

EventBridge kích hoạt Lambda theo lịch. Lambda gọi EC2 API để bật máy chủ trước thời gian sử dụng và tắt trong thời gian nhàn rỗi, từ đó giảm chi phí vận hành.

### AWS Budgets

AWS Budgets theo dõi chi phí dự án và gửi cảnh báo khi chi phí thực tế hoặc dự báo tiến gần ngưỡng đã cấu hình.

## Kiểm thử ứng dụng

Mở AI Learning Assistant qua Public IP hoặc `FE_DOMAIN` và kiểm tra các luồng sau.

### Trợ lý học bài

Chọn chế độ **Giải thích** và nhập:

```text
Giải thích sự khác nhau giữa Amazon S3 và Amazon EBS bằng ví dụ dễ hiểu.
```

Sau đó gửi câu hỏi tiếp theo:

```text
Cho tôi một tình huống thực tế để lựa chọn giữa hai dịch vụ này.
```

Trợ lý phải hiểu “hai dịch vụ này” là S3 và EBS trong lượt hội thoại trước.

### Học tập dựa trên tài liệu

Đính kèm tài liệu mẫu và nhập:

```text
Hãy tóm tắt nội dung chính của tài liệu này và tạo 3 câu hỏi ôn tập.
```

Ứng dụng sử dụng tài liệu làm ngữ cảnh hội thoại hoặc truy xuất các đoạn liên quan từ Knowledge Base thông qua PostgreSQL và pgvector.

### Luyện tập và theo dõi tiến độ

Mở một bài học, trả lời một câu hỏi, xem kết quả, lật một thẻ nhớ và kiểm tra lịch sử học tập. Các bước này xác nhận chu trình học, luyện tập, ôn tập và theo dõi tiến độ hoạt động đầy đủ.

## Checklist nghiệm thu

- [ ] EC2 đang `Running` và status checks là `2/2 passed`.
- [ ] Tất cả Docker container cần thiết đang chạy.
- [ ] Website truy cập được qua địa chỉ đã cấu hình.
- [ ] Docker image cần thiết tồn tại trong Amazon ECR.
- [ ] GitHub Actions workflow gần nhất thành công.
- [ ] MinIO và Amazon S3 đúng với vai trò lưu trữ đã triển khai.
- [ ] CloudWatch nhận metric và Dashboard hiển thị dữ liệu.
- [ ] CloudWatch Alarm và SNS notification đã được cấu hình.
- [ ] Lambda và EventBridge có lịch cùng múi giờ chính xác.
- [ ] AWS Budgets hiển thị budget của dự án.
- [ ] Mô hình AI, ứng dụng và Knowledge Base phản hồi thành công.
- [ ] Hội thoại theo ngữ cảnh và xử lý tài liệu hoạt động.
- [ ] Bài luyện tập, thẻ nhớ và lịch sử học tập truy cập được.

## Nội dung Workshop

1. [Tổng quan kiến trúc và hệ thống](5.1-workshop-overview/)
2. [Chuẩn bị môi trường](5.2-prerequiste/)
3. [Triển khai Amazon EC2](5.3-deploy-ec2/)
4. [Dịch vụ ứng dụng và lưu trữ](5.4-s3-onprem/)
5. [Bảo mật và endpoint policy](5.5-policy/)
6. [Dọn dẹp tài nguyên AWS](5.6-cleanup/)

## Kết luận

Workshop trình bày mô hình Production Lite cho nền tảng học tập Generative AI trên AWS. Docker Compose giúp triển khai nhất quán; GitHub Actions và ECR hỗ trợ quản lý phiên bản; CloudWatch và SNS cung cấp giám sát; Lambda, EventBridge và AWS Budgets hỗ trợ kiểm soát chi phí; ứng dụng cung cấp trợ lý AI dựa trên tài liệu cùng các tính năng học tập thực tế.

