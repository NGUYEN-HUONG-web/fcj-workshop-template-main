---
title: "Bản đề xuất"
date: 2026-08-04
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# AI Learning Assistant Platform

## Nền tảng trợ lý học tập thông minh dựa trên tài liệu triển khai trên AWS

# Phần 1. Giới thiệu dự án

## 1.1 Bối cảnh

Sự phát triển mạnh mẽ của **Trí tuệ nhân tạo (Artificial Intelligence - AI)**, đặc biệt là các **Mô hình ngôn ngữ lớn (Large Language Models - LLMs)**, đang tạo ra nhiều thay đổi trong lĩnh vực giáo dục. Các hệ thống AI có khả năng hỗ trợ người học tìm kiếm thông tin, giải thích kiến thức và tương tác với tài liệu bằng ngôn ngữ tự nhiên, góp phần nâng cao hiệu quả học tập.

Tuy nhiên, hầu hết các chatbot AI hiện nay chỉ dựa trên dữ liệu đã được huấn luyện trước nên chưa thể trả lời chính xác các câu hỏi liên quan đến tài liệu học tập riêng của từng người dùng. Khi thiếu ngữ cảnh phù hợp, AI có thể đưa ra thông tin không chính xác hoặc không phản ánh đúng nội dung của tài liệu.

Trong thực tế, sinh viên thường phải sử dụng nhiều loại tài liệu như giáo trình, slide bài giảng, tài liệu tham khảo và hướng dẫn thực hành. Việc tìm kiếm thông tin trong khối lượng lớn tài liệu này mất nhiều thời gian và ảnh hưởng đến quá trình học tập.

Xuất phát từ nhu cầu đó, dự án **AI Learning Assistant Platform** được đề xuất nhằm xây dựng một nền tảng trợ lý học tập thông minh, cho phép người dùng khai thác hiệu quả tài liệu học tập thông qua công nghệ **Retrieval-Augmented Generation (RAG)**. Hệ thống được phát triển dựa trên nền tảng **FastGPT** và triển khai trên **Amazon Web Services (AWS)** nhằm đảm bảo khả năng mở rộng, tính sẵn sàng và bảo mật.

---

## 1.2 Mục tiêu

Dự án hướng đến việc xây dựng một nền tảng trợ lý học tập thông minh giúp người học tiếp cận và khai thác kiến thức từ tài liệu một cách nhanh chóng và hiệu quả.

Các mục tiêu chính của dự án bao gồm:

- Xây dựng hệ thống AI Learning Assistant ứng dụng công nghệ **Retrieval-Augmented Generation (RAG)**.
- Cho phép người dùng tải lên và quản lý tài liệu học tập.
- Xây dựng **Knowledge Base** phục vụ truy xuất thông tin theo ngữ nghĩa.
- Hỗ trợ AI trả lời câu hỏi dựa trên nội dung tài liệu của người dùng.
- Tích hợp các chức năng hỗ trợ học tập như tóm tắt bài học, tạo câu hỏi trắc nghiệm và Flashcard.
- Triển khai hệ thống trên nền tảng **Amazon Web Services (AWS)** theo mô hình điện toán đám mây.

---

## 1.3 Tổng quan giải pháp

AI Learning Assistant Platform là nền tảng học tập thông minh cho phép người dùng tải lên các tài liệu học tập và tương tác với AI bằng ngôn ngữ tự nhiên.

Sau khi tài liệu được tải lên, hệ thống sẽ tự động xử lý nội dung, chia nhỏ tài liệu, tạo **Embedding** và xây dựng **Knowledge Base**. Khi người dùng đặt câu hỏi, hệ thống sử dụng cơ chế **Retrieval-Augmented Generation (RAG)** để truy xuất các đoạn tài liệu liên quan, sau đó cung cấp ngữ cảnh cho mô hình AI nhằm tạo ra câu trả lời chính xác và bám sát nội dung tài liệu.

Ngoài chức năng hỏi đáp, hệ thống còn hỗ trợ quản lý tài liệu, tóm tắt bài học, tạo câu hỏi trắc nghiệm, Flashcard và lưu lịch sử học tập. Toàn bộ ứng dụng được triển khai trên AWS bằng Docker, tạo nền tảng thuận lợi cho việc mở rộng và phát triển trong tương lai.

