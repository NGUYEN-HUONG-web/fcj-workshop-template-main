---
title: "5.7. Lưu trữ với MinIO và Amazon S3"
date: 2026-08-09
weight: 7
chapter: false
pre: " <b> 5.7. </b> "
---

## Thiết kế lưu trữ

Nền tảng sử dụng nhiều công nghệ lưu trữ vì mỗi loại dữ liệu có cách truy cập khác nhau.

| Lưu trữ | Loại dữ liệu | Mục đích |
|---|---|---|
| MongoDB | Document và metadata | Người dùng, workflow, cấu hình, hội thoại |
| PostgreSQL + pgvector | Dữ liệu quan hệ và vector | Embedding, tìm kiếm ngữ nghĩa, RAG |
| Redis | Dữ liệu tạm trong bộ nhớ | Cache, hàng đợi, điều phối tác vụ nền |
| MinIO | Object của ứng dụng | File tải lên qua API tương thích S3 |
| Amazon S3 | Object bền vững trên AWS | Sao lưu hoặc lưu trữ dài hạn |

## Cấu hình MinIO

Tạo bucket private, khai báo endpoint, credential và Docker volume bền vững. Giữ trang quản trị ở mạng riêng. Kiểm tra upload, download và truy cập từ ứng dụng bằng tài liệu không nhạy cảm.

> **📷 Chèn ảnh tại đây:** MinIO bucket, object mẫu và volume bền vững; không hiển thị credential.  
> File: `/images/5-Workshop/5.7-Storage/minio-storage.png`
<!-- ![MinIO bucket và object](/images/5-Workshop/5.7-Storage/minio-storage.png) -->

## Cấu hình Amazon S3

Tạo bucket private, bật Block Public Access. Áp dụng mã hóa, versioning và lifecycle rule theo chính sách lưu trữ. Cấp quyền cho EC2 qua IAM role và bucket policy tối thiểu.

> **📷 Chèn ảnh tại đây:** S3 bucket private, Block Public Access và cấu hình versioning/mã hóa.  
> File: `/images/5-Workshop/5.7-Storage/s3-bucket-settings.png`
<!-- ![Cấu hình Amazon S3](/images/5-Workshop/5.7-Storage/s3-bucket-settings.png) -->

## Sao lưu và khôi phục

Xác định object MinIO, database export và file cấu hình nào được sao lưu lên S3. Lập lịch, quy định thời gian lưu và kiểm thử khôi phục thay vì chỉ giả định dữ liệu có thể phục hồi.

> **📷 Chèn ảnh tại đây:** Danh sách S3 object có thời gian sao lưu gần nhất; không mở nội dung nhạy cảm.  
> File: `/images/5-Workshop/5.7-Storage/s3-backup-objects.png`
<!-- ![Object sao lưu trên S3](/images/5-Workshop/5.7-Storage/s3-backup-objects.png) -->

## Kiểm tra kết quả

- Ứng dụng tải lên và đọc được file mẫu.
- Object còn tồn tại sau khi restart container.
- Object sao lưu xuất hiện đúng trong S3.
- Truy cập public trái phép bị từ chối.
- Khôi phục mẫu thực hiện thành công.

## Ảnh minh chứng cần bổ sung

1. MinIO bucket và object mẫu không nhạy cảm.
2. MinIO volume bền vững trong Docker Compose hoặc `docker volume ls`.
3. Amazon S3 bucket private đã bật Block Public Access.
4. Danh sách S3 object có thời gian sao lưu.
5. Cấu hình versioning, mã hóa hoặc lifecycle của dự án.

<!-- Thư mục đề xuất: /static/images/5-Workshop/5.7-Storage/ -->
