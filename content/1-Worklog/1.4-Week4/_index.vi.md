---
title: "Nhật ký công việc Tuần 4"
date: 2026-07-15
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Triển khai kiến trúc WordPress trên AWS theo mô hình sẵn sàng cao (High Availability) và có khả năng mở rộng (Scalability).
* Tìm hiểu và cấu hình Auto Scaling Group (ASG), Application Load Balancer (ALB) và Amazon CloudFront.
* Nắm được quy trình di chuyển máy chủ bằng VM Import/Export.
* Thực hành di chuyển cơ sở dữ liệu khác hệ quản trị bằng AWS Schema Conversion Tool (SCT) và AWS Database Migration Service (DMS).
* Khám phá các dịch vụ hỗ trợ di chuyển nâng cao như AWS Migration Hub, AWS Application Migration Service (AWS MGN) và AWS DataSync.

### Các công việc thực hiện trong tuần:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| 2 | - **Triển khai WordPress trên AWS – Phần 1** <br>&emsp; + Chuẩn bị VPC, Public Subnet, Private Subnet và Security Group <br>&emsp; + Triển khai Amazon RDS Multi-AZ <br>&emsp; + Khởi tạo Amazon EC2 và cài đặt WordPress <br>&emsp; + Kết nối WordPress với Amazon RDS | 12/07/2026 | 12/07/2026 | <https://000021.awsstudygroup.com/> |
| 3 | - **Triển khai WordPress trên AWS – Phần 2** <br>&emsp; + Tạo AMI từ EC2 đã cấu hình <br>&emsp; + Cấu hình Launch Template và Auto Scaling Group <br>&emsp; + Triển khai Application Load Balancer (ALB) <br>&emsp; + Tích hợp Amazon CloudFront <br>&emsp; + Thực hành Snapshot và Restore Amazon RDS <br>&emsp; + Dọn dẹp tài nguyên AWS sau khi hoàn thành | 13/07/2026 | 13/07/2026 | <https://000021.awsstudygroup.com/> |
| 4 | - **Di chuyển máy chủ (VM Import/Export)** <br>&emsp; + Chuẩn bị máy ảo On-Premises <br>&emsp; + Tải tệp máy ảo lên Amazon S3 <br>&emsp; + Import máy ảo thành AMI và khởi tạo EC2 <br>&emsp; + Export EC2 trở lại định dạng máy ảo <br>&emsp; + Cấu hình IAM Role và quyền truy cập Amazon S3 | 14/07/2026 | 14/07/2026 | <https://000014.awsstudygroup.com/> |
| 5 | - **Di chuyển cơ sở dữ liệu** <br>&emsp; + Chuẩn bị cơ sở dữ liệu nguồn và đích <br>&emsp; + Chuyển đổi Schema bằng AWS Schema Conversion Tool (SCT) <br>&emsp; + Cấu hình AWS DMS Replication Instance <br>&emsp; + Tạo Source Endpoint, Target Endpoint và Migration Task <br>&emsp; + Thực hiện Full Load và Change Data Capture (CDC) <br>&emsp; + Tìm hiểu AWS DMS Serverless | 15/07/2026 | 15/07/2026 | <https://000043.awsstudygroup.com/> |
| 6 | - **Giám sát quá trình Migration và các dịch vụ nâng cao** <br>&emsp; + Giám sát AWS DMS bằng Amazon CloudWatch <br>&emsp; + Phân tích Task Logs và Table Statistics <br>&emsp; + Khắc phục sự cố trong quá trình di chuyển dữ liệu <br>&emsp; + Tìm hiểu AWS Migration Hub, AWS Application Migration Service (AWS MGN), AWS DataSync và di chuyển container lên Amazon EKS | 16/07/2026 | 16/07/2026 | <https://000043.awsstudygroup.com/> |

### Kết quả đạt được trong tuần 4:

* Hoàn thành triển khai kiến trúc WordPress có tính sẵn sàng cao trên AWS với các dịch vụ:
  * Amazon EC2
  * Amazon RDS Multi-AZ
  * Application Load Balancer (ALB)
  * Auto Scaling Group (ASG)
  * Amazon CloudFront

* Hiểu được cơ chế Auto Scaling giúp tự động tăng hoặc giảm số lượng EC2 Instance theo lưu lượng truy cập.

* Cấu hình thành công Application Load Balancer để phân phối lưu lượng truy cập đến các EC2 Instance đang hoạt động.

* Tích hợp Amazon CloudFront nhằm cải thiện tốc độ truy cập và tối ưu hiệu năng website thông qua mạng phân phối nội dung (CDN).

* Thực hành sao lưu và khôi phục cơ sở dữ liệu bằng Amazon RDS Snapshot và Restore.

* Thực hành quy trình di chuyển máy chủ với VM Import/Export:
  * Import máy ảo từ môi trường On-Premises lên AWS.
  * Tạo Amazon Machine Image (AMI) từ máy ảo đã import.
  * Khởi chạy EC2 từ AMI.
  * Export EC2 trở lại định dạng máy ảo.

* Nắm được cách cấu hình IAM Role và quyền truy cập Amazon S3 phục vụ quá trình di chuyển dữ liệu.

* Thực hiện di chuyển cơ sở dữ liệu khác hệ quản trị bằng:
  * AWS Schema Conversion Tool (SCT)
  * AWS Database Migration Service (DMS)

* Cấu hình thành công:
  * Replication Instance
  * Source Endpoint và Target Endpoint
  * Migration Task
  * Full Load kết hợp Change Data Capture (CDC)

* Tìm hiểu AWS DMS Serverless và hiểu được cơ chế tự động mở rộng tài nguyên trong quá trình migration.

* Biết cách theo dõi tiến trình di chuyển dữ liệu thông qua:
  * Amazon CloudWatch Metrics
  * Table Statistics
  * Task Logs

* Tìm hiểu thêm các dịch vụ hỗ trợ Migration trên AWS:
  * AWS Migration Hub
  * AWS Application Migration Service (AWS MGN)
  * AWS DataSync
  * Di chuyển container lên Amazon EKS

### Đánh giá tuần 4:

Trong tuần này, tôi đã có cơ hội triển khai một kiến trúc WordPress theo mô hình High Availability và Scalability trên AWS, sử dụng các dịch vụ như Amazon EC2, Amazon RDS Multi-AZ, Auto Scaling Group, Application Load Balancer và Amazon CloudFront. Thông qua các bài thực hành, tôi hiểu rõ hơn về cách xây dựng một hệ thống có khả năng chịu lỗi, tự động mở rộng và đáp ứng yêu cầu triển khai trong môi trường thực tế.

Bên cạnh đó, tôi cũng thực hành quy trình di chuyển máy chủ và cơ sở dữ liệu bằng VM Import/Export, AWS Schema Conversion Tool (SCT) và AWS Database Migration Service (DMS). Đồng thời, việc tìm hiểu AWS Migration Hub, AWS MGN và AWS DataSync giúp tôi có cái nhìn tổng quan hơn về các giải pháp Migration trên AWS cũng như quy trình chuyển đổi hệ thống từ môi trường On-Premises lên nền tảng đám mây.