---
title: "Dự án "
date: 2026-08-04
weight: 2
chapter: false
pre: " <b> 2. </b> "
---

# AI Learning Assistant Platform

### Nền tảng trợ lý học tập thông minh dựa trên tài liệu triển khai trên AWS
# Phần 1. Giới thiệu dự án

# Thông tin nhóm thực hiện

| STT | Họ và tên | Mã số sinh viên | Vai trò |
|:---:|---|---|---|---|
| 1 | Nguyễn Thị Thu Hường| 3122411079 | Trưởng nhóm | 
| 2 | Trần Quốc Bảo | 3122411015 | Thành viên | 
| 3 | Nguyễn Ngọc Thúy Vy | 3122411256 | Thành viên |

---
# Phần 2. Tổng quan dự án

## 1.1 Bối cảnh

Trong những năm gần đây, sự phát triển của **Trí tuệ nhân tạo (Artificial Intelligence - AI)** và các **Mô hình ngôn ngữ lớn (Large Language Models - LLMs)** đã mở ra nhiều cơ hội ứng dụng trong lĩnh vực giáo dục. Các hệ thống AI không chỉ hỗ trợ tìm kiếm thông tin mà còn có khả năng tương tác với người dùng bằng ngôn ngữ tự nhiên, giúp nâng cao hiệu quả học tập và giảm thời gian tra cứu tài liệu.

Tuy nhiên, các chatbot AI phổ biến hiện nay thường chỉ dựa trên kiến thức đã được huấn luyện trước. Khi người dùng đặt câu hỏi liên quan đến giáo trình, slide bài giảng hoặc tài liệu nội bộ, AI có thể đưa ra câu trả lời chưa chính xác hoặc không phản ánh đúng nội dung của tài liệu. Hiện tượng này được gọi là **AI Hallucination**, làm giảm độ tin cậy của hệ thống trong môi trường học tập.

Trong thực tế, sinh viên và giảng viên thường phải quản lý nhiều nguồn tài liệu khác nhau như giáo trình, bài giảng, tài liệu tham khảo, hướng dẫn thực hành và báo cáo nghiên cứu. Việc tìm kiếm thông tin trong khối lượng lớn tài liệu này mất nhiều thời gian, gây khó khăn cho quá trình học tập và nghiên cứu.

Để giải quyết vấn đề trên, dự án **AI Learning Assistant Platform** được xây dựng nhằm tạo ra một nền tảng trợ lý học tập thông minh cho phép người dùng tải lên tài liệu, xây dựng **Knowledge Base** và tương tác với AI bằng ngôn ngữ tự nhiên. Hệ thống áp dụng công nghệ **Retrieval-Augmented Generation (RAG)** để truy xuất thông tin từ tài liệu trước khi sinh câu trả lời, giúp nâng cao độ chính xác và giảm hiện tượng AI Hallucination.

Toàn bộ hệ thống được triển khai trên **Amazon Web Services (AWS)** bằng mô hình **Docker Compose** chạy trên **Amazon EC2**, đồng thời tích hợp **GitHub Actions**, **Amazon ECR** và **Amazon CloudWatch** nhằm tự động hóa quá trình triển khai, giám sát hệ thống và tối ưu vận hành.

---

## 1.2 Mục tiêu

Dự án hướng tới việc xây dựng một nền tảng trợ lý học tập thông minh có khả năng hỗ trợ sinh viên và giảng viên khai thác tài liệu học tập hiệu quả thông qua công nghệ Generative AI và điện toán đám mây.

### Mục tiêu chức năng

- Xây dựng nền tảng **AI Learning Assistant Platform** dựa trên FastGPT.
- Cho phép người dùng tải lên và quản lý tài liệu học tập.
- Xây dựng **Knowledge Base** từ tài liệu của người dùng.
- Áp dụng **Retrieval-Augmented Generation (RAG)** để trả lời câu hỏi dựa trên nội dung tài liệu.
- Hỗ trợ các chức năng AI như AI Chat, Summary, Quiz và Flashcard.
- Lưu trữ lịch sử hội thoại và quá trình học tập.

### Mục tiêu kỹ thuật

- Triển khai hệ thống trên **Amazon Web Services (AWS)**.
- Đóng gói toàn bộ ứng dụng bằng **Docker Compose**.
- Sử dụng **Amazon EC2** để vận hành hệ thống.
- Lưu trữ dữ liệu bằng **MongoDB**, **PostgreSQL (pgvector)** và **MinIO**.
- Thiết lập quy trình **CI/CD** với **GitHub Actions** và **Amazon ECR**.
- Giám sát hệ thống bằng **Amazon CloudWatch**.
- Áp dụng các biện pháp bảo mật thông qua **AWS IAM**, **Security Group** và quản lý biến môi trường.

---

## 1.3 Phạm vi dự án

Dự án tập trung xây dựng một phiên bản **Minimum Viable Product (MVP)** của AI Learning Assistant Platform với các chức năng cốt lõi phục vụ học tập và nghiên cứu.

### Phạm vi chức năng

- Đăng nhập và quản lý người dùng.
- Quản lý môn học và Knowledge Base.
- Upload tài liệu học tập.
- AI Chat dựa trên RAG.
- Tóm tắt nội dung tài liệu.
- Sinh câu hỏi trắc nghiệm.
- Tạo Flashcard.
- Lưu lịch sử hội thoại.

### Phạm vi triển khai

Hệ thống được triển khai trên **Amazon EC2** theo mô hình **Production Lite**, trong đó toàn bộ các thành phần được quản lý bằng **Docker Compose**, bao gồm:

- Nginx
- Frontend (Next.js/React)
- Backend (FastGPT Customized)
- MongoDB
- PostgreSQL + pgvector
- MinIO

Ngoài ra, hệ thống còn tích hợp các dịch vụ AWS để phục vụ triển khai và vận hành:

- Amazon EBS
- Amazon S3
- Amazon ECR
- Amazon CloudWatch
- AWS IAM
- Security Group
- AWS Budgets

---

