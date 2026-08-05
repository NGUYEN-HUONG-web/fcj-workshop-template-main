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

AI Learning Assistant Platform được xây dựng theo mô hình **Client–Server** kết hợp với kiến trúc **Retrieval-Augmented Generation (RAG)** và được triển khai trên **Amazon Web Services (AWS)**.

Kiến trúc hệ thống gồm các thành phần chính:

- **Client Layer:** Người dùng truy cập hệ thống thông qua trình duyệt web.
- **Application Layer:** Toàn bộ ứng dụng được triển khai trên **Amazon EC2** bằng **Docker Compose**, bao gồm Nginx, Frontend, Backend, MongoDB, PostgreSQL và MinIO.
- **AI & Data Layer:** Backend xử lý AI Chat, Retrieval-Augmented Generation (RAG), Knowledge Base và quản lý tài liệu học tập; PostgreSQL với **pgvector** hỗ trợ truy xuất ngữ nghĩa, trong khi MongoDB lưu trữ dữ liệu hệ thống.

> **Hình 3.1. Kiến trúc tổng thể của AI Learning Assistant Platform.**
![Hình 3.1](/images/3.1.p.r.s.png)

---

## 3.2 Kiến trúc triển khai trên AWS

Hệ thống được triển khai trên nền tảng **Amazon Web Services (AWS)** bằng **Docker Compose** trên một **Amazon EC2**.

Các dịch vụ AWS chính được sử dụng gồm:

| Dịch vụ | Vai trò |
|----------|----------|
| Amazon EC2 | Chạy toàn bộ hệ thống và các Docker Container |
| Amazon EBS | Lưu trữ Docker Volume và dữ liệu hệ thống |
| Amazon S3 | Lưu trữ và sao lưu tài liệu học tập |
| Amazon CloudWatch | Giám sát tài nguyên, log và trạng thái hệ thống |
| AWS IAM | Quản lý quyền truy cập tài nguyên AWS |
| Security Group | Kiểm soát lưu lượng mạng và bảo mật truy cập |

> **Hình 3.2. Kiến trúc triển khai hệ thống trên AWS.**
![Hình 3.2](/images/3.2.p.r.s.png)

---

## 3.3 Thiết kế cơ sở dữ liệu

Hệ thống sử dụng nhiều thành phần lưu trữ nhằm đáp ứng các yêu cầu về quản lý dữ liệu, truy xuất ngữ nghĩa và lưu trữ tài liệu học tập.

| Thành phần | Vai trò |
|------------|----------|
| MongoDB | Lưu trữ dữ liệu người dùng, hội thoại, Knowledge Base và cấu hình hệ thống |
| PostgreSQL + pgvector | Lưu trữ vector embedding phục vụ Retrieval-Augmented Generation (RAG) |
| MinIO | Lưu trữ tài liệu học tập được người dùng tải lên |
| Amazon S3 | Lưu trữ dữ liệu sao lưu và tài liệu dự phòng |

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
| Database | MongoDB, PostgreSQL + pgvector |
| Object Storage | MinIO, Amazon S3 |
| Container | Docker, Docker Compose |
| Cloud Platform | Amazon Web Services (AWS) |
# Phần 4. Triển khai và kiểm thử

## 4.1 Môi trường triển khai

AI Learning Assistant Platform được triển khai trên nền tảng **Amazon Web Services (AWS)** tại Region **US East (N. Virginia) – us-east-1**. Toàn bộ hệ thống được đóng gói dưới dạng các **Docker Container** và quản lý bằng **Docker Compose** trên một **Amazon EC2**.

Kiến trúc triển khai bao gồm **Nginx**, **Frontend (Next.js/React)**, **AI Learning Assistant Backend (FastGPT Customized)**, **MongoDB**, **PostgreSQL với pgvector** và **MinIO**. Bên cạnh đó, hệ thống sử dụng **Amazon S3** để sao lưu dữ liệu, **Amazon CloudWatch** để giám sát hiệu năng và trạng thái hoạt động, cùng **AWS IAM** và **Security Group** để quản lý quyền truy cập và bảo mật hệ thống.

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
| Backup Storage | Amazon S3 |
| Monitoring | Amazon CloudWatch |
| Security | AWS IAM, Security Group |

