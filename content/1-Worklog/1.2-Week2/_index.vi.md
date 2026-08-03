---
title: "Nhật ký công việc Tuần 2"
date: 2026-06-29
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2

* Tìm hiểu và thực hành với Amazon S3, Amazon EC2 và Amazon RDS.
* Triển khai website tĩnh bằng Amazon S3.
* Triển khai máy chủ Linux và Windows trên Amazon EC2.
* Tạo cơ sở dữ liệu MySQL bằng Amazon RDS.
* Hiểu kiến trúc sẵn sàng cao với Application Load Balancer và Auto Scaling Group.

### Công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| **2** | - Tìm hiểu Amazon S3, Bucket, Object, Object Key và Storage Class.<br>- Tạo S3 Bucket và thực hành tải lên, tải xuống, sao chép và xóa Object.<br>- Bật S3 Versioning và thử khôi phục phiên bản cũ.<br>- Tìm hiểu Cross-Region Replication. | 29/06/2026 | 29/06/2026 | <https://000057.awsstudygroup.com/> |
| **3** | - Cấu hình S3 Static Website Hosting.<br>- Tải lên các tệp HTML, CSS, JavaScript và hình ảnh.<br>- Thiết lập Bucket Policy cho phép truy cập website.<br>- Tìm hiểu Amazon CloudFront và vai trò của CDN trong phân phối nội dung. | 30/06/2026 | 30/06/2026 | <https://000057.awsstudygroup.com/> |
| **4** | - Tìm hiểu AMI, Instance Type, Key Pair, Security Group và EBS.<br>- Khởi tạo EC2 chạy Amazon Linux và Windows Server.<br>- Kết nối máy chủ bằng SSH và RDP.<br>- Cài đặt LAMP trên Linux và XAMPP trên Windows.<br>- Triển khai trang web mẫu trên EC2. | 01/07/2026 | 01/07/2026 | <https://000004.awsstudygroup.com/> |
| **5** | - Tìm hiểu Amazon RDS và các Database Engine được hỗ trợ.<br>- Tạo RDS MySQL, DB Subnet Group và Security Group.<br>- Kết nối từ EC2 đến RDS qua cổng 3306.<br>- Tìm hiểu Automated Backup, Snapshot, Read Replica và Multi-AZ. | 02/07/2026 | 02/07/2026 | <https://000005.awsstudygroup.com/> |
| **6** | - Tạo Launch Template từ cấu hình EC2.<br>- Tạo Target Group và Application Load Balancer.<br>- Triển khai Auto Scaling Group trên nhiều Availability Zone.<br>- Kiểm tra Health Check và khả năng phân phối lưu lượng.<br>- Thử nghiệm thay đổi Desired Capacity. | 03/07/2026 | 03/07/2026 | <https://000006.awsstudygroup.com/> |

### Kết quả đạt được

* Tạo và quản lý thành công S3 Bucket.
* Triển khai Static Website Hosting trên Amazon S3.
* Hiểu S3 Versioning, Bucket Policy và Cross-Region Replication.
* Khởi tạo và kết nối thành công EC2 Linux và Windows.
* Cài đặt môi trường LAMP và XAMPP phục vụ triển khai ứng dụng.
* Tạo RDS MySQL và kết nối cơ sở dữ liệu từ EC2.
* Hiểu sự khác nhau giữa RDS Snapshot, Backup, Read Replica và Multi-AZ.
* Xây dựng kiến trúc có ALB và Auto Scaling trên nhiều Availability Zone.

### Khó khăn và cách khắc phục

| Khó khăn | Cách khắc phục |
| --- | --- |
| Website S3 trả về lỗi `403 Forbidden` | Kiểm tra Block Public Access, Bucket Policy và quyền `s3:GetObject`. |
| Không thể SSH vào EC2 | Kiểm tra Key Pair, Public IPv4, Route Table và Inbound Rule cổng 22. |
| EC2 không kết nối được RDS | Kiểm tra RDS Endpoint và cho phép Security Group của EC2 truy cập cổng 3306. |
| Target hiển thị trạng thái Unhealthy | Kiểm tra Health Check Path, cổng ứng dụng và Security Group của EC2. |

---

### Đánh giá tuần

Tuần 2 giúp tôi hiểu cách kết hợp dịch vụ lưu trữ, máy chủ ảo và cơ sở dữ liệu để triển khai một ứng dụng trên AWS. Thay vì chỉ tìm hiểu từng dịch vụ riêng lẻ, tôi đã bước đầu hình dung được luồng kết nối giữa S3, EC2 và RDS.

Việc thực hành với Application Load Balancer và Auto Scaling Group giúp tôi hiểu rằng một hệ thống sẵn sàng cao không nên phụ thuộc vào một máy chủ duy nhất. Hệ thống cần được triển khai trên nhiều Availability Zone để tăng khả năng chịu lỗi và mở rộng.