---
title: "Worklog Tuần 3"
date: 2026-07-11
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu Tuần 3

* Triển khai hệ thống giám sát và quan sát bằng Amazon CloudWatch (Metrics, Logs, Alarms và Dashboards).
* Xây dựng kiến trúc Hybrid DNS với Route 53 Resolver và Microsoft Active Directory.
* Nâng cao kỹ năng sử dụng AWS CLI để tự động hóa việc quản lý các dịch vụ Storage, Networking, IAM và Compute.

### Công việc thực hiện trong tuần

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Cấu hình CloudWatch Metrics, Logs Insights, Alarms và Dashboards.<br>- **Thực hành:** Giám sát hiệu năng EC2 và tạo cảnh báo khi CPU Utilization vượt ngưỡng. | 06/07/2026 | 06/07/2026 | <https://000008.awsstudygroup.com/> |
| 3 | - Triển khai Microsoft Active Directory.<br>- Cấu hình Remote Desktop Gateway (RDGW).<br>- Thiết lập Route 53 Resolver (Inbound/Outbound Endpoints và Resolver Rules).<br>- Kiểm tra khả năng phân giải Hybrid DNS. | 07/07/2026 | 07/07/2026 | <https://000010.awsstudygroup.com/> |
| 4 | - Cài đặt và cấu hình AWS CLI v2.<br>- Quản lý Amazon S3 và Amazon SNS bằng AWS CLI.<br>- Tìm hiểu các định dạng đầu ra và tùy chọn lọc dữ liệu của AWS CLI. | 08/07/2026 | 08/07/2026 | <https://000011.awsstudygroup.com/> |
| 5 | - Quản lý người dùng và vai trò IAM bằng AWS CLI.<br>- Cấu hình xác thực MFA.<br>- Triển khai các tài nguyên mạng VPC.<br>- Khởi tạo EC2 bằng AWS CLI. | 09/07/2026 | 09/07/2026 | <https://000011.awsstudygroup.com/> |
| 6 | - Khắc phục các lỗi thường gặp của AWS CLI.<br>- Cấu hình thông tin xác thực SAML.<br>- Dọn dẹp tài nguyên AWS bằng AWS CLI. | 10/07/2026 | 10/07/2026 | <https://000011.awsstudygroup.com/> |

### Kết quả đạt được trong Tuần 3

* Triển khai thành công hệ thống giám sát bằng Amazon CloudWatch.
  * Cấu hình Metrics, Logs, Alarms và Dashboards.
  * Giám sát hiệu năng EC2 và thiết lập cảnh báo CPU Utilization.

* Xây dựng thành công môi trường Hybrid DNS bằng cách:
  * Triển khai Microsoft Active Directory.
  * Cấu hình Route 53 Resolver.
  * Kiểm tra khả năng phân giải DNS giữa môi trường on-premises và AWS.

* Nâng cao kỹ năng sử dụng AWS CLI, bao gồm:
  * Quản lý Amazon S3 và Amazon SNS.
  * Tạo và quản lý người dùng, vai trò IAM.
  * Triển khai các tài nguyên mạng VPC.
  * Khởi tạo và quản lý EC2 bằng AWS CLI.

* Rèn luyện kỹ năng xử lý các lỗi thường gặp của AWS CLI liên quan đến:
  * Thông tin xác thực (Credentials) và quyền truy cập (Permissions).
  * Xác thực MFA và SAML.
  * Cấu hình CLI và các lỗi khi gọi AWS API.

* Dọn dẹp toàn bộ tài nguyên AWS bằng AWS CLI nhằm tránh phát sinh chi phí không cần thiết.

### Đánh giá tuần

Trong tuần này, em đã hiểu rõ hơn về giám sát hệ thống trên AWS, mạng lai (Hybrid Networking) và quản trị hạ tầng bằng dòng lệnh. Thông qua việc thực hành với Amazon CloudWatch, em học được cách theo dõi hiệu năng tài nguyên và chủ động phát hiện các sự cố tiềm ẩn. Việc cấu hình Hybrid DNS bằng Route 53 Resolver kết hợp với Microsoft Active Directory giúp em hiểu rõ hơn về mô hình tích hợp giữa hệ thống on-premises và AWS. Bên cạnh đó, em cũng tự tin hơn khi sử dụng AWS CLI để tự động hóa việc triển khai và quản lý hạ tầng thay vì chỉ thao tác trên AWS Management Console. Nhìn chung, các bài thực hành trong tuần đã giúp em nâng cao kiến thức chuyên môn cũng như kỹ năng giải quyết vấn đề trong môi trường AWS.