## 1.4 Tổng quan giải pháp

AI Learning Assistant Platform là một nền tảng học tập thông minh cho phép người dùng khai thác kiến thức từ tài liệu học tập thông qua trí tuệ nhân tạo.

Sau khi người dùng tải tài liệu lên hệ thống, Backend sẽ tự động thực hiện quá trình xử lý gồm trích xuất nội dung, chia nhỏ tài liệu (Chunking), tạo Vector Embedding và lưu trữ vào **Knowledge Base**. Khi người dùng gửi câu hỏi, hệ thống sử dụng cơ chế **Retrieval-Augmented Generation (RAG)** để truy xuất các đoạn tài liệu có liên quan từ **PostgreSQL với pgvector**, sau đó kết hợp với câu hỏi tạo thành ngữ cảnh cho mô hình AI sinh câu trả lời.

Nhờ cơ chế này, hệ thống có thể cung cấp câu trả lời bám sát nội dung tài liệu của người dùng, đồng thời giảm đáng kể hiện tượng AI Hallucination so với các chatbot truyền thống.

Toàn bộ ứng dụng được triển khai trên **Amazon Web Services (AWS)** bằng Docker Compose. Quy trình triển khai được tự động hóa thông qua **GitHub Actions** và **Amazon ECR**, trong khi **Amazon CloudWatch** được sử dụng để giám sát hiệu năng và trạng thái hoạt động của hệ thống.

---

### Bảng 1.1. Thông tin tổng quan dự án

| Tiêu chí | Nội dung |
|----------|----------|
| Tên dự án | AI Learning Assistant Platform |
| Loại dự án | Intelligent Learning Assistant Platform |
| Đối tượng sử dụng | Sinh viên, giảng viên |
| Nền tảng phát triển | FastGPT (Customized) |
| Công nghệ AI | Large Language Models (LLMs), RAG |
| Cloud Platform | Amazon Web Services (AWS) |
| AWS Services | Amazon EC2, Amazon EBS, Amazon S3, Amazon ECR, Amazon CloudWatch, AWS IAM, AWS Budgets |
| Cơ sở dữ liệu | MongoDB, PostgreSQL + pgvector |
| Object Storage | MinIO |
| Containerization | Docker, Docker Compose |
| CI/CD | GitHub Actions + Amazon ECR |
| Monitoring | Amazon CloudWatch |
| Kiến trúc triển khai | Production Lite trên Amazon EC2 |

# Phần 2. Phân tích bài toán và giải pháp

## 2.1 Bài toán

Trong môi trường học tập hiện nay, sinh viên và giảng viên phải sử dụng nhiều nguồn tài liệu như giáo trình, slide bài giảng, tài liệu tham khảo, báo cáo nghiên cứu và hướng dẫn thực hành. Khi số lượng tài liệu ngày càng lớn, việc tìm kiếm một nội dung cụ thể trở nên mất nhiều thời gian và ảnh hưởng đến hiệu quả học tập.

Bên cạnh đó, các chatbot AI phổ biến hiện nay chủ yếu dựa trên dữ liệu đã được huấn luyện trước. Khi người dùng đặt câu hỏi liên quan đến tài liệu cá nhân hoặc tài liệu nội bộ, AI thường không có đủ ngữ cảnh để đưa ra câu trả lời chính xác. Điều này dẫn đến hiện tượng **AI Hallucination**, trong đó mô hình có thể tạo ra thông tin không có trong tài liệu hoặc không phản ánh đúng nội dung mà người dùng mong muốn.

Ngoài ra, quá trình học tập còn tồn tại nhiều khó khăn khác như:

- Khó tìm kiếm thông tin trong nhiều tài liệu khác nhau.
- Mất nhiều thời gian đọc và tổng hợp nội dung.
- Chưa có công cụ hỗ trợ hỏi đáp trực tiếp dựa trên tài liệu học tập.
- Chưa có hệ thống tự động tạo nội dung ôn tập như Quiz hoặc Flashcard.
- Việc quản lý tài liệu và lịch sử học tập còn phân tán.

Những hạn chế trên đặt ra yêu cầu cần xây dựng một nền tảng học tập thông minh có khả năng hiểu nội dung tài liệu của người dùng, hỗ trợ tìm kiếm theo ngữ nghĩa và cung cấp câu trả lời chính xác hơn bằng công nghệ Generative AI.

---

## 2.2 Giải pháp đề xuất

Để giải quyết các vấn đề trên, dự án xây dựng **AI Learning Assistant Platform** dựa trên công nghệ **Retrieval-Augmented Generation (RAG)**.

Khác với chatbot AI truyền thống, hệ thống không chỉ sử dụng kiến thức đã được huấn luyện của mô hình mà còn kết hợp với dữ liệu trong **Knowledge Base** được tạo từ tài liệu do người dùng tải lên.

Sau khi tài liệu được tải lên, hệ thống sẽ tự động thực hiện các bước xử lý như trích xuất nội dung, chia nhỏ tài liệu (Chunking), tạo Vector Embedding và lưu trữ vào cơ sở dữ liệu vector. Khi người dùng đặt câu hỏi, hệ thống sẽ truy xuất những đoạn tài liệu liên quan nhất trước khi gửi đến mô hình AI để sinh câu trả lời.

Nhờ cơ chế này, hệ thống mang lại các lợi ích sau:

- Trả lời dựa trên nội dung tài liệu của người dùng.
- Giảm hiện tượng AI Hallucination.
- Nâng cao độ chính xác của câu trả lời.
- Hiển thị nguồn tham khảo cho câu trả lời.
- Hỗ trợ tìm kiếm theo ngữ nghĩa thay vì chỉ tìm kiếm theo từ khóa.

Ngoài chức năng AI Chat, hệ thống còn cung cấp các tính năng hỗ trợ học tập như:

- Quản lý môn học và Knowledge Base.
- Upload và quản lý tài liệu.
- Tóm tắt nội dung bài học.
- Sinh câu hỏi trắc nghiệm.
- Tạo Flashcard.
- Lưu lịch sử hội thoại và học tập.

