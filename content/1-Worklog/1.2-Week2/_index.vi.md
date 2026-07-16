---
title: "Week 2 Worklog"
date: 2026-06-26
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---


### Mục tiêu tuần 2:

* Nâng cao kỹ năng thực hành với AWS Cloud9 IDE và AWS CLI để quản lý tài nguyên AWS một cách hiệu quả.
* Học cách triển khai và quản trị cơ sở dữ liệu quan hệ bằng Amazon RDS, bao gồm các phương án sao lưu và khôi phục dữ liệu.
* Tìm hiểu kiến trúc có tính sẵn sàng cao (High Availability) và khả năng mở rộng (Scalability) thông qua Launch Template, Application Load Balancer (ALB) và Auto Scaling Group (ASG).

### Các công việc cần triển khai trong tuần này:
| Thứ | Công việc                                                                                                                                                                                   | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu                            |
| --- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------ | --------------- | ----------------------------------------- |
| 2   | - Tạo môi trường phát triển AWS Cloud9.<br>- Làm quen với giao diện Cloud9 và Terminal tích hợp.<br>- Thực hành các lệnh Linux cơ bản và quản lý tệp trên môi trường Cloud9.<br>- Sử dụng AWS CLI để tương tác và quản lý các dịch vụ AWS thông qua dòng lệnh.<br>- Dọn dẹp các tài nguyên đã tạo sau khi hoàn thành bài thực hành.                                                                                             | 29/06/2026   | 29/06/2026      | <https://000049.awsstudygroup.com/> |
| 3   | - Tìm hiểu dịch vụ lưu trữ đối tượng Amazon S3.<br>- Tạo và quản lý các S3 Bucket.<br>- Cấu hình Static Website Hosting trên Amazon S3.<br>- Quản lý Public Access Block và Bucket Policy.<br>- Tích hợp Amazon CloudFront để tối ưu tốc độ phân phối nội dung.<br>- Kích hoạt S3 Versioning và thực hành Cross-Region Replication (CRR) nhằm bảo vệ dữ liệu.                                           | 30/06/2026   | 30/06/2026      | <https://000057.awsstudygroup.com/> |
| 4   | - Chuẩn bị hạ tầng mạng cho Amazon RDS:<br>&emsp;+ Cấu hình VPC.<br>&emsp;+ Cấu hình Security Groups.<br>&emsp;+ Tạo DB Subnet Group.<br>- Khởi tạo EC2 Instance để triển khai ứng dụng.<br>- Tạo và cấu hình Amazon RDS Database Instance.<br>- Kết nối ứng dụng trên EC2 với Amazon RDS.<br>- Thực hành sao lưu và khôi phục cơ sở dữ liệu bằng Snapshot và các tính năng Recovery. | 01/07/2026   | 01/07/2026      | <https://000005.awsstudygroup.com/> |
| 5   | - Xây dựng kiến trúc có tính sẵn sàng cao (High Availability).<br>- Chuẩn bị hạ tầng gồm EC2, RDS và ứng dụng Web.<br>- Tạo Launch Template để chuẩn hóa cấu hình EC2.<br>- Cấu hình Application Load Balancer (ALB):<br>&emsp;+ Tạo Target Groups.<br>&emsp;+ Thiết lập Listener Rules.<br>- Kiểm tra việc phân phối lưu lượng giữa nhiều EC2 Instance.                  | 02/07/2026   | 02/07/2026      | <https://000006.awsstudygroup.com/> |
| 6   | - Tạo Auto Scaling Group (ASG) tích hợp với Application Load Balancer.<br>- Thực hành và kiểm tra các chiến lược mở rộng hệ thống:<br>&emsp;+ Manual Scaling.<br>&emsp;+ Scheduled Scaling.<br>&emsp;+ Dynamic Scaling dựa trên chỉ số CloudWatch.<br>&emsp;+ Predictive Scaling.<br>- Xóa toàn bộ tài nguyên AWS sau khi hoàn thành bài thực hành nhằm tránh phát sinh chi phí.                                                                                       | 03/07/2026   | 03/07/2026      | <https://000006.awsstudygroup.com/> |


