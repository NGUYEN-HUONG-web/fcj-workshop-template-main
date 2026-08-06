---
title: "Nhật ký công việc Tuần 8"
date: 2026-08-06
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu tuần 8

* Hoàn thiện và triển khai dự án cuối kỳ trên AWS.
* Kiểm tra toàn bộ chức năng và luồng hoạt động của hệ thống.
* Thiết lập Monitoring, Logging và Alerting.
* Kiểm tra bảo mật và tối ưu chi phí AWS.
* Hoàn thiện Worklog, Proposal, Workshop và báo cáo thực tập.
* Tổng kết kiến thức và đánh giá quá trình thực tập.

### Công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| **2** | - Hoàn thiện các chức năng còn lại của dự án.<br>- Kiểm tra kết nối giữa Frontend, Backend, Database và các dịch vụ AWS.<br>- Chuẩn hóa biến môi trường và thông tin cấu hình.<br>- Cập nhật sơ đồ kiến trúc hệ thống. | 10/08/2026 | 10/08/2026 | |
| **3** | - Triển khai phiên bản hoàn chỉnh bằng CI/CD Pipeline.<br>- Kiểm tra Docker Image trên Amazon ECR.<br>- Kiểm tra trạng thái Container, Endpoint và Database Connection.<br>- Thực hiện Functional Testing sau khi triển khai. | 11/08/2026 | 11/08/2026 | <https://docs.github.com/actions> |
| **4** | - Cấu hình CloudWatch Logs và Metrics.<br>- Tạo Dashboard theo dõi CPU, Memory, Network và lỗi ứng dụng.<br>- Tạo Alarm và gửi cảnh báo qua SNS.<br>- Phân tích Log để xác định và khắc phục lỗi. | 12/08/2026 | 12/08/2026 | <https://000008.awsstudygroup.com/> |
| **5** | - Sử dụng Cost Explorer để phân tích chi phí theo dịch vụ.<br>- Kiểm tra IAM, Security Group và S3 Bucket Policy.<br>- Xác định tài nguyên không còn sử dụng.<br>- Điều chỉnh cấu hình và lịch Start/Stop để tối ưu chi phí. | 13/08/2026 | 13/08/2026 | <https://docs.aws.amazon.com/cost-management/> |
| **6** | - Hoàn thiện Worklog, Proposal, Blog và Workshop.<br>- Bổ sung hình ảnh, sơ đồ kiến trúc và Code Snippet.<br>- Dọn dẹp tài nguyên AWS không còn sử dụng.<br>- Tổng kết kiến thức, kỹ năng và kinh nghiệm đạt được sau tám tuần. | 14/08/2026 | 14/08/2026 | |

### Kết quả đạt được

#### Hoàn thiện dự án

* Hoàn thiện và triển khai dự án cuối kỳ trên AWS.
* Kiểm tra thành công luồng kết nối giữa các thành phần hệ thống.
* Sử dụng Docker và CI/CD để chuẩn hóa quá trình triển khai.
* Cập nhật sơ đồ kiến trúc và tài liệu hướng dẫn triển khai.

#### Giám sát và vận hành

* Thu thập Metrics và Logs bằng CloudWatch.
* Xây dựng Dashboard theo dõi trạng thái hệ thống.
* Cấu hình Alarm và nhận cảnh báo qua Amazon SNS.
* Sử dụng Log để tìm nguyên nhân và xử lý lỗi.

#### Bảo mật và tối ưu chi phí

* Kiểm tra IAM Policy theo nguyên tắc Least Privilege.
* Rà soát các cổng đang mở trong Security Group.
* Kiểm tra S3 Public Access và Bucket Policy.
* Sử dụng Cost Explorer để xác định dịch vụ phát sinh chi phí.
* Dừng hoặc xóa các tài nguyên không còn sử dụng.
* Áp dụng lịch Start/Stop cho EC2 và RDS khi phù hợp.

#### Hoàn thiện báo cáo

* Hoàn thành Worklog cho tám tuần.
* Hoàn thiện Proposal và Workshop của dự án.
* Bổ sung hình ảnh, sơ đồ kiến trúc và Code Snippet.
* Tổng kết kiến thức và tự đánh giá quá trình thực tập.

### Khó khăn và cách khắc phục

| Khó khăn | Cách khắc phục |
| --- | --- |
| Phiên bản mới triển khai nhưng ứng dụng chưa hoạt động đúng | Kiểm tra Image Tag, biến môi trường, Endpoint và CloudWatch Logs. |
| Chi phí AWS tiếp tục tăng sau bài thực hành | Kiểm tra Cost Explorer theo dịch vụ và Region, sau đó dừng hoặc xóa tài nguyên còn hoạt động. |
| Security Group có cổng mở quá rộng | Chỉ cho phép các cổng cần thiết và giới hạn nguồn truy cập phù hợp. |
| Tài liệu thiếu hình ảnh hoặc không đồng nhất | Rà soát từng bước triển khai và bổ sung ảnh chụp, chú thích và sơ đồ kiến trúc. |

---

### Đánh giá tuần

Trong tuần cuối, tôi đã vận dụng các kiến thức học được để hoàn thiện, triển khai và vận hành dự án trên AWS. Quá trình này giúp tôi hiểu rõ cách các dịch vụ Compute, Storage, Database, Networking, Security, Container và Monitoring phối hợp trong một hệ thống hoàn chỉnh.

Tôi nhận thấy việc triển khai ứng dụng thành công chỉ là bước đầu. Một hệ thống Cloud còn phải được giám sát liên tục, bảo vệ bằng các chính sách phù hợp và kiểm tra chi phí thường xuyên. Sự cố phát sinh chi phí từ một RDS Instance bị bỏ quên giúp tôi rút ra bài học thực tế về trách nhiệm quản lý tài nguyên.

Sau tám tuần thực tập, tôi đã củng cố kiến thức AWS, cải thiện kỹ năng triển khai hạ tầng, sử dụng Container, xây dựng CI/CD Pipeline và xử lý các vấn đề thực tế. Đây là nền tảng quan trọng để tôi tiếp tục phát triển theo định hướng Cloud, DevOps và phát triển ứng dụng trên AWS.