---

## 2.3 Quy trình hoạt động của hệ thống

Quy trình xử lý của AI Learning Assistant Platform bao gồm các bước sau:

### Giai đoạn xây dựng Knowledge Base

1. Người dùng tải tài liệu học tập lên hệ thống.
2. Backend tiếp nhận và trích xuất nội dung từ tài liệu.
3. Nội dung được chia thành các đoạn nhỏ (Chunking).
4. Hệ thống tạo Vector Embedding cho từng đoạn văn bản.
5. Vector Embedding được lưu trong PostgreSQL với pgvector, trong khi Metadata được lưu trong MongoDB.

### Giai đoạn trả lời câu hỏi

6. Người dùng nhập câu hỏi trên giao diện AI Chat.
7. Backend tạo Embedding cho câu hỏi.
8. Hệ thống thực hiện Semantic Search trong Knowledge Base.
9. Những đoạn tài liệu phù hợp nhất được truy xuất.
10. Backend kết hợp câu hỏi với các đoạn tài liệu để tạo Prompt.
11. Prompt được gửi tới Large Language Model (LLM).
12. AI sinh câu trả lời dựa trên ngữ cảnh của tài liệu.
13. Kết quả cùng nguồn tham khảo được trả về cho người dùng.

> **Hình 2.1. Quy trình hoạt động của AI Learning Assistant Platform sử dụng Retrieval-Augmented Generation (RAG).**

![Hình 2.1](/images/h3bl3.png)

---

## 2.4 Lợi ích của giải pháp

Việc áp dụng công nghệ Retrieval-Augmented Generation (RAG) kết hợp với nền tảng Amazon Web Services (AWS) mang lại nhiều lợi ích cho hệ thống.

### Đối với người dùng

- Tìm kiếm thông tin nhanh hơn trong tài liệu học tập.
- Nhận câu trả lời chính xác và bám sát nội dung tài liệu.
- Tiết kiệm thời gian đọc và tổng hợp kiến thức.
- Hỗ trợ ôn tập hiệu quả thông qua Summary, Quiz và Flashcard.
- Dễ dàng quản lý tài liệu và lịch sử học tập.

### Đối với hệ thống

- Giảm hiện tượng AI Hallucination.
- Tăng khả năng mở rộng nhờ triển khai trên AWS.
- Dễ dàng bảo trì và cập nhật bằng Docker Compose.
- Tự động hóa quy trình triển khai thông qua GitHub Actions và Amazon ECR.
- Giám sát hiệu năng bằng Amazon CloudWatch.
- Dễ dàng sao lưu và phục hồi dữ liệu với Amazon S3.

### Đối với tổ chức giáo dục

- Xây dựng kho tri thức tập trung cho từng môn học.
- Hỗ trợ giảng viên chia sẻ tài liệu hiệu quả.
- Nâng cao trải nghiệm học tập cho sinh viên.
- Tạo nền tảng để phát triển các ứng dụng AI trong giáo dục.

---

### Bảng 2.1. So sánh giữa Chatbot AI truyền thống và AI Learning Assistant Platform

| Tiêu chí | Chatbot AI truyền thống | AI Learning Assistant Platform |
|----------|--------------------------|--------------------------------|
| Nguồn dữ liệu | Kiến thức đã huấn luyện | Kiến thức huấn luyện + Knowledge Base |
| Trả lời theo tài liệu người dùng | Không | Có |
| Semantic Search | Không | Có |
| Retrieval-Augmented Generation (RAG) | Không | Có |
| Giảm AI Hallucination | Thấp | Cao |
| Hiển thị nguồn tham khảo | Không | Có |
| Summary | Không | Có |
| Quiz | Không | Có |
| Flashcard | Không | Có |
| Khả năng mở rộng trên AWS | Hạn chế | Có |

# Phần 3. Thiết kế và kiến trúc hệ thống

## 3.1 Kiến trúc tổng thể

AI Learning Assistant Platform được xây dựng theo mô hình **Client–Server** kết hợp với kiến trúc **Retrieval-Augmented Generation (RAG)** và được triển khai trên **Amazon Web Services (AWS)** nhằm xây dựng một nền tảng học tập thông minh có khả năng quản lý tài liệu, tìm kiếm ngữ nghĩa và hỗ trợ học tập bằng trí tuệ nhân tạo.

Hệ thống được thiết kế theo kiến trúc nhiều lớp (Layered Architecture), trong đó mỗi lớp đảm nhận một vai trò riêng biệt. Cách tổ chức này giúp hệ thống dễ mở rộng, dễ bảo trì và thuận lợi trong việc triển khai trên môi trường điện toán đám mây. Toàn bộ ứng dụng được đóng gói dưới dạng Docker Container và vận hành trên Amazon EC2 thông qua Docker Compose.

Kiến trúc hệ thống được chia thành năm lớp chính:

- **Client Layer:** Sinh viên và giảng viên truy cập hệ thống thông qua trình duyệt Web bằng giao thức HTTP hoặc HTTPS. Giao diện được xây dựng bằng Next.js và React, hỗ trợ các chức năng như quản lý môn học, tải tài liệu, AI Chat, Summary, Quiz, Flashcard và lịch sử học tập.

- **Application Layer:** Toàn bộ ứng dụng được triển khai trên **Amazon EC2** dưới dạng các **Docker Container** được quản lý bởi **Docker Compose**, bao gồm Nginx, Frontend, Backend, MongoDB, PostgreSQL với pgvector và MinIO. Nginx đóng vai trò Reverse Proxy tiếp nhận yêu cầu từ người dùng và chuyển tiếp đến các dịch vụ tương ứng.

- **AI & Data Layer:** Backend xử lý AI Chat, Retrieval-Augmented Generation (RAG), Knowledge Base, Document Processing và Semantic Search. PostgreSQL với **pgvector** lưu trữ Vector Embedding, MongoDB quản lý dữ liệu người dùng, hội thoại và cấu hình hệ thống, trong khi MinIO lưu trữ tài liệu học tập.

