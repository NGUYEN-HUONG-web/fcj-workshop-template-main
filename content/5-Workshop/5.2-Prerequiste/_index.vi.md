---
title: "Prerequisites"
date: 2026-08-05
weight: 2
chapter: false
pre: " <b> 5.2. </b> "
---

# Chuẩn bị môi trường

## Mục tiêu

Trong phần này, chúng ta sẽ chuẩn bị các tài khoản, công cụ và môi trường cần thiết trước khi triển khai **AI Learning Assistant Platform** trên **Amazon Web Services (AWS)**.

Sau khi hoàn thành, môi trường sẽ sẵn sàng để triển khai hạ tầng AWS ở các phần tiếp theo.

---

## Tài khoản và công cụ sử dụng

Workshop sử dụng các tài khoản và công cụ sau:

| Thành phần | Mục đích |
|------------|----------|
| AWS Account | Quản lý và triển khai tài nguyên AWS |
| IAM User | Quản lý tài nguyên AWS theo nguyên tắc quyền tối thiểu |
| GitHub | Lưu trữ mã nguồn và cấu hình CI/CD |
| AWS CLI | Quản lý tài nguyên AWS bằng dòng lệnh |
| Git | Quản lý mã nguồn |
| SSH Client | Kết nối đến Amazon EC2 |

---

## AWS Management Console

Đăng nhập vào **AWS Management Console** và lựa chọn Region **US East (N. Virginia) – us-east-1** để triển khai hệ thống.

> **Hình 5.2.1. AWS Management Console**

![Hình 5.2.1](/images/5.2.1.png)

---

## GitHub Repository

Toàn bộ mã nguồn của **AI Learning Assistant Platform** được lưu trữ trên GitHub Repository và sẽ được sử dụng trong quá trình triển khai.

> **Hình 5.2.2. GitHub Repository**

![Hình 5.2.2](/images/5.2.2.png)

---

## AWS CLI

AWS CLI được sử dụng để quản lý tài nguyên AWS và kiểm tra kết nối với tài khoản AWS.

```bash
aws --version
```

```bash
aws sts get-caller-identity
```

> **Hình 5.2.3. Kiểm tra AWS CLI**

![Hình 5.2.3](/images/5.2.3.png)

---

## Git

Git được sử dụng để quản lý và tải mã nguồn từ GitHub Repository.

```bash
git --version
```

> **Hình 5.2.4. Kiểm tra Git**

![Hình 5.2.4](/images/5.2.4.png)

---

## Dịch vụ AWS sử dụng

Workshop sử dụng các dịch vụ AWS sau:

| Dịch vụ | Mục đích |
|----------|----------|
| Amazon EC2 | Triển khai AI Learning Assistant Platform |
| Amazon EBS | Lưu trữ dữ liệu |
| Amazon ECR | Quản lý Docker Image |
| Amazon S3 | Sao lưu dữ liệu |
| Amazon CloudWatch | Giám sát hệ thống |
| AWS IAM | Quản lý quyền truy cập |
| Security Group | Kiểm soát lưu lượng mạng |
| AWS Budgets | Theo dõi chi phí |

---

## Kết quả

Sau khi hoàn thành phần này, môi trường triển khai đã sẵn sàng để bắt đầu khởi tạo hạ tầng AWS.