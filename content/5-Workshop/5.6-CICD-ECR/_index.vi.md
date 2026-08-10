---
title: "5.6. CI/CD với GitHub Actions và ECR"
date: 2026-08-09
weight: 6
chapter: false
pre: " <b> 5.6. </b> "
---

## Mục tiêu pipeline

Pipeline tạo quy trình phân phối có thể lặp lại và truy vết. Mỗi lần build thành công sinh ra Docker image có phiên bản trên Amazon ECR, thay vì build trực tiếp trên máy chủ.

## Chuẩn bị ECR

Tạo private ECR repository, bật image scanning khi phù hợp và cấu hình lifecycle policy để xóa image cũ. Chỉ cấp cho workflow quyền cần thiết để push image.

![Docker image và tag trong Amazon ECR](/images/5-Workshop/5.6-CICD-ECR/ecr-images.png)

## GitHub Actions workflow

Workflow điển hình gồm:

1. Checkout mã nguồn.
2. Kiểm tra dependency hoặc mã nguồn.
3. Xác thực AWS bằng credential ngắn hạn hoặc OIDC.
4. Đăng nhập Amazon ECR.
5. Build Docker image.
6. Gắn tag theo commit SHA hoặc release.
7. Push image lên ECR.
8. Deploy EC2 nếu workflow thực tế đã triển khai bước này.

Lưu cấu hình trong GitHub Secrets hoặc Variables. Ưu tiên OIDC thay cho Access Key dài hạn.

![GitHub Actions build và push image thành công](/images/5-Workshop/5.6-CICD-ECR/github-actions-success.png)

## Kiểm tra triển khai

Xác nhận workflow thành công, tag và digest đúng đã tồn tại trong ECR, EC2 chạy đúng phiên bản image. Giữ lại tag ổn định gần nhất để rollback khi phiên bản mới lỗi.

![Image tag đang được triển khai trên EC2](/images/5-Workshop/5.6-CICD-ECR/deployed-image-tag.png)

## Ảnh minh chứng cần bổ sung

1. ECR repository chứa image và tag của ứng dụng.
2. Chi tiết image hiển thị digest và thời gian push.
3. GitHub Actions workflow chạy thành công.
4. Các bước build và push image lên ECR.
5. EC2 chạy đúng image tag nếu đã có tự động deploy.

<!-- Thư mục đề xuất: /static/images/5-Workshop/5.6-CICD-ECR/ -->