- **Infrastructure Layer:** Hệ thống được triển khai trên Amazon Web Services (AWS). Amazon EC2 cung cấp môi trường chạy ứng dụng, Amazon EBS lưu trữ Docker Volume và dữ liệu lâu dài, Amazon S3 lưu trữ các bản sao lưu. AWS IAM quản lý quyền truy cập, Security Group kiểm soát lưu lượng mạng và Elastic IP cung cấp địa chỉ truy cập cố định từ Internet.

- **DevOps & Monitoring Layer:** GitHub Actions và Amazon ECR hỗ trợ quy trình CI/CD. Khi mã nguồn được cập nhật lên GitHub Repository, Docker Image sẽ được xây dựng và đẩy lên Amazon ECR trước khi triển khai lên Amazon EC2. Amazon CloudWatch thu thập Logs và Metrics, CloudWatch Alarm gửi cảnh báo khi xảy ra sự cố, trong khi AWS Budgets hỗ trợ theo dõi chi phí sử dụng AWS.

Kiến trúc được thiết kế theo hướng **Production Lite**, phù hợp với quy mô MVP nhưng vẫn đáp ứng các yêu cầu về triển khai, bảo mật, giám sát, sao lưu và tự động hóa trên nền tảng AWS.

> **Hình 3.1. Kiến trúc tổng thể của AI Learning Assistant Platform.**

![Hình 3.1](/images/3.1.d.x.png)

---

## 3.2 Kiến trúc triển khai trên AWS

AI Learning Assistant Platform được triển khai trên **Amazon Web Services (AWS)** tại Region **US East (N. Virginia) – us-east-1**.

Toàn bộ hệ thống được triển khai trong một **Amazon VPC**. Máy chủ Amazon EC2 được đặt trong **Public Subnet** và gắn **Elastic IP** để người dùng có thể truy cập từ Internet thông qua giao thức HTTP hoặc HTTPS. Security Group được cấu hình để chỉ cho phép các cổng dịch vụ cần thiết như SSH (22), HTTP (80) và HTTPS (443), đồng thời hạn chế các truy cập không hợp lệ.

Bên trong Amazon EC2, Docker Compose quản lý các Docker Container của hệ thống gồm Nginx, Frontend, Backend, MongoDB, PostgreSQL với pgvector và MinIO. Các Container giao tiếp với nhau thông qua Docker Network nội bộ nhằm đảm bảo an toàn dữ liệu. Amazon EBS được sử dụng để lưu Docker Volume và dữ liệu lâu dài.

Để đảm bảo khả năng phục hồi dữ liệu, MongoDB, PostgreSQL và MinIO được sao lưu định kỳ lên **Amazon S3**. Amazon CloudWatch kết hợp với CloudWatch Alarm được sử dụng để giám sát hiệu năng, thu thập Logs và gửi cảnh báo khi xảy ra sự cố.

Quy trình triển khai được tự động hóa bằng **GitHub Actions** và **Amazon ECR**. Khi mã nguồn được cập nhật lên GitHub Repository, GitHub Actions sẽ tự động xây dựng Docker Image, đẩy Image lên Amazon ECR và triển khai phiên bản mới lên Amazon EC2.

### Bảng 3.1. Các dịch vụ AWS được sử dụng

| Dịch vụ AWS | Vai trò | Lý do lựa chọn |
|-------------|----------|----------------|
| Amazon VPC | Cung cấp môi trường mạng riêng cho hệ thống | Cô lập hạ tầng, tăng tính bảo mật |
| Public Subnet | Chứa Amazon EC2 | Cho phép hệ thống truy cập Internet |
| Internet Gateway | Kết nối Amazon VPC với Internet | Cho phép người dùng truy cập ứng dụng |
| Elastic IP | Cung cấp địa chỉ IP Public cố định | Thuận tiện truy cập và cấu hình tên miền |
| Amazon EC2 | Chạy toàn bộ AI Learning Assistant Platform | Dễ triển khai, quản trị và mở rộng |
| Amazon EBS | Lưu Docker Volume và dữ liệu lâu dài | Dữ liệu không bị mất khi khởi động lại EC2 |
| Amazon S3 | Sao lưu MongoDB, PostgreSQL và tài liệu học tập | Độ bền cao, chi phí thấp, dễ mở rộng |
| Amazon ECR | Lưu trữ Docker Images | Tích hợp tốt với GitHub Actions và EC2 |
| Amazon CloudWatch | Thu thập Metrics và Logs | Theo dõi hiệu năng hệ thống theo thời gian thực |
| CloudWatch Alarm | Gửi cảnh báo khi xảy ra sự cố | Phát hiện sớm các vấn đề vận hành |
| Amazon SNS | Gửi Email Notification | Thông báo tự động cho quản trị viên |
| AWS IAM | Quản lý IAM User và phân quyền | Đảm bảo nguyên tắc Least Privilege |
| Security Group | Kiểm soát truy cập mạng | Bảo vệ EC2 khỏi truy cập trái phép |
| AWS Budgets | Theo dõi và cảnh báo chi phí | Kiểm soát ngân sách AWS |

Kiến trúc hiện tại được tối ưu cho môi trường thực tập và giai đoạn MVP. Việc triển khai trên một Amazon EC2 giúp giảm chi phí vận hành nhưng vẫn đảm bảo khả năng mở rộng thông qua Docker Container, CI/CD và các dịch vụ quản trị của AWS.

> **Hình 3.2. Kiến trúc triển khai hệ thống trên AWS.**

![Hình 3.2](/images/3.2.d.s.png)

---

## 3.3 Thiết kế cơ sở dữ liệu

Hệ thống sử dụng mô hình lưu trữ kết hợp giữa cơ sở dữ liệu quan hệ, cơ sở dữ liệu NoSQL và Object Storage nhằm tối ưu hiệu năng cho từng loại dữ liệu.

### Bảng 3.2. Thành phần lưu trữ của hệ thống