> **Hình 4.1. Môi trường triển khai AI Learning Assistant Platform trên AWS.**
![Hình 4.1](/images/4.1.p.r.png)

---

## 4.2 Quy trình triển khai hệ thống

Quy trình triển khai hệ thống được thực hiện theo các bước sau:

1. Khởi tạo và cấu hình **Amazon EC2**, **Security Group** và **Elastic IP**.
2. Cài đặt **Docker** và **Docker Compose** trên máy chủ EC2.
3. Tải mã nguồn từ GitHub và cấu hình các biến môi trường.
4. Khởi động các Docker Container gồm **Nginx**, **Frontend**, **Backend**, **MongoDB**, **PostgreSQL** và **MinIO**.
5. Kết nối **Amazon S3** để sao lưu dữ liệu và **Amazon CloudWatch** để giám sát hệ thống.
6. Kiểm tra trạng thái hoạt động của các dịch vụ và cấu hình Nginx.
7. Truy cập hệ thống thông qua trình duyệt để kiểm thử và đưa vào vận hành.

> **Hình 4.2. Quy trình triển khai AI Learning Assistant Platform trên AWS.**
![Hình 4.2](/images/4.2.p.r.png)

---

## 4.3 Kiểm thử hệ thống

Sau khi triển khai thành công, hệ thống được kiểm thử nhằm đánh giá tính ổn định và khả năng hoạt động của các chức năng chính.

| Chức năng | Kết quả |
|-----------|----------|
| Đăng nhập và xác thực người dùng | Thành công |
| Quản lý môn học | Thành công |
| Upload tài liệu học tập | Thành công |
| Xây dựng Knowledge Base | Thành công |
| AI Chat (RAG) | Thành công |
| Tóm tắt bài học (Summary) | Thành công |
| Tạo bài kiểm tra (Quiz) | Thành công |
| Tạo Flashcard | Thành công |
| Lưu lịch sử học tập | Thành công |

Kết quả kiểm thử cho thấy hệ thống hoạt động ổn định, các Docker Container vận hành bình thường và các chức năng chính đều đáp ứng yêu cầu của hệ thống.

---

## 4.4 Giám sát và vận hành

Trong quá trình vận hành, **Amazon CloudWatch** được sử dụng để theo dõi hiệu năng và trạng thái hoạt động của hệ thống.

Các chỉ số được giám sát bao gồm:

- CPU Utilization.
- Memory Usage.
- Disk Usage.
- Network Traffic.
- Docker Container Logs.
- Trạng thái hoạt động của các dịch vụ.

Ngoài ra, dữ liệu và tài liệu học tập được sao lưu định kỳ lên **Amazon S3** nhằm đảm bảo khả năng phục hồi khi xảy ra sự cố và hỗ trợ duy trì tính ổn định của hệ thống.
# Phần 5. Bảo mật, chi phí và quản lý rủi ro

## 5.1 Bảo mật hệ thống

AI Learning Assistant Platform lưu trữ tài khoản, tài liệu học tập và lịch sử hội thoại của người dùng. Vì vậy, bảo mật được xem là một yêu cầu quan trọng trong quá trình triển khai hệ thống trên AWS.

Các biện pháp bảo mật chính bao gồm:

- Sử dụng **AWS IAM** để quản lý quyền truy cập vào tài nguyên AWS theo nguyên tắc quyền tối thiểu.
- Sử dụng **Security Group** để giới hạn các cổng và nguồn được phép truy cập Amazon EC2.
- Sử dụng **HTTPS** để mã hóa dữ liệu truyền giữa người dùng và hệ thống.
- Không lưu API Key, mật khẩu hoặc thông tin nhạy cảm trực tiếp trong mã nguồn.
- Sử dụng **AWS Secrets Manager** hoặc biến môi trường để quản lý thông tin xác thực.
- Sử dụng **AWS KMS** để hỗ trợ mã hóa dữ liệu khi cần thiết.
- Amazon S3 được cấu hình hạn chế quyền truy cập đối với tài liệu và dữ liệu sao lưu.
- MongoDB, PostgreSQL và các dịch vụ nội bộ không được mở trực tiếp ra Internet.
- Sử dụng **Amazon CloudWatch** để theo dõi log và phát hiện các hoạt động bất thường.


