---
title: "5.1 Giới thiệu"
date: 2026-08-09
weight: 1
chapter: false
pre: " <b> 5.1. </b> "
---

# 5.1 Giới thiệu

## 5.1.1 Bối cảnh

Sự phát triển nhanh của Trí tuệ nhân tạo, mô hình ngôn ngữ lớn và điện toán đám mây tạo ra nhiều cơ hội ứng dụng trong giáo dục. AI không chỉ hỗ trợ tìm kiếm thông tin mà còn có thể giải thích kiến thức, hướng dẫn học tập, tạo câu hỏi ôn tập và tương tác với người học bằng ngôn ngữ tự nhiên.

Trong thực tế, sinh viên và giảng viên thường sử dụng nhiều loại tài liệu như giáo trình, slide, bài thực hành, tài liệu tham khảo và bài nghiên cứu. Khi số lượng tài liệu tăng, việc tìm lại một nội dung cụ thể trở nên mất thời gian và làm giảm hiệu quả học tập.

Các chatbot AI thông thường chủ yếu dựa vào kiến thức có sẵn từ quá trình huấn luyện. Chúng không tự động hiểu tài liệu riêng của người dùng và có thể tạo câu trả lời sai hoặc không có căn cứ, thường được gọi là **AI Hallucination**.

## 5.1.2 Bài toán cần giải quyết

Dự án cần giải quyết các yêu cầu chính:

- Cho phép người dùng tập trung tài liệu học tập vào một nền tảng.
- Tìm kiếm nội dung theo ý nghĩa thay vì chỉ khớp từ khóa.
- Tạo câu trả lời dựa trên tài liệu do người dùng cung cấp.
- Giảm thông tin không chính xác và tăng khả năng truy vết nguồn.
- Kết hợp học lý thuyết, hỏi đáp, luyện tập và theo dõi tiến độ.
- Triển khai hệ thống trên AWS với chi phí phù hợp phạm vi đồ án.

## 5.1.3 Giải pháp đề xuất

**AI Learning Assistant Platform** là nền tảng trợ lý học tập thông minh được tùy biến từ FastGPT và xây dựng theo phương pháp **Retrieval-Augmented Generation (RAG)**.

Khi người dùng tải tài liệu lên, hệ thống trích xuất nội dung, chia tài liệu thành các đoạn nhỏ, tạo vector embedding và xây dựng Knowledge Base. Khi có câu hỏi, hệ thống tìm các đoạn liên quan, ghép chúng vào ngữ cảnh và gửi prompt đến mô hình ngôn ngữ lớn để tạo câu trả lời.

So với chatbot truyền thống, giải pháp có ba điểm khác biệt:

1. Câu trả lời được tạo dựa trên tài liệu riêng của người dùng.
2. Semantic Search giúp tìm nội dung liên quan ngay cả khi câu hỏi không dùng đúng từ khóa trong tài liệu.
3. Knowledge Base có thể tái sử dụng cho nhiều cuộc hội thoại và chức năng học tập.

Hình 5.1: Trang chính AI Learning Assistant sau khi đăng nhập.  

![Trang chính AI Learning Assistant sau khi đăng nhập](/images/hinh5.1-wshop.png)

## 5.1.4 Mục tiêu dự án

### Mục tiêu chức năng

- Quản lý lộ trình, môn học và nội dung bài học AWS.
- Cho phép tải lên và quản lý tài liệu học tập.
- Xây dựng Knowledge Base từ tài liệu.
- Cung cấp trợ lý với các chế độ Giải thích, Hướng dẫn và Luyện thi.
- Hỗ trợ hội thoại nhiều lượt và duy trì ngữ cảnh.
- Tóm tắt tài liệu và tạo câu hỏi ôn tập.
- Cung cấp bài luyện tập, thẻ nhớ và lịch sử học tập.
- Hiển thị nguồn tham khảo khi workflow hỗ trợ.

### Mục tiêu kỹ thuật

