---
title: "Nhật ký Tuần 5"
date: 2026-07-22
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Tìm hiểu cách tự động hóa các tác vụ vận hành trên AWS bằng AWS Lambda kết hợp với Amazon EventBridge.
* Xây dựng hệ thống giám sát trực quan bằng Grafana và tích hợp dữ liệu từ Amazon CloudWatch.
* Nắm được cách quản lý tài nguyên AWS thông qua Tags, Resource Groups và mô hình phân quyền Attribute-Based Access Control (ABAC).
* Thực hành quản trị EC2 bằng AWS Systems Manager (SSM) mà không cần sử dụng SSH.
* Làm quen với Infrastructure as Code (IaC) bằng cách triển khai hạ tầng với AWS CloudFormation.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - **Tự động hóa vận hành trên AWS** <br>&emsp; + Xây dựng hàm AWS Lambda bằng Python (boto3) để tự động khởi động và dừng EC2 theo lịch <br>&emsp; + Cấu hình Amazon EventBridge để kích hoạt Lambda theo thời gian định sẵn <br>&emsp; + Tích hợp Slack Webhook để gửi thông báo sau khi tác vụ hoàn thành <br>&emsp; + Theo dõi quá trình thực thi bằng Amazon CloudWatch Logs | 20/07/2026 | 20/07/2026 | <https://000022.awsstudygroup.com/> |
| 3 | - **Giám sát hệ thống với Grafana** <br>&emsp; + Khởi tạo Amazon EC2 và cài đặt Grafana Open Source <br>&emsp; + Kết nối Grafana với Amazon CloudWatch <br>&emsp; + Xây dựng Dashboard theo dõi CPU, Network và Disk của EC2 <br>&emsp; + Tùy chỉnh Dashboard để trực quan hóa hiệu năng hệ thống | 21/07/2026 | 21/07/2026 | <https://000029.awsstudygroup.com/> |
| 4 | - **Quản trị tài nguyên và phân quyền** <br>&emsp; + Áp dụng chiến lược gắn Tag cho tài nguyên (Environment, Owner, Cost Center...) <br>&emsp; + Tạo Resource Groups để quản lý tài nguyên theo nhóm <br>&emsp; + Tìm hiểu mô hình Attribute-Based Access Control (ABAC) <br>&emsp; + Cấu hình IAM Policy dựa trên Tag để kiểm soát quyền truy cập EC2 | 22/07/2026 | 22/07/2026 | <https://000027.awsstudygroup.com/><br><https://000028.awsstudygroup.com/> |
| 5 | - **Quản lý hệ thống với AWS Systems Manager** <br>&emsp; + Kết nối EC2 bằng Session Manager mà không cần mở cổng SSH <br>&emsp; + Cấu hình lưu Session Logs lên Amazon S3 <br>&emsp; + Thực hiện Run Command trên nhiều EC2 cùng lúc <br>&emsp; + Tìm hiểu Patch Manager và quy trình cập nhật hệ điều hành tự động | 23/07/2026 | 23/07/2026 | <https://000058.awsstudygroup.com/><br><https://000031.awsstudygroup.com/> |
| 6 | - **Hạ tầng dưới dạng mã (Infrastructure as Code)** <br>&emsp; + Viết CloudFormation Template bằng YAML hoặc JSON <br>&emsp; + Triển khai Amazon VPC và EC2 thông qua CloudFormation Stack <br>&emsp; + Tìm hiểu Parameters, Mappings, Resources và Outputs <br>&emsp; + Thực hành Drift Detection để phát hiện sự khác biệt giữa hạ tầng thực tế và template | 24/07/2026 | 24/07/2026 | <https://000037.awsstudygroup.com/> |

### Kết quả đạt được tuần 5:

* Xây dựng thành công quy trình tự động khởi động và dừng EC2 theo lịch bằng AWS Lambda kết hợp với Amazon EventBridge.
* Tích hợp Slack Webhook để nhận thông báo mỗi khi tác vụ tự động được thực hiện.
* Giảm thiểu các thao tác thủ công trong quá trình quản lý tài nguyên AWS.

* Triển khai Grafana trên Amazon EC2 và kết nối thành công với Amazon CloudWatch.
* Xây dựng Dashboard theo dõi CPU, Network, Disk và các chỉ số hiệu năng của EC2.
* Hiểu cách trực quan hóa dữ liệu nhằm hỗ trợ giám sát và phân tích hệ thống.

* Áp dụng Tag để phân loại tài nguyên theo môi trường, người quản lý và chi phí.
* Tạo Resource Groups giúp quản lý các tài nguyên liên quan một cách thuận tiện hơn.
* Thực hành cấu hình IAM Policy theo mô hình ABAC nhằm kiểm soát quyền truy cập dựa trên thuộc tính của tài nguyên.

* Sử dụng AWS Systems Manager Session Manager để quản trị EC2 an toàn mà không cần SSH.
* Cấu hình lưu nhật ký phiên làm việc lên Amazon S3 phục vụ kiểm tra và kiểm toán.
* Thực hiện Run Command để quản lý nhiều EC2 cùng lúc.
* Tìm hiểu quy trình cập nhật hệ điều hành và đánh giá tuân thủ bằng Patch Manager.

* Viết CloudFormation Template để tự động triển khai hạ tầng AWS.
* Triển khai Amazon VPC và EC2 thông qua CloudFormation Stack.
* Hiểu được vai trò của Parameters, Mappings, Resources và Outputs trong CloudFormation.
* Thực hành Drift Detection để kiểm tra sự khác biệt giữa cấu hình thực tế và cấu hình đã định nghĩa.

### Đánh giá tuần 5:

Trong tuần này, tôi đã nâng cao kỹ năng vận hành và quản trị hệ thống trên AWS thông qua việc tự động hóa các tác vụ quản trị bằng AWS Lambda và Amazon EventBridge. Việc tích hợp Slack Webhook giúp tôi theo dõi trạng thái của các tác vụ tự động một cách nhanh chóng và thuận tiện hơn.

Bên cạnh đó, tôi đã triển khai Grafana kết hợp với Amazon CloudWatch để xây dựng các Dashboard giám sát trực quan, từ đó hiểu rõ hơn về hiệu năng và trạng thái hoạt động của hạ tầng AWS. Tôi cũng nắm được cách tổ chức tài nguyên bằng Tags và Resource Groups, đồng thời áp dụng mô hình phân quyền ABAC để tăng cường tính bảo mật trong quản lý tài nguyên.

Ngoài ra, việc sử dụng AWS Systems Manager giúp tôi quản trị EC2 an toàn mà không cần SSH, trong khi AWS CloudFormation mang lại cái nhìn tổng quan về Infrastructure as Code, giúp quá trình triển khai hạ tầng trở nên nhất quán, dễ bảo trì và có thể tái sử dụng trong các dự án thực tế.
```