## 5.2 Chi phí triển khai dự kiến

AI Learning Assistant Platform được triển khai theo mô hình MVP trên Amazon Web Services (AWS) nhằm tối ưu chi phí nhưng vẫn đảm bảo hiệu năng và khả năng mở rộng. Trong giai đoạn đầu, toàn bộ hệ thống được triển khai trên một Amazon EC2 instance bằng Docker Compose, kết hợp với các dịch vụ lưu trữ, giám sát và bảo mật của AWS.

Bảng dưới đây trình bày chi phí ước tính hàng tháng của các dịch vụ chính được sử dụng trong hệ thống.

### Bảng 5.1. Chi phí triển khai dự kiến

| STT | Dịch vụ AWS | Cấu hình dự kiến | Mục đích sử dụng | Chi phí ước tính (USD/tháng) |
|:--:|-------------|------------------|------------------|-----------------------------:|
| 1 | Amazon EC2 | t3.large (2 vCPU, 8 GB RAM) | Chạy AI Learning Assistant, Nginx, MongoDB, PostgreSQL và MinIO | 60 |
| 2 | Amazon EBS | 50 GB (gp3) | Lưu Docker Volume và dữ liệu hệ thống | 4 |
| 3 | Amazon S3 | 50 GB | Lưu tài liệu học tập và sao lưu dữ liệu | 2 |
| 4 | Amazon CloudWatch | Metrics, Logs, Alarms | Giám sát và cảnh báo hệ thống | 5 |
| 5 | Elastic IP | 01 Public IP | Truy cập hệ thống từ Internet | 0* |
| 6 | Data Transfer | Khoảng 100 GB/tháng | Lưu lượng truy cập Internet | 8 |
| 7 | Google Gemini API / OpenAI API | Theo số lượng request | Xử lý AI và sinh câu trả lời | 15 – 50 |

| | | | **Tổng chi phí dự kiến** | **94 – 129 USD/tháng** |

> **Lưu ý:**
>
> - Chi phí trên chỉ mang tính ước tính tại Region **US East (N. Virginia) – us-east-1** và có thể thay đổi theo bảng giá AWS.
> - Elastic IP không phát sinh chi phí khi được gắn với một EC2 đang hoạt động.
> - Chi phí sử dụng mô hình AI phụ thuộc vào số lượng request và số lượng token được xử lý.

### Đánh giá chi phí

Với quy mô từ **5–20 người dùng**, chi phí triển khai khoảng **94–129 USD/tháng**, trong đó Amazon EC2 và dịch vụ mô hình ngôn ngữ (LLM API) chiếm tỷ trọng lớn nhất. Kiến trúc triển khai trên một EC2 bằng Docker Compose giúp giảm chi phí hạ tầng trong giai đoạn đầu nhưng vẫn đáp ứng đầy đủ các chức năng của hệ thống.

### Biện pháp tối ưu chi phí

Để giảm chi phí vận hành, hệ thống áp dụng các biện pháp sau:

- Triển khai toàn bộ dịch vụ trên một Amazon EC2 trong giai đoạn MVP.
- Theo dõi chi phí bằng **AWS Budgets** và **Billing Alerts**.
- Giám sát tài nguyên bằng **Amazon CloudWatch** để tối ưu cấu hình EC2.
- Xóa hoặc dừng các tài nguyên không sử dụng sau khi kiểm thử.
- Sao lưu dữ liệu định kỳ lên Amazon S3 thay vì duy trì nhiều bản sao trực tiếp trên EC2.
- Giới hạn số lượng request và token gửi đến mô hình AI nhằm kiểm soát chi phí API.
- Có thể mở rộng sang **Amazon ECS**, **Application Load Balancer** và **Auto Scaling** khi số lượng người dùng tăng mà không cần thay đổi kiến trúc tổng thể.
# Phần 6. Đánh giá và hướng phát triển

## 6.1 Đánh giá theo AWS Well-Architected Framework

