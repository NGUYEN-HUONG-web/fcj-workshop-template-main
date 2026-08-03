---
title: "Nhật ký công việc Tuần 5"
date: 2026-07-20
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5

* Hiểu khái niệm Infrastructure as Code và lợi ích của việc tự động hóa hạ tầng.
* Tìm hiểu cấu trúc AWS CloudFormation Template.
* Triển khai hạ tầng AWS bằng YAML.
* Thực hành cập nhật Stack bằng Change Set.
* Tự động khởi động và dừng tài nguyên để tối ưu chi phí.

### Công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| **2** | - Tìm hiểu Infrastructure as Code và Declarative Configuration.<br>- So sánh triển khai thủ công với triển khai bằng CloudFormation.<br>- Làm quen cú pháp YAML và JSON.<br>- Tìm hiểu vòng đời của CloudFormation Stack. | 20/07/2026 | 20/07/2026 | <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/Welcome.html> |
| **3** | - Tìm hiểu các thành phần Parameters, Resources, Outputs, Mappings và Conditions.<br>- Viết Template tạo VPC, Public Subnet, Internet Gateway và Route Table.<br>- Kiểm tra cú pháp và các quan hệ phụ thuộc. | 21/07/2026 | 21/07/2026 | <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-anatomy.html> |
| **4** | - Bổ sung Security Group, IAM Role và EC2 vào Template.<br>- Sử dụng User Data để tự động cài đặt Web Server.<br>- Kiểm tra Template bằng AWS CLI.<br>- Triển khai và theo dõi Stack Events. | 22/07/2026 | 22/07/2026 | <https://docs.aws.amazon.com/cli/latest/reference/cloudformation/> |
| **5** | - Tạo Change Set để xem trước thay đổi.<br>- Cập nhật Instance Type và Security Group.<br>- Tìm hiểu Stack Rollback, Drift Detection và Nested Stack.<br>- Kiểm tra tài nguyên sau khi cập nhật. | 23/07/2026 | 23/07/2026 | <https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/using-cfn-updating-stacks.html> |
| **6** | - Viết Lambda Function thực hiện Start/Stop RDS hoặc EC2.<br>- Tạo Amazon EventBridge Schedule.<br>- Kiểm tra kết quả qua CloudWatch Logs.<br>- Xóa Stack và dọn dẹp tài nguyên sau bài thực hành. | 24/07/2026 | 24/07/2026 | <https://docs.aws.amazon.com/eventbridge/> |

### Kết quả đạt được

* Hiểu lợi ích của Infrastructure as Code.
* Viết được CloudFormation Template bằng YAML.
* Triển khai tự động VPC, Subnet, Route Table, Security Group và EC2.
* Sử dụng Parameters và Outputs để tăng khả năng tái sử dụng.
* Sử dụng User Data để cấu hình EC2 khi khởi tạo.
* Biết theo dõi Stack Events và xử lý Rollback.
* Tạo Change Set để kiểm tra thay đổi trước khi cập nhật.
* Tự động Start/Stop tài nguyên bằng EventBridge và Lambda.

### Khó khăn và cách khắc phục

| Khó khăn | Cách khắc phục |
| --- | --- |
| Template báo lỗi cú pháp YAML | Kiểm tra khoảng trắng, thụt dòng và xác thực bằng `validate-template`. |
| Stack bị Rollback | Xem Stack Events để tìm tài nguyên đầu tiên tạo thất bại. |
| Tài nguyên phụ thuộc chưa được tạo | Dùng `Ref`, `GetAtt` hoặc `DependsOn` để xác định mối quan hệ. |
| Lambda không có quyền Start/Stop tài nguyên | Bổ sung IAM Policy phù hợp vào Execution Role của Lambda. |

---

### Đánh giá tuần

Tuần 5 giúp tôi hiểu cách quản lý hạ tầng giống như quản lý mã nguồn. CloudFormation cho phép triển khai cùng một kiến trúc nhiều lần với cấu hình nhất quán, hạn chế sai sót do thao tác thủ công.

Tôi cũng áp dụng EventBridge và Lambda để tự động dừng tài nguyên ngoài thời gian sử dụng. Nội dung này đặc biệt hữu ích sau khi tôi nhận thấy một RDS Instance bị bỏ quên có thể làm tăng chi phí AWS liên tục.