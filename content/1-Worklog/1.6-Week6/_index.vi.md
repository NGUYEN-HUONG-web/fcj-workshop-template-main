---
title: "Nhật ký công việc Tuần 6"
date: 2026-07-27
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu tuần 6

* Hiểu Container và sự khác nhau giữa Container với máy ảo.
* Đóng gói ứng dụng bằng Docker.
* Quản lý Docker Image bằng Amazon ECR.
* Tìm hiểu Amazon ECS và AWS Fargate.
* Tìm hiểu Kubernetes và Amazon EKS.
* Triển khai ứng dụng Container trên AWS.

### Công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| **2** | - Tìm hiểu Docker Image, Container, Dockerfile, Registry, Volume và Network.<br>- Cài đặt Docker Desktop.<br>- Thực hành `docker pull`, `docker run`, `docker ps`, `docker logs` và `docker exec`.<br>- So sánh Container với Virtual Machine. | 27/07/2026 | 27/07/2026 | <https://docs.docker.com/get-started/> |
| **3** | - Viết Dockerfile cho Backend và Frontend.<br>- Sử dụng Multi-stage Build để giảm kích thước Image.<br>- Build và chạy Container trên máy cục bộ.<br>- Tìm hiểu Docker Compose và Environment Variables. | 28/07/2026 | 28/07/2026 | <https://docs.docker.com/build/building/multi-stage/> |
| **4** | - Tạo Amazon ECR Repository.<br>- Đăng nhập ECR bằng AWS CLI.<br>- Gắn thẻ và Push Docker Image lên ECR.<br>- Bật Image Scanning và kiểm tra các lỗ hổng được phát hiện. | 29/07/2026 | 29/07/2026 | <https://docs.aws.amazon.com/AmazonECR/latest/userguide/getting-started-cli.html> |
| **5** | - Tìm hiểu ECS Cluster, Task Definition, Task và Service.<br>- So sánh ECS on EC2 và AWS Fargate.<br>- Tạo Task Definition sử dụng Image từ ECR.<br>- Triển khai ECS Service và kiểm tra Container Logs. | 30/07/2026 | 30/07/2026 | <https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html> |
| **6** | - Tìm hiểu Kubernetes Control Plane, Worker Node, Pod, Deployment và Service.<br>- Làm quen với `kubectl` và Manifest YAML.<br>- Tìm hiểu Amazon EKS, Managed Node Group và EKS Pod Identity.<br>- Triển khai ứng dụng mẫu và kiểm tra trạng thái Pod. | 31/07/2026 | 31/07/2026 | <https://docs.aws.amazon.com/eks/latest/userguide/what-is-eks.html> |

### Kết quả đạt được

* Phân biệt được Container và Virtual Machine.
* Viết Dockerfile và đóng gói ứng dụng thành Docker Image.
* Sử dụng Multi-stage Build để tối ưu kích thước Image.
* Chạy nhiều Container bằng Docker Compose.
* Tạo ECR Repository và Push Image thành công.
* Hiểu cấu trúc ECS Cluster, Task Definition và Service.
* Hiểu vai trò của Pod, Deployment và Service trong Kubernetes.
* Làm quen với Amazon EKS và Managed Node Group.
* Sử dụng được các lệnh Docker, AWS ECR và `kubectl` cơ bản.

### Khó khăn và cách khắc phục

| Khó khăn | Cách khắc phục |
| --- | --- |
| Docker Image có kích thước lớn | Sử dụng Base Image nhỏ hơn và Multi-stage Build. |
| Không Push được Image lên ECR | Kiểm tra AWS Region, IAM Permission và thực hiện lại lệnh đăng nhập ECR. |
| Container dừng ngay sau khi chạy | Kiểm tra `docker logs`, biến môi trường và lệnh `ENTRYPOINT`. |
| Pod ở trạng thái `ImagePullBackOff` | Kiểm tra Image URI, Image Tag và quyền truy cập ECR. |
| Kubernetes Service không truy cập được | Kiểm tra Label, Selector, Port và TargetPort. |

---

### Đánh giá tuần

Tuần 6 giúp tôi hiểu cách Container chuẩn hóa môi trường phát triển và triển khai ứng dụng. Docker đảm bảo ứng dụng sử dụng cùng một môi trường khi chạy trên máy cá nhân và trên AWS.

Amazon ECR hỗ trợ lưu trữ Image, còn ECS và EKS cung cấp hai phương án điều phối Container. Kubernetes mạnh và linh hoạt nhưng có nhiều thành phần phức tạp, vì vậy việc hiểu rõ Pod, Deployment, Service và cách đọc trạng thái tài nguyên là rất quan trọng.