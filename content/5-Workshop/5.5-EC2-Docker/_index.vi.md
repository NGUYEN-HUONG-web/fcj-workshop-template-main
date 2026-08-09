---
title: "Triển khai EC2 và Docker Compose"
date: 2026-08-09
weight: 5
chapter: false
pre: " <b> 5.5. </b> "
---

# 5.5 Triển khai EC2 và Docker Compose

## Tạo EC2 instance

Khởi tạo EC2 bằng Linux AMI được hỗ trợ, instance type phù hợp, EBS đủ dung lượng, IAM role, key pair nếu dùng SSH và Security Group theo nguyên tắc đặc quyền tối thiểu. Ghi lại Region và Instance ID.

> **📷 Chèn ảnh tại đây:** EC2 `Running`, status checks `2/2 passed`; che định danh nhạy cảm.  
> File: `/images/5-Workshop/5.5-EC2-Docker/ec2-running.png`
<!-- ![EC2 đang hoạt động](/images/5-Workshop/5.5-EC2-Docker/ec2-running.png) -->

> **📷 Chèn ảnh tại đây:** Inbound rules của Security Group.  
> File: `/images/5-Workshop/5.5-EC2-Docker/security-group.png`
<!-- ![Security Group của EC2](/images/5-Workshop/5.5-EC2-Docker/security-group.png) -->

## Cài đặt môi trường chạy

Kết nối bằng SSH hoặc Session Manager, cập nhật hệ điều hành và cài Docker Engine, Docker Compose plugin, Git cùng CloudWatch Agent. Chỉ thêm user triển khai vào nhóm Docker khi cần.

## Triển khai hệ thống

Clone cấu hình triển khai, tạo `.env` được bảo vệ, đăng nhập ECR nếu dùng private image và chạy:

```bash
docker compose pull
docker compose up -d
docker compose ps
```

> **📷 Chèn ảnh tại đây:** Terminal EC2 hiển thị các container `Up` hoặc healthy.  
> File: `/images/5-Workshop/5.5-EC2-Docker/ec2-containers.png`
<!-- ![Container trên EC2](/images/5-Workshop/5.5-EC2-Docker/ec2-containers.png) -->

## Cấu hình Nginx

Nginx Reverse Proxy nhận request từ Public IP hoặc `FE_DOMAIN` và chuyển đến ứng dụng. Cấu hình HTTPS khi có domain và chứng chỉ. Không mở công khai cổng MongoDB, PostgreSQL, Redis hoặc trang quản trị MinIO.

> **📷 Chèn ảnh tại đây:** Website truy cập thành công qua Public IP hoặc domain.  
> File: `/images/5-Workshop/5.5-EC2-Docker/public-website.png`
<!-- ![Website chạy trên EC2](/images/5-Workshop/5.5-EC2-Docker/public-website.png) -->

## Kiểm tra kết quả

- EC2 ở trạng thái `Running`.
- Status checks hiển thị `2/2 passed`.
- Container cần thiết ở trạng thái `Up` hoặc healthy.
- Website truy cập được qua địa chỉ công khai đã cấu hình.
- Log không có lỗi nghiêm trọng lặp lại.
- Data volume được mount đúng.

## Ảnh minh chứng cần bổ sung

1. EC2 ở trạng thái `Running`, status checks là `2/2 passed`.
2. Chi tiết EC2 đã che định danh nhạy cảm.
3. Inbound rules của Security Group.
4. Terminal hiển thị Docker và các container đang chạy.
5. Website truy cập qua Public IP hoặc domain đã cấu hình.

<!-- Thư mục đề xuất: /static/images/5-Workshop/5.5-EC2-Docker/ -->