### Kết quả đạt được tuần 2:
#### AWS Cloud9 & AWS CLI

* Thiết lập thành công AWS Cloud9 làm môi trường phát triển trên nền tảng đám mây.
* Nâng cao kỹ năng sử dụng AWS CLI để quản lý tài nguyên AWS mà không cần phụ thuộc hoàn toàn vào AWS Management Console.
* Thực hành tạo, chỉnh sửa và xóa tài nguyên AWS thông qua các lệnh dòng lệnh.
* Làm quen với các lệnh Linux và xây dựng các tập lệnh cơ bản trong môi trường Cloud9.

#### Lưu trữ và Phân phối nội dung

* Triển khai thành công website tĩnh bằng Amazon S3.
* Cấu hình Bucket Policy và Public Access để công khai nội dung một cách an toàn.
* Tích hợp Amazon CloudFront nhằm tăng tốc độ truy cập và phân phối nội dung trên phạm vi toàn cầu.
* Kích hoạt S3 Versioning để bảo vệ dữ liệu khỏi việc chỉnh sửa hoặc xóa nhầm.
* Triển khai Cross-Region Replication (CRR) nhằm tăng khả năng phục hồi dữ liệu và hỗ trợ chiến lược dự phòng.

#### Quản trị cơ sở dữ liệu

* Triển khai và cấu hình thành công cơ sở dữ liệu Amazon RDS.
* Kết nối ứng dụng đang chạy trên Amazon EC2 với cơ sở dữ liệu Amazon RDS.
* Thực hành các tác vụ quản trị cơ sở dữ liệu, bao gồm:
  * Tạo Database Snapshot.
  * Quản lý Backup.
  * Khôi phục dữ liệu theo thời điểm (Point-in-Time Recovery - PITR).

* Cấu hình Security Groups và DB Subnet Groups nhằm đảm bảo kết nối cơ sở dữ liệu an toàn.

#### Tính sẵn sàng cao và Khả năng mở rộng

* Thiết kế và triển khai kiến trúc web có tính sẵn sàng cao bằng:
  * Launch Template.
  * Application Load Balancer (ALB).
  * Auto Scaling Group (ASG).

* Cấu hình và kiểm thử nhiều chính sách mở rộng hệ thống:
  * Manual Scaling.
  * Scheduled Scaling.
  * Dynamic Scaling.
  * Predictive Scaling.

* Kiểm tra quá trình cân bằng tải và khả năng duy trì hoạt động của ứng dụng trong các tình huống mở rộng hệ thống.
* Hiểu rõ hơn các nguyên tắc thiết kế kiến trúc AWS nhằm xây dựng hệ thống có khả năng mở rộng, chịu lỗi và hoạt động ổn định.

---

### Đánh giá cuối tuần

Trong tuần thứ hai của kỳ thực tập, tôi tiếp tục mở rộng kiến thức và kỹ năng thực hành về AWS thông qua các dịch vụ phát triển, lưu trữ, cơ sở dữ liệu và kiến trúc có khả năng mở rộng. Việc sử dụng AWS Cloud9 kết hợp với AWS CLI giúp tôi nâng cao hiệu quả trong quá trình quản lý tài nguyên, đồng thời giảm sự phụ thuộc vào giao diện AWS Management Console.

Bên cạnh đó, việc triển khai website tĩnh trên Amazon S3 kết hợp với CloudFront giúp tôi hiểu rõ hơn về cách phân phối nội dung trên nền tảng đám mây. Thực hành với Amazon RDS giúp tôi nắm được quy trình triển khai, quản trị và khôi phục cơ sở dữ liệu, trong khi việc xây dựng kiến trúc sử dụng Application Load Balancer và Auto Scaling Group mang lại kinh nghiệm thực tế về thiết kế hệ thống có tính sẵn sàng cao và khả năng mở rộng. Những kiến thức và kỹ năng này là nền tảng quan trọng để tôi tiếp tục nghiên cứu các dịch vụ AWS nâng cao trong những tuần tiếp theo.