---
title: "Nhật ký công việc Tuần 3"
date: 2026-07-06
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3

* Triển khai hoạt động giám sát bằng Amazon CloudWatch.
* Cấu hình CloudWatch Metrics, Logs, Alarms và Dashboards.
* Tìm hiểu Hybrid DNS với Route 53 Resolver và Microsoft Active Directory.
* Thực hành quản lý tài nguyên bằng AWS CLI.
* Viết các lệnh và Script cơ bản để tự động hóa công việc quản trị.

### Công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| **2** | - Tìm hiểu CloudWatch Metrics, Logs và Namespaces.<br>- Theo dõi CPUUtilization, NetworkIn, NetworkOut và StatusCheckFailed của EC2.<br>- Xem DatabaseConnections và FreeStorageSpace của RDS.<br>- Thực hành truy vấn Log bằng CloudWatch Logs Insights. | 06/07/2026 | 06/07/2026 | <https://000008.awsstudygroup.com/> |
| **3** | - Tạo CloudWatch Alarm cho chỉ số CPU của EC2.<br>- Tạo Amazon SNS Topic và Email Subscription.<br>- Cấu hình gửi cảnh báo khi chỉ số vượt ngưỡng.<br>- Xây dựng CloudWatch Dashboard tổng hợp EC2 và RDS Metrics. | 07/07/2026 | 07/07/2026 | <https://000008.awsstudygroup.com/> |
| **4** | - Tìm hiểu DNS và mô hình Hybrid DNS.<br>- Triển khai Microsoft Active Directory và Remote Desktop Gateway.<br>- Tạo Route 53 Private Hosted Zone.<br>- Kiểm tra khả năng phân giải tên miền trong VPC. | 08/07/2026 | 08/07/2026 | <https://000010.awsstudygroup.com/> |
| **5** | - Tạo Route 53 Resolver Inbound Endpoint và Outbound Endpoint.<br>- Tạo Resolver Rule và liên kết Rule với VPC.<br>- Kiểm tra phân giải tên miền từ AWS đến hệ thống bên ngoài và theo chiều ngược lại. | 09/07/2026 | 09/07/2026 | <https://000010.awsstudygroup.com/> |
| **6** | - Cài đặt và cấu hình AWS CLI.<br>- Kiểm tra danh tính bằng `aws sts get-caller-identity`.<br>- Thực hành lệnh quản lý S3, IAM, EC2 và VPC.<br>- Viết Script cơ bản để kiểm tra, khởi động và dừng EC2.<br>- Tổng kết nội dung tuần 3. | 10/07/2026 | 10/07/2026 | <https://000011.awsstudygroup.com/> |

### Kết quả đạt được

* Theo dõi được các chỉ số hoạt động của EC2 và RDS.
* Tạo CloudWatch Alarm và nhận thông báo qua Amazon SNS.
* Xây dựng Dashboard theo dõi tài nguyên tập trung.
* Sử dụng Logs Insights để truy vấn và phân tích Log.
* Hiểu vai trò của Route 53 Resolver trong Hybrid DNS.
* Phân biệt được Inbound Endpoint và Outbound Endpoint.
* Cài đặt và sử dụng AWS CLI để quản lý tài nguyên.
* Viết được các lệnh hỗ trợ kiểm tra trạng thái EC2 và S3.

### Khó khăn và cách khắc phục

| Khó khăn | Cách khắc phục |
| --- | --- |
| CloudWatch Alarm ở trạng thái `INSUFFICIENT_DATA` | Chờ hệ thống thu thập đủ dữ liệu và kiểm tra Period, Evaluation Periods. |
| SNS không gửis. email | Kiểm tra email xác nhận Subscription và thư mục Spam. |
| Resolver không phân giải được tên miền | Kiểm tra Security Group, Resolver Rule, DNS Server IP và liên kết VPC. |
| AWS CLI báo `Unable to locate credentials` | Chạy `aws configure` và kiểm tra lại Access Key, Secret Key và Region. |

---

### Đánh giá tuần

Tuần 3 giúp tôi hiểu rõ tầm quan trọng của Monitoring và Observability trong vận hành Cloud. CloudWatch không chỉ hiển thị số liệu mà còn hỗ trợ cảnh báo và phân tích sự cố thông qua Metrics, Logs và Alarms.

Hybrid DNS là phần kiến thức khó nhất trong tuần vì liên quan đến Active Directory, Route 53 Resolver và cấu hình mạng. AWS CLI giúp tôi rút ngắn thời gian thực hiện các công việc lặp lại, nhưng cũng yêu cầu cẩn thận với quyền IAM và thông tin xác thực.