- Container hóa ứng dụng bằng Docker và Docker Compose.
- Triển khai hệ thống trên Amazon EC2.
- Lưu Docker image theo phiên bản trong Amazon ECR.
- Tự động build bằng GitHub Actions.
- Sử dụng MongoDB, PostgreSQL/pgvector, Redis và MinIO đúng vai trò.
- Sao lưu dữ liệu cần thiết trên Amazon S3.
- Giám sát bằng CloudWatch, Alarm và SNS.
- Tự động bật/tắt EC2 bằng Lambda và EventBridge.
- Theo dõi chi phí bằng AWS Budgets.

![Hình5.1.1 Lộ trình](/images/5.1.1.wrokshop.png)
![Hình5.1.2 Trợ lý AI](/images/hinh5.1-wshop.png)
![Hình5.1.3 Trợ lý tài liệu (trợ lý bài học)](/images/hinh5.1.3.wrokshop.png)
![Hình5.1.4 Bài luyện tập](/images/hinh5.1.4.workshop.png)
![Hình5.1.5 Thẻ nhớ mặt trước](/images/5.1.5.workshomt.png)
![Hình5.1.5 Thẻ nhớ mặt sau](/images/hinh1.1.5bworkshop.png)


## 5.1.5 Phạm vi dự án

### Phạm vi chức năng

Workshop tập trung vào phiên bản MVP với các chức năng học tập cốt lõi: quản lý nội dung, hỏi đáp AI dựa trên RAG, đọc tài liệu, bài luyện tập, thẻ nhớ và lịch sử hoạt động.

### Phạm vi triển khai

Hệ thống sử dụng mô hình **Production Lite** trên một Amazon EC2 instance. Các dịch vụ ứng dụng chạy bằng Docker Compose; EBS lưu volume; ECR lưu image; S3 lưu backup; CloudWatch cung cấp giám sát; Lambda và EventBridge hỗ trợ tự động hóa.

### Ngoài phạm vi hiện tại

- High Availability trên nhiều Availability Zone.
- Auto Scaling và container orchestration quy mô lớn.
- Managed database cho toàn bộ thành phần dữ liệu.
- Disaster Recovery đa Region.
- Phân tích học tập nâng cao và dashboard giảng viên hoàn chỉnh.

Các nội dung này được xem là hướng phát triển sau giai đoạn MVP.

## 5.1.6 Tổng quan quy trình hoạt động

Luồng sử dụng của người học:

```text
Đăng nhập
   ↓
Chọn lộ trình hoặc môn học
   ↓
Mở bài học / tải tài liệu
   ↓
Đặt câu hỏi cho trợ lý AI
   ↓
Nhận câu trả lời dựa trên Knowledge Base
   ↓
Ôn tập bằng câu hỏi và thẻ nhớ
   ↓
Theo dõi lịch sử học tập
```

Luồng vận hành của hệ thống:

```text
Source code → GitHub Actions → Amazon ECR → Amazon EC2

Người dùng → Nginx → AI Learning Assistant → Data & AI Services

CloudWatch → Alarm → SNS

EventBridge → Lambda → Start/Stop EC2
```
![Hình5.1.6  Sơ đồ quy trình hoạt động từ người dùng đến các chức năng học tập và dịch vụ AWS.  ](/images/5.1.6ws.png)
## 5.1.7 Giá trị của giải pháp

Đối với người học, nền tảng giúp giảm thời gian tìm tài liệu, cung cấp giải thích theo ngữ cảnh và kết hợp học–hỏi–luyện tập trong một quy trình thống nhất.

Đối với người quản trị, kiến trúc container giúp quản lý dịch vụ rõ ràng; AWS cung cấp hạ tầng triển khai, lưu trữ, giám sát, cảnh báo, tự động hóa và kiểm soát chi phí.

Giải pháp có thể được mở rộng cho trường học, trung tâm đào tạo hoặc doanh nghiệp cần xây dựng hệ thống hỏi đáp thông minh dựa trên tài liệu nội bộ.