| Thành phần | Vai trò |
|------------|----------|
| MongoDB | Lưu trữ thông tin người dùng, hội thoại, Knowledge Base và cấu hình hệ thống |
| PostgreSQL + pgvector | Lưu trữ Vector Embedding phục vụ Semantic Search và Retrieval-Augmented Generation |
| MinIO | Lưu trữ tài liệu học tập do người dùng tải lên |
| Amazon S3 | Sao lưu MongoDB, PostgreSQL và tài liệu học tập |
| Amazon EBS | Lưu Docker Volume và dữ liệu lâu dài của hệ thống |

MongoDB lưu dữ liệu nghiệp vụ của hệ thống, PostgreSQL với pgvector lưu trữ Vector Embedding phục vụ Semantic Search, MinIO lưu các tài liệu gốc của người dùng, trong khi Amazon S3 được sử dụng để sao lưu dữ liệu nhằm đảm bảo khả năng phục hồi khi xảy ra sự cố.

MongoDB, PostgreSQL và MinIO hoạt động trong Docker Network nội bộ và không được mở trực tiếp ra Internet nhằm tăng cường bảo mật.

> **Hình 3.3. Sơ đồ cơ sở dữ liệu của hệ thống.**

![Hình 3.3](/images/3.3.pr.drawio.png)

---

## 3.4 Quy trình hoạt động

Sau khi người dùng tải tài liệu lên hệ thống, AI Learning Assistant Platform thực hiện quy trình Retrieval-Augmented Generation (RAG) theo các bước sau:

1. Người dùng tải tài liệu học tập lên hệ thống.
2. Backend trích xuất nội dung từ tài liệu.
3. Tài liệu được chia thành các đoạn nhỏ (Chunking).
4. Hệ thống tạo Vector Embedding cho từng đoạn.
5. Embedding được lưu trong PostgreSQL với pgvector, trong khi Metadata được lưu trong MongoDB.
6. Người dùng gửi câu hỏi từ giao diện AI Chat.
7. Backend tạo Embedding cho câu hỏi và thực hiện Semantic Search trong Vector Database.
8. Các đoạn tài liệu liên quan được truy xuất và kết hợp với câu hỏi để tạo Prompt.
9. Prompt được gửi đến Large Language Model (LLM).
10. AI tạo câu trả lời dựa trên ngữ cảnh của tài liệu và trả kết quả kèm nguồn tham khảo cho người dùng.

Quy trình trên được chia thành hai giai đoạn chính:

- **Giai đoạn xây dựng Knowledge Base:** Bao gồm Upload, Document Processing, Chunking, Embedding và lưu trữ dữ liệu.
- **Giai đoạn AI Chat:** Bao gồm Semantic Search, Prompt Engineering và sinh câu trả lời bằng Large Language Model.

Việc tách biệt hai giai đoạn giúp hệ thống tái sử dụng Knowledge Base cho nhiều phiên hội thoại, giảm thời gian xử lý và nâng cao hiệu quả truy xuất dữ liệu.

> **Hình 3.4. Quy trình hoạt động của AI Learning Assistant Platform sử dụng RAG.**

![Hình 3.4](/images/3.4.p.r.png)

---

## 3.5 Công nghệ sử dụng

### Bảng 3.3. Công nghệ sử dụng trong hệ thống

| Thành phần | Công nghệ |
|------------|-----------|
| Frontend | Next.js, React, TypeScript |
| Backend | FastGPT (Customized), Node.js |
| AI Model | Google Gemini / OpenAI (LLMs) |
| AI Framework | Retrieval-Augmented Generation (RAG) |
| Database | MongoDB, PostgreSQL + pgvector |
| Object Storage | MinIO |
| Reverse Proxy | Nginx |
| Containerization | Docker, Docker Compose |
| Version Control | GitHub |
| CI/CD | GitHub Actions |
| Container Registry | Amazon ECR |
| Cloud Platform | Amazon EC2, Amazon EBS, Amazon S3 |
| Monitoring | Amazon CloudWatch, CloudWatch Alarm |
| Security | AWS IAM, Security Group |
| Cost Management | AWS Budgets |
# Phần 4. Triển khai và kiểm thử

## 4.1 Môi trường triển khai

AI Learning Assistant Platform được triển khai trên **Amazon Web Services (AWS)** tại Region **US East (N. Virginia) – us-east-1** theo mô hình **Production Lite**.

Toàn bộ hệ thống được triển khai trong một **Amazon VPC**, trong đó **Amazon EC2** được đặt tại **Public Subnet** và gắn **Elastic IP** để người dùng có thể truy cập từ Internet thông qua giao thức HTTP hoặc HTTPS. **Security Group** được cấu hình để chỉ cho phép các cổng dịch vụ cần thiết như SSH (22), HTTP (80) và HTTPS (443), đảm bảo an toàn cho hệ thống.

Ứng dụng được đóng gói dưới dạng **Docker Container** và quản lý bằng **Docker Compose**, bao gồm **Nginx**, **Frontend (Next.js/React)**, **Backend (FastGPT Customized)**, **MongoDB**, **PostgreSQL với pgvector** và **MinIO**. Các Container giao tiếp với nhau thông qua Docker Network nội bộ nhằm đảm bảo tính bảo mật và ổn định trong quá trình vận hành.

Hệ thống sử dụng **Amazon EBS** để lưu trữ dữ liệu lâu dài, **Amazon S3** để sao lưu dữ liệu, **Amazon ECR** để quản lý Docker Image, **GitHub Actions** để tự động hóa quy trình CI/CD, **Amazon CloudWatch** để giám sát hệ thống, cùng **AWS IAM**, **Security Group** và **AWS Budgets** để quản lý bảo mật và chi phí.

### Cấu hình môi trường