### Thông tin tổng quan

| Tiêu chí | Giá trị |
|----------|----------|
| Tên dự án | AI Learning Assistant Platform |
| Loại dự án | Nền tảng trợ lý học tập thông minh |
| Đối tượng sử dụng | Sinh viên, giảng viên |
| Nền tảng phát triển | FastGPT (Customized) |
| Công nghệ AI | RAG, Knowledge Base, Embedding |
| Cloud Platform | Amazon Web Services (AWS) |
| Dịch vụ AWS | Amazon EC2, Amazon S3, Amazon CloudWatch |
| Cơ sở dữ liệu | MongoDB, PostgreSQL |
| Phương thức triển khai | Docker Compose |

# Phần 2. Phân tích bài toán và giải pháp

## 2.1 Bài toán

Trong môi trường học tập hiện nay, sinh viên thường phải sử dụng nhiều nguồn tài liệu như giáo trình, slide bài giảng, tài liệu tham khảo và hướng dẫn thực hành. Khi số lượng tài liệu ngày càng lớn, việc tìm kiếm một nội dung cụ thể trở nên mất nhiều thời gian và ảnh hưởng đến hiệu quả học tập.

Mặc dù các chatbot AI hiện nay có khả năng trả lời nhiều câu hỏi bằng ngôn ngữ tự nhiên, nhưng phần lớn chỉ dựa trên kiến thức đã được huấn luyện trước. Điều này khiến AI không thể khai thác chính xác nội dung từ tài liệu riêng của người dùng, đồng thời có thể tạo ra những câu trả lời không đúng với ngữ cảnh hoặc không có trong tài liệu.

Do đó, cần có một giải pháp cho phép AI hiểu và khai thác trực tiếp dữ liệu từ tài liệu học tập, giúp người dùng tìm kiếm thông tin nhanh chóng và nhận được câu trả lời chính xác hơn.

Hình 2.1 Bài toán hiện tại
![Hình 2.1](/images/2.1.pr.png)
---

## 2.2 Giải pháp đề xuất

Để giải quyết các vấn đề trên, dự án đề xuất xây dựng **AI Learning Assistant Platform** dựa trên công nghệ **Retrieval-Augmented Generation (RAG)**.

Khác với chatbot AI truyền thống, hệ thống cho phép người dùng tải lên các tài liệu học tập để xây dựng **Knowledge Base**. Khi người dùng đặt câu hỏi, hệ thống sẽ truy xuất những đoạn nội dung liên quan từ Knowledge Base trước khi gửi đến mô hình AI để tạo câu trả lời.

Nhờ đó, AI có thể:

- Trả lời dựa trên nội dung tài liệu của người dùng.
- Giảm hiện tượng AI tạo thông tin không có căn cứ (Hallucination).
- Hiển thị nguồn tham khảo của câu trả lời.
- Nâng cao độ chính xác và tính tin cậy của kết quả.

Ngoài chức năng hỏi đáp, hệ thống còn hỗ trợ các tính năng như:

- Quản lý tài liệu học tập.
- Tóm tắt nội dung bài học.
- Tạo câu hỏi trắc nghiệm.
- Tạo Flashcard hỗ trợ ôn tập.
- Lưu lịch sử học tập và hội thoại.

---

## 2.3 Quy trình hoạt động

Quy trình hoạt động của hệ thống gồm các bước sau:

1. Người dùng tải tài liệu học tập lên hệ thống.
2. Hệ thống trích xuất nội dung và xử lý tài liệu.
3. Nội dung được chia thành các đoạn nhỏ (Chunking).
4. Hệ thống tạo Embedding và lưu vào Vector Database.
5. Người dùng đặt câu hỏi bằng ngôn ngữ tự nhiên.
6. Hệ thống truy xuất các đoạn tài liệu phù hợp từ Knowledge Base.
7. Mô hình AI sử dụng các đoạn tài liệu làm ngữ cảnh để sinh câu trả lời.
8. Kết quả cùng nguồn tham khảo được hiển thị cho người dùng.

