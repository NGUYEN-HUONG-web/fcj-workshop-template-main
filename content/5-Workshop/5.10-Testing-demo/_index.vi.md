---
title: "5.10. Dọn dẹp và hướng phát triển"
date: 2026-08-09
weight: 10
chapter: false
pre: " <b> 5.10. </b> "
---

## Dọn dẹp tài nguyên

Dọn dẹp theo thứ tự phụ thuộc để tránh bỏ sót tài nguyên:

1. Export dữ liệu cần giữ và xác nhận bản sao lưu cuối trên Amazon S3.
2. Dừng Docker Compose, xóa container tạm, image và volume không sử dụng.
3. Stop hoặc terminate EC2 theo quyết định lưu giữ.
4. Giải phóng Elastic IP không dùng, xóa EBS volume hoặc snapshot lỗi thời.
5. Xóa ECR image cũ hoặc áp dụng lifecycle policy.
6. Chỉ xóa S3 object hoặc bucket tạm sau khi xác nhận yêu cầu lưu dữ liệu.
7. Tắt hoặc xóa EventBridge schedule và Lambda không còn sử dụng.
8. Xóa CloudWatch Alarm, Dashboard, Log Group và SNS subscription không cần thiết.
9. Xóa IAM policy và role tạm sau khi tài nguyên phụ thuộc đã được loại bỏ.
10. Kiểm tra Billing, Cost Explorer và Resource Explorer để tìm tài nguyên còn sót.

![Tài nguyên đã được dọn dẹp](/images/5.10.png)

Xóa tài nguyên là thao tác không thể hoàn tác. Cần kiểm tra Resource ID, Region, trạng thái sao lưu và danh sách phụ thuộc trước mỗi thao tác.

## Bàn giao hệ thống

Ghi nhận image tag đang triển khai, phiên bản cấu hình môi trường, vị trí backup, tài nguyên giám sát, lịch tự động, giới hạn đã biết và quy trình khôi phục. Chuyển giao secret qua kênh bảo mật được phê duyệt, không đưa vào báo cáo hoặc Git repository.

## Hướng phát triển

- Chuyển database và object storage sang dịch vụ AWS managed khi phù hợp.
- Chạy ứng dụng trên nhiều Availability Zone sau Application Load Balancer.
- Bổ sung Auto Scaling, container orchestration và zero-downtime deployment.
- Dùng AWS Secrets Manager hoặc Systems Manager Parameter Store để xoay vòng secret.
- Bổ sung HTTPS với custom domain, AWS Certificate Manager và bảo vệ lớp biên.
- Cải thiện RAG bằng kiểm tra chất lượng tài liệu, hybrid search, reranking, citation và bộ dữ liệu đánh giá.
- Bổ sung phân quyền theo vai trò, audit log, quota và kiểm soát an toàn nội dung.
- Mở rộng learning analytics, bài kiểm tra thích ứng, gợi ý cá nhân hóa và dashboard cho giảng viên.
- Tự động hóa integration test, security test, load test, backup test và disaster-recovery test.
- Dùng Infrastructure as Code để tái tạo môi trường nhất quán.


Các hướng phát triển cần được ưu tiên dựa trên số liệu sử dụng, yêu cầu độ tin cậy, rủi ro bảo mật và ngân sách thực tế.
