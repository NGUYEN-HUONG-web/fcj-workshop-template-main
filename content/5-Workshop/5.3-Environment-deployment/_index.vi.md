---
title: "Triển khai môi trường"
date: 2026-08-09
weight: 3
chapter: false
pre: " <b> 5.3. </b> "
---

# 5.3 Triển khai môi trường

## Mục tiêu

Phần này chuẩn bị môi trường triển khai thống nhất cho AI Learning Assistant. Kiến trúc mục tiêu theo mô hình Production Lite: phù hợp phạm vi đồ án nhưng vẫn bảo đảm khả năng tái triển khai, bảo mật, giám sát và khôi phục.

## Các môi trường sử dụng

| Môi trường | Mục đích | Thành phần chính |
|---|---|---|
| Local | Phát triển và kiểm thử chức năng | Docker Desktop/Engine, Docker Compose, trình duyệt |
| GitHub Actions | Tự động build và phân phối | Workflow runner, xác thực AWS, Docker build |
| Amazon ECR | Lưu trữ container image | Image ứng dụng theo phiên bản |
| Amazon EC2 | Môi trường chạy hệ thống | Docker Compose, Nginx, CloudWatch Agent |
| Amazon S3 | Object storage trên AWS | Sao lưu hoặc lưu trữ dài hạn |

## Kế hoạch tài nguyên AWS

Thống nhất quy tắc đặt tên cho EC2, ECR repository, S3 bucket, IAM role, CloudWatch, Lambda, EventBridge, SNS và AWS Budget. Các tài nguyên theo Region nên được tạo trong cùng một Region, trừ khi kiến trúc yêu cầu khác.

> **📷 Chèn ảnh tại đây:** AWS Console hiển thị Region và tài nguyên chính; che Account ID.  
> File: `/images/5-Workshop/5.3-Environment/aws-region-resources.png`
<!-- ![Region và tài nguyên AWS](/images/5-Workshop/5.3-Environment/aws-region-resources.png) -->

## Kế hoạch mạng và truy cập

1. Đặt EC2 trong subnet có kết nối Internet đầu ra.
2. Chỉ cho phép SSH từ IP tin cậy hoặc sử dụng Session Manager.
3. Mở HTTP/HTTPS phục vụ website.
4. Giữ cổng database và cache bên trong Docker network.
5. Gán IAM role cho EC2 thay vì lưu Access Key dài hạn trên máy chủ.

## Biến môi trường

Tạo `.env` từ file mẫu của dự án và khai báo thông tin MongoDB, PostgreSQL, Redis, MinIO, mô hình AI, URL ứng dụng và cấu hình lưu trữ. Không commit `.env` lên Git.

> **📷 Chèn ảnh tại đây:** Cấu trúc repository và `.env.example`; che toàn bộ secret.  
> File: `/images/5-Workshop/5.3-Environment/repository-environment.png`
<!-- ![Repository và cấu hình môi trường](/images/5-Workshop/5.3-Environment/repository-environment.png) -->

## Kết quả mong đợi

Môi trường local, CI/CD và AWS dùng cấu hình tương thích; tài nguyên được đặt tên nhất quán; thông tin bí mật được tách khỏi mã nguồn.

## Ảnh minh chứng cần bổ sung

1. AWS Console hiển thị đúng Region sử dụng.
2. Cấu trúc repository có Dockerfile, Docker Compose và workflow.
3. Danh sách tài nguyên AWS và quy tắc đặt tên.
4. File cấu hình mẫu đã che toàn bộ giá trị bí mật.

<!-- Thư mục đề xuất: /static/images/5-Workshop/5.3-Environment/ -->
