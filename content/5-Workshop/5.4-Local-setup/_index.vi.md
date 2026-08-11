---
title: "5.4. Điều kiện tiên quyết và chạy local"
date: 2026-08-09
weight: 4
chapter: false
pre: " <b> 5.4. </b> "
---

## Điều kiện tiên quyết

- Git và tài khoản GitHub.
- Docker Engine hoặc Docker Desktop có Docker Compose.
- Tối thiểu 8 GB RAM và đủ dung lượng cho image, volume.
- Trình duyệt được hỗ trợ.
- Biến môi trường và thông tin xác thực mô hình AI hợp lệ.
- AWS CLI nếu cần kiểm tra quyền AWS từ local.

![Phiên bản Git, Docker và Docker Compose](/images/5-Workshop/5.4-Local-Setup/tool-versions.png)

## Tải và cấu hình dự án

```bash
git clone <repository-url>
cd <repository-directory>
cp .env.example .env
```

Mở `.env` và cấu hình theo tài liệu dự án. Dùng mật khẩu mạnh, riêng biệt và không chia sẻ file này.

## Khởi chạy hệ thống local

```bash
docker compose pull
docker compose up -d
docker compose ps
```

Chờ các container ứng dụng, MongoDB, PostgreSQL/pgvector, Redis, MinIO, Code Sandbox và Nginx hoạt động.

![Các container chạy trên môi trường local](/images/5-Workshop/5.4-Local-Setup/local-containers.png)

## Kiểm tra local

1. Mở frontend URL đã cấu hình.
2. Đăng nhập 
3. Mở một lộ trình và bài học.
4. Gửi câu hỏi mẫu cho trợ lý AI.
5. Tải lên tài liệu mẫu không nhạy cảm.
6. Khởi động lại container và kiểm tra dữ liệu vẫn tồn tại.

![Ứng dụng và trợ lý AI chạy trên môi trường local](/images/5-Workshop/5.4-Local-Setup/local-application.png)

## Xử lý lỗi

```bash
docker compose logs --tail=100 <service-name>
docker compose restart <service-name>
docker system df
```

Kiểm tra xung đột cổng, biến môi trường sai, thiếu bộ nhớ, dependency không healthy và kết nối API mô hình trước khi triển khai AWS.