> **Hình 2.2. Quy trình hoạt động của AI Learning Assistant Platform sử dụng RAG.**

![Quy trình Retrieval-Augmented Generation](/images/h3bl3.png)

## 2.4 Lợi ích của giải pháp

Việc áp dụng công nghệ RAG vào AI Learning Assistant Platform mang lại nhiều lợi ích:

- Hỗ trợ tìm kiếm thông tin nhanh chóng trong tài liệu học tập.
- Nâng cao độ chính xác của câu trả lời nhờ sử dụng dữ liệu thực tế.
- Giảm hiện tượng Hallucination của mô hình AI.
- Tiết kiệm thời gian học tập và ôn tập.
- Tạo môi trường học tập thông minh, linh hoạt và dễ mở rộng trên nền tảng AWS.

Giải pháp không chỉ phù hợp với sinh viên và giảng viên mà còn có thể mở rộng cho các tổ chức đào tạo hoặc doanh nghiệp cần xây dựng hệ thống hỏi đáp dựa trên tài liệu nội bộ.

# Phần 3. Thiết kế và kiến trúc hệ thống

## 3.1 Kiến trúc tổng thể

AI Learning Assistant Platform được xây dựng theo mô hình Client – Server kết hợp với kiến trúc **Retrieval-Augmented Generation (RAG)**. Hệ thống gồm ba thành phần chính:

- **Frontend:** Giao diện web giúp người dùng quản lý tài liệu và tương tác với AI.
- **Backend:** Xử lý nghiệp vụ, quản lý người dùng, tài liệu và điều phối các dịch vụ AI.
- **Knowledge Base & AI:** Lưu trữ dữ liệu học tập, truy xuất thông tin và tạo câu trả lời dựa trên mô hình ngôn ngữ lớn (LLMs).

> **Hình 3.1. Kiến trúc tổng thể của AI Learning Assistant Platform.**
![Hình 3.1](/images/3.1.pr.png)
---

## 3.2 Kiến trúc triển khai trên AWS

Hệ thống được triển khai trên nền tảng **Amazon Web Services (AWS)** bằng Docker Compose.

Các dịch vụ chính được sử dụng gồm:

| Dịch vụ | Vai trò |
|----------|----------|
| Amazon EC2 | Chạy toàn bộ ứng dụng |
| Amazon EBS | Lưu trữ dữ liệu hệ thống |
| Amazon S3 | Lưu trữ và sao lưu tài liệu |
| Amazon CloudWatch | Giám sát hệ thống |
| AWS IAM | Quản lý quyền truy cập |
| Security Group | Kiểm soát lưu lượng mạng |

> **Hình 3.2. Kiến trúc triển khai hệ thống trên AWS.**
![Hình 3.2](/images/3.2.p.r.s.png)
---

## 3.3 Thiết kế cơ sở dữ liệu

Hệ thống sử dụng **MongoDB** để lưu trữ dữ liệu ứng dụng và **PostgreSQL** để hỗ trợ lưu trữ dữ liệu phục vụ quá trình truy xuất.

Các nhóm dữ liệu chính bao gồm:

- Người dùng.
- Môn học.
- Tài liệu học tập.
- Knowledge Base.
- Hội thoại.
- Lịch sử học tập.

> **Hình 3.3. Sơ đồ cơ sở dữ liệu của hệ thống.**
![Hình 3.3](/images/3.3.pr.drawio.png)
---

## 3.4 Quy trình hoạt động

Sau khi người dùng tải tài liệu lên, hệ thống thực hiện các bước sau:

1. Trích xuất nội dung từ tài liệu.
2. Chia tài liệu thành các đoạn nhỏ (Chunking).
3. Tạo Embedding cho từng đoạn.
4. Lưu dữ liệu vào Knowledge Base.
5. Người dùng đặt câu hỏi.
6. Hệ thống truy xuất các đoạn tài liệu liên quan.
7. Mô hình AI tạo câu trả lời và trả kết quả cho người dùng.

> **Hình 3.4. Quy trình hoạt động của AI Learning Assistant Platform sử dụng RAG.**
![Hình 3.4](/images/3.4.p.r.png)
---

## 3.5 Công nghệ sử dụng

