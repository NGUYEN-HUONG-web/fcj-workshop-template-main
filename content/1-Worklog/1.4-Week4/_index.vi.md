---
title: "Nhật ký công việc Tuần 4"
date: 2026-07-13
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4

* Xây dựng ứng dụng WordPress theo kiến trúc sẵn sàng cao.
* Tìm hiểu các chiến lược di chuyển máy chủ và dữ liệu lên AWS.
* Thực hành AWS Schema Conversion Tool và AWS Database Migration Service.
* Phân biệt Full Load và Change Data Capture.
* Tìm hiểu AWS DataSync, Application Migration Service và AWS Outposts.

### Công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| **2** | - Thiết kế kiến trúc WordPress có tính sẵn sàng cao.<br>- Xác định vai trò của ALB, Auto Scaling, RDS Multi-AZ, S3 và CloudFront.<br>- Chuẩn bị VPC, Public Subnet, Private Subnet và Security Group. | 13/07/2026 | 13/07/2026 | <https://000006.awsstudygroup.com/> |
| **3** | - Cài đặt WordPress trên EC2.<br>- Kết nối WordPress với Amazon RDS.<br>- Tạo Launch Template, Target Group và Application Load Balancer.<br>- Cấu hình Auto Scaling Group trên hai Availability Zone.<br>- Kiểm tra khả năng chịu lỗi. | 14/07/2026 | 14/07/2026 | <https://000006.awsstudygroup.com/> |
| **4** | - Tìm hiểu VM Import/Export và các định dạng máy ảo được hỗ trợ.<br>- Chuẩn bị S3 Bucket và IAM Role phục vụ Migration.<br>- Nghiên cứu quy trình chuyển máy ảo hiện có thành AMI trên AWS. | 15/07/2026 | 15/07/2026 | <https://docs.aws.amazon.com/vm-import/latest/userguide/what-is-vmimport.html> |
| **5** | - Cài đặt AWS Schema Conversion Tool.<br>- Đánh giá khả năng tương thích của Database Schema.<br>- Tạo DMS Replication Instance, Source Endpoint và Target Endpoint.<br>- Thực hành Full Load và Change Data Capture. | 16/07/2026 | 16/07/2026 | <https://docs.aws.amazon.com/dms/> |
| **6** | - Tìm hiểu AWS DataSync, Application Migration Service và AWS Outposts.<br>- So sánh các dịch vụ Migration theo loại dữ liệu và hệ thống.<br>- Kiểm tra dữ liệu sau di chuyển.<br>- Tổng kết nội dung tuần 4. | 17/07/2026 | 17/07/2026 | <https://aws.amazon.com/cloud-data-migration/> |

### Kết quả đạt được

* Thiết kế được kiến trúc WordPress có tính sẵn sàng cao.
* Triển khai WordPress kết hợp EC2, ALB, Auto Scaling và RDS.
* Hiểu cách CloudFront hỗ trợ phân phối nội dung và giảm tải cho hệ thống.
* Nắm được quy trình VM Import/Export.
* Biết sử dụng AWS SCT để đánh giá và chuyển đổi Schema.
* Hiểu vai trò của Replication Instance và Endpoint trong AWS DMS.
* Phân biệt Full Load và Change Data Capture.
* Hiểu trường hợp sử dụng DataSync, MGN và AWS Outposts.

### Khó khăn và cách khắc phục

| Khó khăn | Cách khắc phục |
| --- | --- |
| WordPress không kết nối được RDS | Kiểm tra DB Endpoint, thông tin đăng nhập và Security Group cổng 3306. |
| Target trong ALB không Healthy | Kiểm tra Health Check Path, cổng HTTP và trạng thái Web Server. |
| DMS Endpoint Test thất bại | Kiểm tra Route Table, Security Group, Database Credentials và quyền IAM. |
| Schema chuyển đổi không hoàn toàn tương thích | Xem Assessment Report của AWS SCT và điều chỉnh các đối tượng thủ công. |

---

### Đánh giá tuần

Tuần 4 giúp tôi kết hợp kiến thức về Compute, Network, Database và Load Balancing để tạo một kiến trúc hoàn chỉnh. Tôi hiểu rằng khả năng sẵn sàng cao cần được thiết kế đồng bộ ở cả tầng ứng dụng và cơ sở dữ liệu.

Các bài thực hành Migration cho thấy việc di chuyển hệ thống không chỉ đơn giản là sao chép dữ liệu. Người triển khai phải đánh giá khả năng tương thích, bảo mật kết nối, kiểm tra tính toàn vẹn dữ liệu và xây dựng kế hoạch hạn chế thời gian gián đoạn.