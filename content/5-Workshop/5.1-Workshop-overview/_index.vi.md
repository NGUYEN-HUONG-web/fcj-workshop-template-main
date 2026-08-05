---
title: "Workshop Overview"
date: 2026-07-17
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

# Tổng quan Workshop

## Giới thiệu

Trong workshop này, chúng ta sẽ triển khai **AI Learning Assistant Platform** trên nền tảng **Amazon Web Services (AWS)**.

AI Learning Assistant Platform là một nền tảng trợ lý học tập thông minh được phát triển dựa trên **FastGPT (Customized)** và ứng dụng công nghệ **Retrieval-Augmented Generation (RAG)** nhằm hỗ trợ người học khai thác tài liệu học tập thông qua trí tuệ nhân tạo.

Hệ thống cho phép người dùng tải lên tài liệu học tập để xây dựng **Knowledge Base**, sau đó sử dụng mô hình AI để trả lời câu hỏi dựa trên chính nội dung của tài liệu. Ngoài chức năng hỏi đáp, nền tảng còn hỗ trợ các tính năng như **tóm tắt bài học (Summary)**, **tạo câu hỏi trắc nghiệm (Quiz)**, **Flashcard** và **quản lý lịch sử học tập**.

Trong workshop này, toàn bộ hệ thống sẽ được triển khai trên **Amazon EC2** bằng **Docker Compose**. Bên cạnh đó, các dịch vụ của AWS như **Amazon S3**, **Amazon CloudWatch**, **AWS IAM** và **Security Group** sẽ được sử dụng để lưu trữ dữ liệu, giám sát hệ thống và đảm bảo an toàn trong quá trình vận hành.

Sau khi hoàn thành workshop, người dùng có thể truy cập AI Learning Assistant Platform thông qua trình duyệt web, tải tài liệu học tập và sử dụng đầy đủ các chức năng AI của hệ thống.

---

# Kiến trúc triển khai

AI Learning Assistant Platform được triển khai theo mô hình **Client – Server** trên nền tảng Amazon Web Services (AWS).

Người dùng truy cập hệ thống thông qua trình duyệt web. Các yêu cầu được chuyển đến **Nginx** để điều phối đến **Frontend** và **AI Learning Assistant Backend (FastGPT Customized)**. Backend chịu trách nhiệm xử lý nghiệp vụ, quản lý người dùng, điều phối mô hình AI và thực hiện quy trình **Retrieval-Augmented Generation (RAG)**.

Toàn bộ ứng dụng được triển khai trên một **Amazon EC2** dưới dạng nhiều **Docker Container**, kết hợp với các dịch vụ lưu trữ, giám sát và bảo mật của AWS.

### Các thành phần triển khai

| Thành phần | Vai trò |
|------------|----------|
| Amazon EC2 | Chạy toàn bộ AI Learning Assistant Platform |
| Docker Compose | Quản lý và điều phối các Docker Container |
| Nginx | Reverse Proxy |
| Frontend (Next.js / React) | Giao diện người dùng |
| AI Learning Assistant Backend (FastGPT Customized) | Xử lý nghiệp vụ, AI Chat và RAG |
| MongoDB | Lưu trữ dữ liệu người dùng và hệ thống |
| PostgreSQL + pgvector | Lưu trữ Vector Embedding phục vụ truy xuất ngữ nghĩa |
| MinIO | Lưu trữ tài liệu học tập |
| Amazon S3 | Sao lưu dữ liệu |
| Amazon CloudWatch | Giám sát hiệu năng và nhật ký hệ thống |
| AWS IAM | Quản lý quyền truy cập |
| Security Group | Kiểm soát truy cập mạng |

> **Hình 5.1. Kiến trúc triển khai AI Learning Assistant Platform trên AWS**

![Hình 5.1](/images/5.1.ws.png)

---

# Quy trình hoạt động

Sau khi hệ thống được triển khai thành công trên AWS, AI Learning Assistant Platform hoạt động theo quy trình sau:

1. Người dùng đăng nhập vào hệ thống.
2. Tải tài liệu học tập lên AI Learning Assistant Platform.
3. Hệ thống xử lý tài liệu, thực hiện Chunking và tạo Vector Embedding.
4. Dữ liệu được lưu vào Knowledge Base.
5. Người dùng đặt câu hỏi bằng ngôn ngữ tự nhiên.
6. Backend thực hiện Retrieval-Augmented Generation (RAG) để truy xuất các đoạn tài liệu liên quan.
7. Mô hình AI sinh câu trả lời dựa trên nội dung của tài liệu.
8. Kết quả cùng nguồn tham khảo được trả về giao diện người dùng.

> **Hình 5.2. Quy trình hoạt động của AI Learning Assistant Platform**

![Hình 5.2](/images/4.2.p.r.png)

---

# Kết quả đạt được

Sau khi hoàn thành workshop, bạn sẽ có thể:

- Triển khai thành công **AI Learning Assistant Platform** trên **Amazon Web Services (AWS)**.
- Khởi tạo và cấu hình **Amazon EC2** để vận hành hệ thống.
- Cài đặt và sử dụng **Docker** cùng **Docker Compose** để quản lý các Docker Container.
- Triển khai các thành phần của hệ thống gồm **Nginx**, **Frontend**, **Backend**, **MongoDB**, **PostgreSQL với pgvector** và **MinIO**.
- Thiết lập **Amazon S3** để sao lưu dữ liệu.
- Cấu hình **Amazon CloudWatch** để giám sát hiệu năng và trạng thái hoạt động của hệ thống.
- Thiết lập **AWS IAM** và **Security Group** nhằm quản lý quyền truy cập và bảo vệ hệ thống.
- Truy cập AI Learning Assistant Platform thông qua trình duyệt web và kiểm tra toàn bộ chức năng của hệ thống.

---

# Nội dung Workshop

Workshop được chia thành các phần sau:

| Mục | Nội dung |
|-----|----------|
| **5.1** | Tổng quan Workshop |
| **5.2** | Chuẩn bị môi trường triển khai |
| **5.3** | Triển khai hạ tầng trên AWS |
| **5.4** | Triển khai AI Learning Assistant Platform |
| **5.5** | Cấu hình giám sát và bảo mật |
| **5.6** | Dọn dẹp tài nguyên AWS |