| Thành phần | Công nghệ |
|------------|-----------|
| Frontend | Next.js, React, TypeScript |
| Backend | FastGPT (Customized) |
| AI | Large Language Models (LLMs) |
| AI Framework | Retrieval-Augmented Generation (RAG) |
| Database | MongoDB, PostgreSQL |
| Object Storage | MinIO / Amazon S3 |
| Container | Docker, Docker Compose |
| Cloud Platform | Amazon Web Services (AWS) |
# Phần 4. Triển khai và kiểm thử

## 4.1 Môi trường triển khai

AI Learning Assistant Platform được triển khai trên nền tảng **Amazon Web Services (AWS)** tại Region **US East (N. Virginia) – us-east-1**. Toàn bộ hệ thống được đóng gói dưới dạng các Docker Container và quản lý bằng Docker Compose trên một máy chủ Amazon EC2.

Kiến trúc triển khai bao gồm các thành phần chính như Frontend, AI Learning Assistant Backend (FastGPT), MongoDB, PostgreSQL với pgvector, MinIO và Nginx. Ngoài ra, hệ thống sử dụng Amazon S3 để lưu trữ tài liệu và sao lưu dữ liệu, Amazon CloudWatch để giám sát hoạt động, cùng AWS IAM để quản lý quyền truy cập.

### Cấu hình môi trường

| Thành phần | Công nghệ |
|------------|-----------|
| Cloud Platform | Amazon Web Services (AWS) |
| Region | us-east-1 |
| Compute | Amazon EC2 |
| Container | Docker Compose |
| Reverse Proxy | Nginx |
| Backend | FastGPT (Customized) |
| Frontend | Next.js / React |
| Database | MongoDB |
| Vector Database | PostgreSQL + pgvector |
| Object Storage | MinIO |
| Backup | Amazon S3 |
| Monitoring | Amazon CloudWatch |
| Security | IAM, Security Group |

> **Hình 4.1. Môi trường triển khai AI Learning Assistant Platform trên AWS.**
![Hình 4.1](/images/4.1.p.r.png)
## 4.2 Quy trình triển khai hệ thống

Quá trình triển khai được thực hiện theo các bước sau:

1. Tạo và cấu hình Amazon EC2.
2. Cài đặt Docker và Docker Compose.
3. Tải mã nguồn từ GitHub.
4. Cấu hình các biến môi trường.
5. Khởi động các container bằng Docker Compose.
6. Kiểm tra trạng thái hoạt động của các dịch vụ.
7. Cấu hình Nginx và Security Group.
8. Truy cập và kiểm thử hệ thống thông qua trình duyệt.

> **Hình 4.2. Quy trình triển khai AI Learning Assistant Platform trên AWS.**
![Hình 4.1](/images/4.2.p.r.png)
## 4.3 Kiểm thử hệ thống

Sau khi triển khai thành công, hệ thống được kiểm thử nhằm đánh giá tính ổn định và khả năng hoạt động của các chức năng chính.

| Chức năng | Kết quả |
|-----------|----------|
| Đăng nhập | Thành công |
| Tạo môn học | Thành công |
| Upload tài liệu | Thành công |
| Xây dựng Knowledge Base | Thành công |
| AI Chat (RAG) | Thành công |
| Summary | Thành công |
| Quiz | Thành công |
| Flashcard | Thành công |
| Lưu lịch sử hội thoại | Thành công |

Kết quả kiểm thử cho thấy hệ thống hoạt động ổn định và đáp ứng các yêu cầu chức năng đã đề ra.
## 4.4 Giám sát và vận hành

Trong quá trình vận hành, Amazon CloudWatch được sử dụng để theo dõi hiệu năng và trạng thái hoạt động của hệ thống.

Các chỉ số được giám sát bao gồm:

- CPU Utilization.
- Memory Usage.
- Disk Usage.
- Network Traffic.
- Docker Container Logs.
- Trạng thái dịch vụ.

Ngoài ra, dữ liệu tài liệu được sao lưu định kỳ lên Amazon S3 nhằm đảm bảo khả năng phục hồi khi xảy ra sự cố.

> **Hình 4.3. Dashboard giám sát AI Learning Assistant Platform bằng Amazon CloudWatch.**