AI Learning Assistant Platform được đánh giá dựa trên các nguyên tắc của **AWS Well-Architected Framework**, nhằm đảm bảo hệ thống có khả năng vận hành ổn định, bảo mật, tối ưu hiệu năng và chi phí.

### Bảng 6.1. Đánh giá hệ thống theo AWS Well-Architected Framework

| Trụ cột | Giải pháp áp dụng trong dự án |
|----------|-------------------------------|
| Operational Excellence | Triển khai bằng Docker Compose, sử dụng GitHub để quản lý mã nguồn và Amazon CloudWatch để giám sát hệ thống. |
| Security | Áp dụng AWS IAM, Security Group, HTTPS, AWS Secrets Manager và AWS KMS để bảo vệ tài nguyên và dữ liệu. |
| Reliability | Sao lưu dữ liệu bằng Amazon S3, theo dõi trạng thái hệ thống bằng CloudWatch và sử dụng Docker Restart Policy để tăng khả năng phục hồi. |
| Performance Efficiency | Sử dụng PostgreSQL + pgvector để truy xuất dữ liệu theo ngữ nghĩa, kết hợp RAG nhằm nâng cao hiệu quả trả lời của AI. |
| Cost Optimization | Triển khai toàn bộ dịch vụ trên một Amazon EC2 trong giai đoạn MVP, sử dụng AWS Budgets và Billing Alerts để kiểm soát chi phí. |
| Sustainability | Kiến trúc có thể mở rộng sang ECS, Auto Scaling và Application Load Balancer khi số lượng người dùng tăng. |

Nhìn chung, hệ thống đáp ứng các yêu cầu cơ bản của AWS Well-Architected Framework đối với một ứng dụng AI triển khai trên nền tảng điện toán đám mây. Kiến trúc hiện tại phù hợp với quy mô MVP và có khả năng mở rộng trong các giai đoạn tiếp theo.

> **Hình 6.1. Đánh giá AI Learning Assistant Platform theo AWS Well-Architected Framework.**
![Hình 4.2](/images/6.1.p.r.png)
---

## 6.2 Hướng phát triển

Trong tương lai, AI Learning Assistant Platform có thể được mở rộng nhằm nâng cao hiệu năng, khả năng mở rộng và trải nghiệm người dùng.

Các hướng phát triển chính bao gồm:

- Chuyển từ Docker Compose sang Amazon ECS hoặc Amazon EKS để tăng khả năng mở rộng.
- Triển khai Application Load Balancer và Auto Scaling để hỗ trợ nhiều người dùng đồng thời.
- Mở rộng Knowledge Base cho nhiều môn học và nhiều nhóm người dùng.
- Tích hợp thêm các mô hình AI như Amazon Bedrock, Google Gemini hoặc OpenAI.
- Bổ sung các tính năng AI như tạo Mindmap, AI Tutor, Speech-to-Text và Text-to-Speech.
- Xây dựng ứng dụng di động trên Android và iOS.
- Tối ưu quy trình RAG nhằm cải thiện tốc độ và độ chính xác của câu trả lời.
- Hoàn thiện hệ thống giám sát, cảnh báo và sao lưu tự động để nâng cao độ tin cậy của hệ thống.

Với kiến trúc hiện tại, AI Learning Assistant Platform có thể tiếp tục mở rộng để đáp ứng nhu cầu học tập của nhiều người dùng, đồng thời sẵn sàng triển khai ở quy mô lớn hơn trên nền tảng Amazon Web Services.
# Phần 7. Kết luận

## 7.1 Kết quả đạt được

AI Learning Assistant Platform được xây dựng nhằm hỗ trợ người học khai thác tài liệu học tập thông qua trí tuệ nhân tạo kết hợp với công nghệ Retrieval-Augmented Generation (RAG). Hệ thống cho phép người dùng tải lên tài liệu, xây dựng Knowledge Base và tương tác với AI bằng ngôn ngữ tự nhiên, từ đó nâng cao độ chính xác của câu trả lời so với các chatbot AI truyền thống.