| Thành phần | Công nghệ / Dịch vụ |
|------------|---------------------|
| Cloud Platform | Amazon Web Services (AWS) |
| Region | us-east-1 (N. Virginia) |
| Network | Amazon VPC, Public Subnet |
| Compute | Amazon EC2 |
| Public IP | Elastic IP |
| Persistent Storage | Amazon EBS |
| Container | Docker, Docker Compose |
| Reverse Proxy | Nginx |
| Frontend | Next.js, React |
| Backend | FastGPT (Customized) |
| Database | MongoDB, PostgreSQL + pgvector |
| Object Storage | MinIO |
| Container Registry | Amazon ECR |
| CI/CD | GitHub Actions |
| Monitoring | Amazon CloudWatch |
| Backup Storage | Amazon S3 |
| Security | AWS IAM, Security Group |
| Cost Monitoring | AWS Budgets |

> **Hình 4.1. Môi trường triển khai AI Learning Assistant Platform trên AWS.**

![Hình 4.1](/images/4.1.d.x.png)

---

## 4.2 Quy trình triển khai hệ thống

Quy trình triển khai hệ thống được thực hiện theo các bước sau:

1. Tạo và cấu hình hạ tầng AWS gồm **Amazon VPC**, **Public Subnet**, **Internet Gateway**, **Security Group**, **Elastic IP** và **Amazon EC2**.
2. Tạo **IAM User** và phân quyền theo nguyên tắc **Least Privilege** để phục vụ quá trình triển khai.
3. Cài đặt **Docker** và **Docker Compose** trên Amazon EC2.
4. Cấu hình các biến môi trường và Docker Compose cho toàn bộ hệ thống.
5. Đẩy mã nguồn lên **GitHub Repository**.
6. **GitHub Actions** tự động Build Docker Image và đẩy Image lên **Amazon ECR**.
7. Amazon EC2 tải Docker Image mới từ Amazon ECR và khởi động các Container bằng **Docker Compose**.
8. **Amazon CloudWatch** thu thập Metrics và Logs để giám sát trạng thái hoạt động của hệ thống.
9. Dữ liệu MongoDB, PostgreSQL và MinIO được sao lưu định kỳ lên **Amazon S3** nhằm đảm bảo khả năng phục hồi dữ liệu.

Quy trình trên giúp tự động hóa việc triển khai, giảm thiểu thao tác thủ công và đảm bảo hệ thống luôn được cập nhật nhanh chóng khi có phiên bản mới.

> **Hình 4.2. Quy trình triển khai AI Learning Assistant Platform trên AWS.**

![Hình 4.2](/images/4.2.d.x..png)

---

## 4.3 Kiểm thử hệ thống

Sau khi triển khai thành công, hệ thống được kiểm thử nhằm đánh giá tính ổn định, khả năng hoạt động và sự tương thích giữa các thành phần của hệ thống.

### Kết quả kiểm thử

| Chức năng | Nội dung kiểm thử | Kết quả |
|-----------|-------------------|----------|
| Đăng nhập và xác thực người dùng | Kiểm tra đăng nhập và phân quyền | Thành công |
| Quản lý môn học | Tạo, chỉnh sửa và quản lý môn học | Thành công |
| Upload tài liệu học tập | Tải tài liệu lên hệ thống | Thành công |
| Xây dựng Knowledge Base | Xử lý tài liệu và tạo Vector Embedding | Thành công |
| AI Chat (RAG) | Trả lời câu hỏi dựa trên tài liệu | Thành công |
| Summary | Tóm tắt nội dung tài liệu | Thành công |
| Quiz | Sinh câu hỏi trắc nghiệm | Thành công |
| Flashcard | Tạo Flashcard từ tài liệu | Thành công |
| Docker Compose | Khởi động và quản lý Container | Thành công |
| GitHub Actions | Build Docker Image | Thành công |
| Amazon ECR | Push/Pull Docker Image | Thành công |
| Amazon CloudWatch | Thu thập Logs và Metrics | Thành công |

Kết quả kiểm thử cho thấy toàn bộ Docker Container hoạt động ổn định, các chức năng chính đáp ứng yêu cầu của nền tảng và quá trình Retrieval-Augmented Generation (RAG) hoạt động chính xác với dữ liệu được tải lên.

> **Hình 4.3. Kết quả kiểm thử AI Learning Assistant Platform.**

![Hình 4.3](/images/4.3.d.x.png)

---

## 4.4 Giám sát và vận hành

Trong quá trình vận hành, **Amazon CloudWatch** được sử dụng để giám sát hiệu năng và trạng thái hoạt động của hệ thống. CloudWatch thu thập Metrics và Logs từ Amazon EC2 cũng như các Docker Container để hỗ trợ theo dõi và phát hiện sự cố.

Các chỉ số được theo dõi bao gồm:

- CPU Utilization
- Memory Usage
- Disk Usage
- Network Traffic
- Docker Container Logs
- System Status Check

**CloudWatch Alarm** được cấu hình để gửi cảnh báo khi các chỉ số vượt quá ngưỡng cho phép. Thông báo được gửi qua **Amazon SNS** đến quản trị viên nhằm kịp thời xử lý sự cố và đảm bảo hệ thống hoạt động ổn định.

Bên cạnh đó, dữ liệu của MongoDB, PostgreSQL và các tài liệu học tập được sao lưu định kỳ lên **Amazon S3** nhằm đảm bảo khả năng phục hồi dữ liệu khi xảy ra sự cố. **AWS Budgets** được sử dụng để theo dõi chi phí và gửi cảnh báo khi mức sử dụng tài nguyên vượt quá ngân sách đã thiết lập.

### Nội dung giám sát

| Thành phần | Nội dung giám sát |
|------------|-------------------|
| Amazon EC2 | CPU, Memory, Disk, Network |
| Docker Containers | Trạng thái hoạt động và Logs |
| MongoDB | Dung lượng lưu trữ và kết nối |
| PostgreSQL | Hiệu năng truy vấn và dung lượng |
| MinIO | Dung lượng Object Storage |
| Amazon CloudWatch | Metrics, Logs và Alarm |
| Amazon S3 | Trạng thái sao lưu dữ liệu |
| AWS Budgets | Chi phí sử dụng AWS |
# Phần 5. Bảo mật và tối ưu chi phí

