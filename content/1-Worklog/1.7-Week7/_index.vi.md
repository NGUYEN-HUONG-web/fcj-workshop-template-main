---
title: "Nhật ký công việc Tuần 7"
date: 2026-08-03
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu tuần 7

* Hiểu văn hóa DevOps và quy trình CI/CD.
* Quản lý mã nguồn bằng Git và GitHub.
* Xây dựng Pipeline tự động bằng GitHub Actions.
* Tự động kiểm thử, Build và đóng gói ứng dụng.
* Đẩy Docker Image lên Amazon ECR.
* Tự động triển khai phiên bản mới lên AWS.

### Công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| **2** | - Tìm hiểu DevOps và vòng đời phát triển phần mềm.<br>- Phân biệt Continuous Integration, Continuous Delivery và Continuous Deployment.<br>- Ôn tập Git Branch, Commit, Merge và Pull Request.<br>- Xây dựng quy tắc quản lý mã nguồn cho dự án. | 03/08/2026 | 03/08/2026 | <https://docs.github.com/actions> |
| **3** | - Tìm hiểu cấu trúc GitHub Actions Workflow.<br>- Tạo Workflow trong `.github/workflows`.<br>- Cấu hình Trigger khi Push và Pull Request.<br>- Tạo Job Checkout Source Code và thiết lập môi trường Build. | 04/08/2026 | 04/08/2026 | <https://docs.github.com/actions/writing-workflows> |
| **4** | - Cấu hình cài đặt Dependencies.<br>- Chạy Unit Test và Build ứng dụng tự động.<br>- Lưu Build Artifact.<br>- Kiểm tra Workflow Logs và xử lý các lỗi xảy ra trong Pipeline. | 05/08/2026 | 05/08/2026 | <https://docs.github.com/actions/automating-builds-and-tests> |
| **5** | - Bổ sung bước Build Docker Image.<br>- Cấu hình kết nối AWS bằng GitHub Secrets hoặc IAM Role.<br>- Đăng nhập Amazon ECR.<br>- Gắn Tag theo Commit SHA và Push Image lên ECR. | 06/08/2026 | 06/08/2026 | <https://github.com/aws-actions/amazon-ecr-login> |
| **6** | - Cập nhật phiên bản ứng dụng trên ECS, EKS hoặc EC2.<br>- Kiểm tra trạng thái triển khai và Log.<br>- Thử nghiệm thay đổi mã nguồn để kích hoạt Pipeline.<br>- Hoàn thiện tài liệu quy trình CI/CD. | 07/08/2026 | 07/08/2026 | <https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-cd-pipeline.html> |

### Kết quả đạt được

* Hiểu mục đích và các giai đoạn của CI/CD.
* Quản lý mã nguồn theo Branch và Pull Request.
* Tạo GitHub Actions Workflow bằng YAML.
* Tự động chạy Test và Build khi mã nguồn thay đổi.
* Lưu Artifact sau quá trình Build.
* Tự động Build và Push Docker Image lên Amazon ECR.
* Quản lý thông tin nhạy cảm bằng GitHub Secrets.
* Thực hiện triển khai ứng dụng lên AWS.
* Biết đọc Workflow Logs và xác định bước gây lỗi.

### Khó khăn và cách khắc phục

| Khó khăn | Cách khắc phục |
| --- | --- |
| Pipeline không được kích hoạt | Kiểm tra tên Branch và sự kiện trong phần `on` của Workflow. |
| Build không tìm thấy tệp JAR | Chạy bước Maven/Gradle Build trước khi Build Docker Image và kiểm tra đúng đường dẫn Artifact. |
| GitHub Actions không đăng nhập được ECR | Kiểm tra AWS Region, quyền IAM và thông tin xác thực. |
| Image mới đã Push nhưng ứng dụng chưa cập nhật | Tạo Revision mới cho Task Definition hoặc cập nhật Deployment sử dụng Image Tag mới. |
| Workflow để lộ thông tin nhạy cảm | Chuyển toàn bộ thông tin xác thực sang GitHub Secrets hoặc sử dụng OpenID Connect. |

---

### Đánh giá tuần

Tuần 7 giúp tôi hiểu cách DevOps kết nối quá trình phát triển và vận hành phần mềm. Thay vì Build và Deploy thủ công, GitHub Actions tự động kiểm tra mã nguồn, chạy Test, đóng gói ứng dụng và triển khai phiên bản mới.

Điều tôi học được là một Pipeline tốt không chỉ cần chạy thành công mà còn phải an toàn, dễ theo dõi và có khả năng phát hiện lỗi sớm. Việc sử dụng Secret hoặc OpenID Connect giúp hạn chế nguy cơ để lộ thông tin xác thực AWS.