Bên cạnh chức năng hỏi đáp, hệ thống còn tích hợp các tính năng hỗ trợ học tập như quản lý tài liệu, tóm tắt bài học, tạo câu hỏi trắc nghiệm, Flashcard và lưu lịch sử hội thoại. Toàn bộ ứng dụng được triển khai trên nền tảng Amazon Web Services (AWS), đáp ứng các yêu cầu cơ bản về hiệu năng, bảo mật, khả năng mở rộng và quản lý hệ thống.

Thông qua quá trình thực hiện dự án, các mục tiêu chính đã đạt được gồm:

- Xây dựng nền tảng AI Learning Assistant dựa trên FastGPT.
- Ứng dụng Retrieval-Augmented Generation (RAG) để nâng cao chất lượng câu trả lời.
- Triển khai hệ thống trên Amazon EC2 bằng Docker Compose.
- Tích hợp MongoDB, PostgreSQL, MinIO và các dịch vụ AWS.
- Xây dựng kiến trúc có khả năng mở rộng và phù hợp với giai đoạn MVP.

---

## 7.2 Hạn chế

Mặc dù đã đáp ứng các mục tiêu đề ra, hệ thống vẫn còn một số hạn chế:

- Kiến trúc hiện tại sử dụng một Amazon EC2 nên chưa đáp ứng yêu cầu sẵn sàng cao (High Availability).
- Chưa triển khai Auto Scaling và Load Balancer.
- Chất lượng câu trả lời vẫn phụ thuộc vào nội dung và chất lượng của tài liệu được tải lên.
- Chưa hỗ trợ ứng dụng di động và làm việc ngoại tuyến.
- Một số tính năng AI nâng cao vẫn đang trong giai đoạn nghiên cứu và phát triển.

---

## 7.3 Hướng phát triển

Trong tương lai, AI Learning Assistant Platform sẽ được mở rộng theo các hướng sau:

- Triển khai Amazon ECS hoặc Amazon EKS để nâng cao khả năng mở rộng.
- Sử dụng Application Load Balancer và Auto Scaling nhằm hỗ trợ nhiều người dùng đồng thời.
- Tích hợp thêm các mô hình AI như Amazon Bedrock, Google Gemini hoặc OpenAI.
- Mở rộng các chức năng học tập như AI Tutor, Mindmap, Speech-to-Text và Text-to-Speech.
- Phát triển ứng dụng trên nền tảng Android và iOS.
- Tối ưu quy trình RAG để nâng cao tốc độ và độ chính xác của hệ thống.
- Hoàn thiện cơ chế giám sát, sao lưu và phục hồi dữ liệu nhằm tăng tính ổn định và an toàn trong quá trình vận hành.

Những định hướng trên sẽ giúp AI Learning Assistant Platform trở thành một nền tảng học tập thông minh có khả năng phục vụ nhiều đối tượng người dùng và đáp ứng tốt hơn các nhu cầu trong môi trường giáo dục hiện đại.

---

## 7.4 Kết luận

AI Learning Assistant Platform là một giải pháp hỗ trợ học tập ứng dụng trí tuệ nhân tạo, được xây dựng trên nền tảng FastGPT và triển khai trên Amazon Web Services (AWS). Việc kết hợp công nghệ Retrieval-Augmented Generation (RAG) với Knowledge Base giúp hệ thống cung cấp câu trả lời bám sát tài liệu học tập, góp phần nâng cao hiệu quả học tập và giảm hiện tượng AI tạo thông tin không có căn cứ.

Với kiến trúc được thiết kế theo hướng mở, hệ thống có thể tiếp tục mở rộng và tích hợp thêm nhiều dịch vụ AI cũng như các dịch vụ AWS trong tương lai. Dự án không chỉ đáp ứng mục tiêu xây dựng một trợ lý học tập thông minh mà còn tạo nền tảng cho việc nghiên cứu, phát triển và ứng dụng Generative AI trong lĩnh vực giáo dục.

Bên cạnh việc xây dựng nền tảng học tập thông minh, dự án còn minh họa cách triển khai một ứng dụng Generative AI trên Amazon Web Services thông qua Docker Compose, Amazon EC2, Amazon S3, Amazon CloudWatch và các dịch vụ bảo mật của AWS. Đây là nền tảng để tiếp tục mở rộng hệ thống trong tương lai.