## 5.1 Bảo mật hệ thống

AI Learning Assistant Platform lưu trữ tài khoản người dùng, tài liệu học tập, Knowledge Base và lịch sử hội thoại. Vì vậy, hệ thống áp dụng nhiều biện pháp bảo mật nhằm đảm bảo tính bảo mật, toàn vẹn và khả năng sẵn sàng của dữ liệu khi triển khai trên **Amazon Web Services (AWS)**.

Các biện pháp bảo mật được áp dụng bao gồm:

- Sử dụng **IAM User** thay cho Root User trong quá trình triển khai và quản trị hệ thống.
- Áp dụng nguyên tắc **Least Privilege** thông qua **AWS IAM**, chỉ cấp quyền cần thiết cho từng người dùng và dịch vụ.
- Kích hoạt **Multi-Factor Authentication (MFA)** đối với tài khoản quản trị AWS nhằm tăng cường bảo mật.
- Cấu hình **Security Group** để chỉ cho phép các cổng dịch vụ cần thiết như SSH (22), HTTP (80) và HTTPS (443).
- Sử dụng **HTTPS** để mã hóa dữ liệu trao đổi giữa người dùng và hệ thống.
- Lưu trữ API Key và thông tin cấu hình bằng **Environment Variables**, không lưu trực tiếp trong mã nguồn.
- MongoDB, PostgreSQL và MinIO chỉ hoạt động trong **Docker Network** nội bộ và không được truy cập trực tiếp từ Internet.
- Giới hạn quyền truy cập đối với **Amazon S3**, chỉ cho phép các dịch vụ và người dùng được cấp quyền truy cập dữ liệu sao lưu.
- Sử dụng **Amazon CloudWatch** và **CloudWatch Alarm** để giám sát trạng thái hoạt động của hệ thống và phát hiện sớm các sự cố.
- Theo dõi chi phí sử dụng tài nguyên bằng **AWS Budgets** nhằm tránh phát sinh chi phí ngoài dự kiến.

Những biện pháp trên giúp hệ thống đáp ứng các yêu cầu cơ bản về bảo mật khi triển khai trên nền tảng AWS, đồng thời giảm thiểu các rủi ro liên quan đến truy cập trái phép và mất mát dữ liệu.

---

## 5.2 Chi phí triển khai dự kiến

AI Learning Assistant Platform được triển khai theo mô hình **Production Lite**, tập trung tối ưu chi phí nhưng vẫn đảm bảo khả năng vận hành ổn định, dễ mở rộng và đáp ứng các yêu cầu của giai đoạn MVP.

### Bảng 5.1. Chi phí triển khai dự kiến

| Dịch vụ AWS | Vai trò | Chi phí dự kiến (USD/Tháng) |
|-------------|----------|----------------------------:|
| Amazon EC2 (t3.large) | Chạy toàn bộ ứng dụng | 60 |
| Amazon EBS (50 GB) | Lưu trữ dữ liệu lâu dài | 4 |
| Amazon S3 | Sao lưu dữ liệu | 2 |
| Amazon ECR | Lưu trữ Docker Image | 1 |
| Amazon CloudWatch | Giám sát hệ thống | 3 |
| Data Transfer | Lưu lượng Internet | 8 |
| Google Gemini / OpenAI API | Xử lý AI | 15–50 |
| **Tổng chi phí dự kiến** |  | **93–128 USD/Tháng** |

### Các giải pháp tối ưu chi phí

Để giảm chi phí vận hành, hệ thống áp dụng các giải pháp sau:

- Triển khai toàn bộ dịch vụ trên một **Amazon EC2** trong giai đoạn MVP.
- Theo dõi mức sử dụng tài nguyên bằng **AWS Budgets**.
- Lưu trữ dữ liệu sao lưu trên **Amazon S3** thay vì duy trì nhiều bản sao trên EC2.
- Xóa các tài nguyên AWS không còn sử dụng sau khi hoàn thành quá trình kiểm thử.
- Tối ưu số lượng yêu cầu gửi tới mô hình AI nhằm giảm chi phí xử lý.
- Chỉ mở rộng sang **Application Load Balancer** và **Amazon ECS** khi số lượng người dùng tăng.

---

# Phần 6. Đánh giá và hướng phát triển

## 6.1 Đánh giá theo AWS Well-Architected Framework

AI Learning Assistant Platform được đánh giá dựa trên sáu trụ cột của **AWS Well-Architected Framework** nhằm đảm bảo hệ thống đáp ứng các yêu cầu về vận hành, bảo mật, hiệu năng và tối ưu chi phí.

### Bảng 6.1. Đánh giá hệ thống

| Trụ cột | Nội dung áp dụng |
|----------|------------------|
| Operational Excellence | Docker Compose, GitHub Actions, Amazon CloudWatch |
| Security | AWS IAM, Security Group, HTTPS, Environment Variables |
| Reliability | Amazon S3 Backup, Docker Restart Policy, CloudWatch Alarm |
| Performance Efficiency | PostgreSQL + pgvector, Retrieval-Augmented Generation (RAG) |
| Cost Optimization | Amazon EC2, AWS Budgets, Amazon CloudWatch |
| Sustainability | Có thể mở rộng lên Amazon ECS và Application Load Balancer |

Kết quả đánh giá cho thấy AI Learning Assistant Platform đáp ứng các nguyên tắc cơ bản của AWS Well-Architected Framework đối với một hệ thống Generative AI triển khai trên AWS. Kiến trúc hiện tại phù hợp với giai đoạn MVP và sẵn sàng mở rộng khi số lượng người dùng tăng trong tương lai.

> **Hình 6.1. Đánh giá AI Learning Assistant Platform theo AWS Well-Architected Framework.**

![Hình 6.1](/images/6.1.p.r.png)

---

## 6.2 Hướng phát triển

Trong tương lai, hệ thống có thể được mở rộng theo các hướng sau:

