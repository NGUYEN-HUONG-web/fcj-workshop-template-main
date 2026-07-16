---
title: "Worklog Tuần 4"
date: 2026-07-15
weight: 4
chapter: false
pre: " <b> 1.4 </b> "
---

### Mục tiêu Tuần 4:

* Triển khai kiến trúc WordPress trên AWS theo mô hình sẵn sàng cao (High Availability - HA) và có khả năng mở rộng (Scalability).
* Tìm hiểu cách cấu hình Auto Scaling Group (ASG), Application Load Balancer (ALB) và Amazon CloudFront.
* Nắm vững quy trình di chuyển máy chủ bằng tính năng VM Import/Export.
* Thực hiện di chuyển cơ sở dữ liệu không đồng nhất bằng AWS Schema Conversion Tool (SCT) và AWS Database Migration Service (DMS).
* Nghiên cứu các dịch vụ di chuyển nâng cao của AWS như AWS Migration Hub, AWS Application Migration Service (MGN) và AWS DataSync.

### Công việc thực hiện trong tuần:

| Ngày | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --------- | ------------ | ---------------- | ------------------ |
| 2 | - **WordPress trên AWS – Phần 1** <br>&emsp; + Chuẩn bị VPC, Public/Private Subnet và Security Group <br>&emsp; + Triển khai Amazon RDS Multi-AZ <br>&emsp; + Khởi tạo EC2 và cài đặt WordPress <br>&emsp; + Kết nối WordPress với Amazon RDS | 29/09/2025 | 29/09/2025 | <https://000021.awsstudygroup.com/> |
| 3 | - **WordPress trên AWS – Phần 2** <br>&emsp; + Tạo AMI từ EC2 đã cấu hình <br>&emsp; + Cấu hình Launch Template và Auto Scaling Group <br>&emsp; + Triển khai Application Load Balancer <br>&emsp; + Tích hợp Amazon CloudFront <br>&emsp; + Thực hiện Snapshot và Restore cho RDS <br>&emsp; + Dọn dẹp tài nguyên AWS | 30/09/2025 | 30/09/2025 | <https://000021.awsstudygroup.com/> |
| 4 | - **Di chuyển máy chủ (VM Import/Export)** <br>&emsp; + Chuẩn bị máy ảo mô phỏng môi trường On-Premises <br>&emsp; + Tải ảnh máy ảo lên Amazon S3 <br>&emsp; + Import VM thành AMI và khởi tạo EC2 <br>&emsp; + Export EC2 trở lại thành ảnh máy ảo <br>&emsp; + Cấu hình IAM Role và quyền truy cập S3 | 01/10/2025 | 01/10/2025 | <https://000014.awsstudygroup.com/> |
| 5 | - **Di chuyển cơ sở dữ liệu** <br>&emsp; + Chuẩn bị cơ sở dữ liệu nguồn và đích <br>&emsp; + Chuyển đổi Schema bằng AWS SCT <br>&emsp; + Cấu hình AWS DMS Replication Instance <br>&emsp; + Tạo Endpoint và Migration Task <br>&emsp; + Thực hiện Full Load kết hợp Change Data Capture (CDC) <br>&emsp; + Tìm hiểu AWS DMS Serverless | 02/10/2025 | 02/10/2025 | <https://000043.awsstudygroup.com/> |
| 6 | - **Giám sát và các dịch vụ di chuyển nâng cao** <br>&emsp; + Giám sát DMS bằng Amazon CloudWatch <br>&emsp; + Phân tích Task Logs và Table Statistics <br>&emsp; + Khắc phục các sự cố trong quá trình Migration <br>&emsp; + Tìm hiểu AWS Migration Hub, AWS MGN, AWS DataSync và di chuyển Container lên Amazon EKS | 03/10/2025 | 03/10/2025 | <https://000043.awsstudygroup.com/> |

### Thành tựu Tuần 4:

* Triển khai thành công kiến trúc WordPress có tính sẵn sàng cao bằng cách sử dụng:
  * Amazon EC2
  * Amazon RDS Multi-AZ
  * Application Load Balancer (ALB)
  * Auto Scaling Group (ASG)
  * Amazon CloudFront

* Hiểu cách Auto Scaling tự động tăng hoặc giảm số lượng EC2 dựa trên nhu cầu của ứng dụng.

* Cấu hình Application Load Balancer để phân phối lưu lượng truy cập đến các EC2 đang hoạt động ổn định.

* Cải thiện hiệu suất truy cập website bằng cách tích hợp Amazon CloudFront làm mạng phân phối nội dung (CDN).

* Thực hành sao lưu và khôi phục dữ liệu bằng Amazon RDS Snapshot và Restore.

* Có kinh nghiệm thực hành quy trình VM Import/Export, bao gồm:
  * Import máy ảo từ môi trường On-Premises lên AWS
  * Tạo AMI từ máy ảo đã Import
  * Khởi tạo EC2 từ AMI
  * Export EC2 trở lại thành ảnh máy ảo để sử dụng ngoài AWS

* Hiểu cách cấu hình IAM Role và quyền truy cập Amazon S3 phục vụ quá trình di chuyển dữ liệu an toàn.

* Thực hiện di chuyển cơ sở dữ liệu không đồng nhất bằng:
  * AWS Schema Conversion Tool (SCT)
  * AWS Database Migration Service (DMS)

* Cấu hình thành công:
  * Replication Instance
  * Source Endpoint và Target Endpoint
  * Migration Task
  * Full Load kết hợp Change Data Capture (CDC)

* Tìm hiểu AWS DMS Serverless và cơ chế tự động mở rộng tài nguyên trong quá trình di chuyển dữ liệu.

* Biết cách giám sát quá trình Migration thông qua:
  * Amazon CloudWatch Metrics
  * Table Statistics
  * Task Logs

* Nghiên cứu các dịch vụ di chuyển nâng cao của AWS gồm:
  * AWS Migration Hub
  * AWS Application Migration Service (MGN)
  * AWS DataSync
  * Di chuyển Container lên Amazon EKS
  ### Đánh giá Tuần 4:

Trong tuần 4, em đã có cơ hội thực hành triển khai kiến trúc WordPress có tính sẵn sàng cao và khả năng mở rộng trên AWS bằng Amazon EC2, RDS Multi-AZ, Auto Scaling Group, Application Load Balancer và Amazon CloudFront.

Bên cạnh đó, em cũng nắm được quy trình di chuyển máy chủ và cơ sở dữ liệu bằng VM Import/Export, AWS Schema Conversion Tool (SCT) và AWS Database Migration Service (DMS). Đồng thời, em tìm hiểu thêm về AWS Migration Hub, AWS MGN và AWS DataSync, giúp hiểu rõ hơn về các giải pháp di chuyển và triển khai hệ thống trên AWS.