- Triển khai **Amazon ECS** hoặc **Amazon EKS** nhằm nâng cao khả năng mở rộng và tính sẵn sàng.
- Sử dụng **Application Load Balancer (ALB)** kết hợp **Auto Scaling** để hỗ trợ nhiều người dùng đồng thời.
- Mở rộng Knowledge Base cho nhiều môn học, nhiều khoa và nhiều nhóm người dùng.
- Tích hợp thêm các mô hình AI như **Amazon Bedrock**, **Google Gemini** hoặc **OpenAI**.
- Phát triển các tính năng AI như AI Tutor, Mindmap, Speech-to-Text và Text-to-Speech.
- Hoàn thiện hệ thống Monitoring, Alerting và Backup nhằm nâng cao độ tin cậy.
- Xây dựng Dashboard giám sát tập trung bằng Amazon CloudWatch Dashboard.
- Tăng cường bảo mật bằng AWS WAF và AWS Shield khi triển khai trên môi trường Internet.

Với kiến trúc hiện tại, AI Learning Assistant Platform có thể đáp ứng tốt nhu cầu triển khai trong giai đoạn MVP và sẵn sàng mở rộng khi quy mô hệ thống tăng lên trong tương lai.

---

# Phần 7. Kết luận

## 7.1 Kết quả đạt được

AI Learning Assistant Platform được xây dựng nhằm hỗ trợ người học khai thác tài liệu học tập thông qua trí tuệ nhân tạo kết hợp với công nghệ **Retrieval-Augmented Generation (RAG)**. Hệ thống cho phép người dùng tải lên tài liệu, xây dựng Knowledge Base và tương tác với AI bằng ngôn ngữ tự nhiên, từ đó nâng cao độ chính xác của câu trả lời so với các chatbot AI truyền thống.

Bên cạnh chức năng hỏi đáp, hệ thống còn tích hợp các tính năng hỗ trợ học tập như quản lý tài liệu, tóm tắt bài học, tạo câu hỏi trắc nghiệm, Flashcard và lưu lịch sử hội thoại. Toàn bộ ứng dụng được triển khai trên **Amazon Web Services (AWS)**, đáp ứng các yêu cầu về hiệu năng, bảo mật, khả năng mở rộng và quản trị hệ thống.

Thông qua quá trình thực hiện dự án, các mục tiêu chính đã đạt được gồm:

- Xây dựng nền tảng AI Learning Assistant dựa trên FastGPT.
- Ứng dụng Retrieval-Augmented Generation (RAG) nhằm nâng cao chất lượng câu trả lời.
- Triển khai hệ thống trên Amazon EC2 bằng Docker Compose.
- Tích hợp MongoDB, PostgreSQL, MinIO và các dịch vụ AWS.
- Thiết lập quy trình CI/CD với GitHub Actions và Amazon ECR.
- Xây dựng hệ thống giám sát bằng Amazon CloudWatch.
- Hoàn thiện cơ chế sao lưu dữ liệu trên Amazon S3.
- Áp dụng các biện pháp bảo mật theo AWS Best Practices.

---

## 7.2 Hạn chế

Mặc dù đã đáp ứng các mục tiêu đề ra, hệ thống vẫn còn một số hạn chế:

- Kiến trúc hiện tại sử dụng một Amazon EC2 nên chưa đáp ứng yêu cầu High Availability.
- Chưa triển khai Auto Scaling và Application Load Balancer.
- Chưa triển khai Multi-AZ cho các thành phần cơ sở dữ liệu.
- Chất lượng câu trả lời vẫn phụ thuộc vào nội dung và chất lượng của tài liệu được tải lên.
- Chưa hỗ trợ ứng dụng trên nền tảng di động.
- Một số tính năng AI nâng cao vẫn đang trong giai đoạn nghiên cứu.

---

## 7.3 Hướng phát triển

Trong tương lai, AI Learning Assistant Platform sẽ được mở rộng theo các hướng sau:

- Triển khai Amazon ECS hoặc Amazon EKS để nâng cao khả năng mở rộng.
- Sử dụng Application Load Balancer và Auto Scaling nhằm hỗ trợ nhiều người dùng đồng thời.
- Tích hợp Amazon Bedrock, Google Gemini hoặc OpenAI.
- Mở rộng các chức năng AI như AI Tutor, Mindmap, Speech-to-Text và Text-to-Speech.
- Phát triển ứng dụng trên Android và iOS.
- Tối ưu quy trình Retrieval-Augmented Generation (RAG).
- Hoàn thiện cơ chế Backup và Disaster Recovery.
- Tăng cường giám sát và bảo mật theo các tiêu chuẩn AWS.

Những định hướng trên sẽ giúp AI Learning Assistant Platform trở thành một nền tảng học tập thông minh có khả năng phục vụ nhiều đối tượng người dùng và đáp ứng tốt hơn nhu cầu trong môi trường giáo dục hiện đại.

---

## 7.4 Kết luận

AI Learning Assistant Platform là một giải pháp hỗ trợ học tập ứng dụng trí tuệ nhân tạo, được xây dựng trên nền tảng FastGPT và triển khai trên Amazon Web Services (AWS). Việc kết hợp công nghệ Retrieval-Augmented Generation (RAG) với Knowledge Base giúp hệ thống cung cấp câu trả lời bám sát tài liệu học tập, góp phần nâng cao hiệu quả học tập và giảm hiện tượng AI Hallucination.

Kiến trúc hệ thống được thiết kế theo hướng mở, tích hợp Docker Compose, GitHub Actions, Amazon ECR, Amazon CloudWatch và các dịch vụ AWS nhằm đảm bảo khả năng triển khai, vận hành và mở rộng trong tương lai.

Dự án không chỉ đáp ứng mục tiêu xây dựng một trợ lý học tập thông minh mà còn giúp nhóm tích lũy kinh nghiệm thực tế trong việc thiết kế, triển khai, giám sát và vận hành một ứng dụng Generative AI trên nền tảng Amazon Web Services. Đây là nền tảng quan trọng để tiếp tục nghiên cứu và phát triển các hệ thống AI phục vụ giáo dục trong tương lai.