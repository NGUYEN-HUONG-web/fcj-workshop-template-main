---
title: "Chia sẻ và đóng góp ý kiến"
date: 2026-08-09
weight: 7
chapter: false
pre: "<b>7. </b>"
---


## 1. Cảm nhận chung

Chương trình **First Cloud AI Journey – AWS Workforce Bootcamp** mang đến cho em cơ hội tiếp cận AWS thông qua các hoạt động thực hành và áp dụng kiến thức vào một sản phẩm cụ thể.

Việc kết hợp worklog, bài blog, sự kiện chuyên môn, hoạt động nhóm và dự án cuối kỳ giúp em tìm hiểu về các dịch vụ AWS, đồng thời phát triển khả năng:

- Tự nghiên cứu tài liệu kỹ thuật.
- Ghi chép quá trình học tập.
- Giải quyết vấn đề kỹ thuật.
- Làm việc và phối hợp theo nhóm.
- Trình bày kết quả rõ ràng.
- Đánh giá công việc đã hoàn thành và xác định những hạn chế còn tồn tại.

Điểm em đặc biệt đánh giá cao là chương trình khuyến khích học viên chủ động học tập và tự giải quyết vấn đề.

Thay vì chỉ tập trung vào lý thuyết, em có cơ hội làm việc trực tiếp với các công nghệ và dịch vụ như:

- Docker.
- Amazon EC2.
- Amazon EBS.
- Amazon S3.
- AWS Identity and Access Management.
- Amazon CloudWatch.
- AWS Budgets.
- Retrieval-Augmented Generation.

Thông qua quá trình triển khai dự án RAG Chat, em có thể kiểm tra những nội dung đã hoàn thành, xác định giới hạn của kiến trúc hiện tại và đề xuất các hướng cải thiện trong tương lai.

## 2. Những điều em hài lòng

### 2.1 Nội dung có tính thực tiễn

Chương trình cung cấp nội dung có tính thực tế và tạo điều kiện để học viên làm việc với các dịch vụ AWS thông dụng.

Thông qua các bài tập và hoạt động dự án, em hiểu rõ hơn cách nhiều dịch vụ AWS phối hợp trong một hệ thống thay vì chỉ tìm hiểu từng dịch vụ riêng lẻ.

### 2.2 Các buổi chia sẻ chuyên môn

Các buổi chia sẻ và sự kiện chuyên môn giúp em mở rộng kiến thức về:

- Điện toán đám mây.
- Trí tuệ nhân tạo.
- Retrieval-Augmented Generation.
- Chứng chỉ AWS.
- Kinh nghiệm làm việc thực tế.
- Định hướng nghề nghiệp trong lĩnh vực Cloud và AI.

Các sự kiện này cũng giúp em có thêm góc nhìn về cách công nghệ được ứng dụng trong môi trường chuyên nghiệp.

### 2.3 Hoạt động dự án nhóm

Quá trình thực hiện dự án nhóm giúp em học cách:

- Phân chia trách nhiệm.
- Theo dõi tiến độ.
- Trao đổi khi gặp vấn đề.
- Thống nhất nội dung kỹ thuật.
- Kết hợp các phần việc riêng thành một sản phẩm chung.
- Hỗ trợ các thành viên khác khi cần thiết.

Đây là cơ hội để em cải thiện kỹ năng cộng tác và hiểu rõ hơn trách nhiệm của từng thành viên trong nhóm.

### 2.4 Worklog và bài blog

Yêu cầu viết worklog và blog giúp em hình thành thói quen ghi lại quá trình học tập thay vì chỉ tập trung vào kết quả cuối cùng.

Worklog giúp em:

- Theo dõi tiến độ hằng tuần.
- Ghi lại những công việc đã hoàn thành.
- Xác định các vấn đề hiện tại.
- Lập kế hoạch cho giai đoạn tiếp theo.
- Đánh giá sự tiến bộ của bản thân.

Các bài blog giúp em luyện tập cách giải thích kiến thức kỹ thuật rõ ràng và có cấu trúc.

### 2.5 Workshop cuối kỳ

Workshop cuối kỳ tạo cơ hội để em tổng hợp kiến thức đã học thành một quy trình hoàn chỉnh mà người khác có thể làm theo.

Quá trình viết tài liệu workshop giúp em chú ý hơn đến:

- Cấu trúc tài liệu.
- Trình tự các bước thực hiện.
- Câu lệnh triển khai.
- Hình ảnh minh chứng.
- Kết quả mong đợi.
- Những lỗi có thể xảy ra.
- Cách kiểm tra sau mỗi bước.

## 3. Những khó khăn em gặp phải

### 3.1 Khối lượng kiến thức lớn

Chương trình bao gồm một lượng kiến thức tương đối lớn về AWS, Docker, RAG và triển khai ứng dụng.

Trong khi đó, thời gian dành cho việc học, triển khai, kiểm thử và hoàn thiện báo cáo còn giới hạn.

Một số chủ đề cần được nghiên cứu sâu hơn, đặc biệt là:

- Bảo mật hệ thống.
- Quản lý secret.
- Sao lưu và khôi phục.
- Giám sát tập trung.
- Đánh giá chất lượng RAG.
- Kiến trúc có khả năng mở rộng.

### 3.2 Xử lý lỗi triển khai

Một số lỗi chỉ xuất hiện khi build Docker image hoặc triển khai ứng dụng lên EC2.

Quá trình xử lý thường yêu cầu kiểm tra nhiều lớp:

```text
Mã nguồn
→ Docker image
→ Docker container
→ Cổng dịch vụ
→ Security Group
→ EC2
→ EBS
→ IAM
→ Các dịch vụ AWS liên quan
```

Việc xác định nguyên nhân gốc đôi khi mất nhiều thời gian vì lỗi có thể đến từ cấu hình, quyền truy cập, kết nối mạng hoặc môi trường chạy.

### 3.3 Thu thập bằng chứng kỹ thuật

Bằng chứng kỹ thuật đôi lúc được thu thập quá muộn.

Do đó, một số bài kiểm thử không có đầy đủ ảnh trước và sau, bao gồm:

- Kiểm tra persistence.
- Kiểm tra container restart.
- Kiểm tra sao lưu dữ liệu.
- Kiểm tra khôi phục dữ liệu.
- Kiểm tra quyền IAM.
- Kiểm tra cảnh báo chi phí.

Trong các dự án tiếp theo, em cần xác định trước những bằng chứng cần thu thập và lưu lại kết quả ngay sau mỗi bài kiểm thử.

### 3.4 Chi phí và hạn mức dịch vụ

Chi phí Cloud và quota của các dịch vụ bên ngoài cần được theo dõi trong suốt quá trình thử nghiệm.

Nếu không kiểm soát phù hợp, những tài nguyên không còn sử dụng vẫn có thể tiếp tục phát sinh chi phí.

Em cần chú ý hơn đến:

- Trạng thái EC2.
- Dung lượng lưu trữ EBS.
- Dữ liệu lưu trên Amazon S3.
- Lưu lượng mạng.
- Quota của model AI.
- Ngân sách và cảnh báo chi phí.
- Những tài nguyên không còn được sử dụng.

## 4. Đề xuất cho chương trình

### 4.1 Mở thêm ngày làm việc tại văn phòng

Em đề xuất chương trình mở thêm nhiều ngày hoặc khung giờ để sinh viên đăng ký tham gia trực tiếp tại văn phòng.

Chương trình có số lượng học viên tương đối đông, nhưng số ngày và lượt tham dự được phê duyệt còn hạn chế. Điều này khiến nhiều sinh viên khó sắp xếp thời gian để có trải nghiệm làm việc trực tiếp.

Việc bổ sung ngày hoặc khung giờ có thể:

- Tạo cơ hội công bằng hơn cho sinh viên.
- Cho phép sinh viên gặp mentor trực tiếp.
- Tăng khả năng trao đổi giữa các nhóm dự án.
- Hỗ trợ xử lý vấn đề kỹ thuật nhanh hơn.
- Giúp sinh viên trải nghiệm môi trường làm việc thực tế.
- Tạo thêm cơ hội kết nối và học tập đồng đẳng.

### 4.2 Cung cấp lộ trình theo trình độ

Chương trình có thể cung cấp các lộ trình học tập dựa trên nền tảng và trình độ của học viên.

Ví dụ:

- Lộ trình AWS cơ bản cho sinh viên chưa có kinh nghiệm Cloud.
- Lộ trình DevOps cơ bản cho sinh viên đến từ lĩnh vực AI hoặc Data.
- Lộ trình AI và RAG cho sinh viên có nền tảng phát triển phần mềm.
- Nội dung nâng cao cho sinh viên đã có chứng chỉ hoặc kinh nghiệm AWS.

Cấu trúc này có thể giúp học viên xây dựng nền tảng cần thiết trước khi bắt đầu những dự án phức tạp hơn.

### 4.3 Tổ chức thêm workshop thực hành

Chương trình có thể tổ chức thêm các workshop hoặc phòng lab về:

- Terraform.
- AWS Lambda.
- Amazon API Gateway.
- CI/CD.
- AWS Secrets Manager.
- Amazon CloudWatch.
- Sao lưu và khôi phục sau thảm họa.
- Bảo mật container.
- Kiến trúc serverless.
- Đánh giá RAG.

Những phiên thực hành theo từng chủ đề sẽ giúp học viên hiểu rõ hơn cách áp dụng các dịch vụ này vào dự án thực tế.

### 4.4 Tăng cơ hội trình bày và thảo luận

Chương trình có thể tổ chức thêm các buổi để học viên:

- Trình bày tiến độ dự án.
- Chia sẻ những lỗi đã gặp.
- Giải thích các giải pháp đã thử nghiệm.
- Nhận phản hồi từ mentor.
- Học hỏi cách tiếp cận của những nhóm khác.
- Luyện tập kỹ năng thuyết trình kỹ thuật.

### 4.5 Mở rộng hoạt động học tập đồng đẳng

Các học viên có nền tảng và trình độ khác nhau có thể được ghép nhóm để hỗ trợ học tập đồng đẳng.

Ví dụ:

- Sinh viên có kinh nghiệm AWS hỗ trợ cấu hình Cloud.
- Sinh viên có kinh nghiệm AI hỗ trợ RAG và tích hợp model.
- Sinh viên có kinh nghiệm lập trình hỗ trợ phát triển ứng dụng.
- Sinh viên có kinh nghiệm DevOps hỗ trợ Docker và CI/CD.

Cách tiếp cận này vừa hỗ trợ quá trình thực hiện dự án, vừa giúp mỗi học viên cải thiện kỹ năng giao tiếp và làm việc nhóm.

## 5. Điều em đánh giá cao nhất

Điều có giá trị nhất đối với em là cơ hội hoàn thành một dự án thực tế từ đầu đến cuối.

Em có thể quan sát cách nhiều thành phần phối hợp với nhau:

```text
Chuẩn bị mã nguồn
→ Xây dựng Docker image
→ Khởi tạo hạ tầng AWS
→ Triển khai ứng dụng
→ Lưu trữ dữ liệu
→ Cấu hình quyền truy cập
→ Sao lưu dữ liệu
→ Giám sát hệ thống
→ Kiểm soát chi phí
→ Viết tài liệu
```

Môi trường học tập cũng khuyến khích học viên đặt câu hỏi và tự nghiên cứu. Điều này giúp em tự tin hơn khi làm việc với những công nghệ chưa quen thuộc.

## 6. Em có giới thiệu chương trình không?

Em sẵn sàng giới thiệu chương trình cho những sinh viên quan tâm đến:

- Điện toán đám mây.
- Trí tuệ nhân tạo.
- DevOps.
- Phát triển phần mềm.
- Triển khai ứng dụng trên AWS.

Chương trình mang lại cơ hội học công nghệ mới, hoàn thành một dự án thực tế và trải nghiệm phương pháp làm việc kỹ thuật có cấu trúc.

Chương trình đặc biệt có giá trị đối với những sinh viên muốn rút ngắn khoảng cách giữa kiến thức học thuật và kỹ năng thực hành trong ngành.

## 7. Mong muốn trong tương lai

Em mong chương trình tiếp tục kết hợp các chủ đề về Cloud và AI.

Trong tương lai, em mong muốn chương trình bổ sung thêm nội dung về:

- Bảo mật Cloud.
- CI/CD.
- Serverless.
- Observability.
- Infrastructure as Code.
- Điều phối container.
- Quản lý secret.
- Đánh giá RAG.
- AI Agent.
- FinOps và tối ưu chi phí.

Nếu có cơ hội, em muốn tiếp tục tham gia các hoạt động chuyên môn, workshop và sự kiện cộng đồng của FCAJ để củng cố kiến thức và chia sẻ những gì đã học với các học viên sau.

## 8. Lời cảm ơn

Em xin cảm ơn ban tổ chức, các mentor, team admin và những học viên khác đã hỗ trợ em trong suốt chương trình.

Những kiến thức và trải nghiệm thu nhận được là nền tảng có giá trị để em tiếp tục phát triển theo định hướng Cloud và AI.

Chương trình đã giúp em cải thiện kỹ năng kỹ thuật và hiểu rõ hơn cách:

- Chủ động học tập.
- Làm việc theo kế hoạch.
- Phối hợp với nhóm.
- Trình bày thông tin kỹ thuật.
- Tiếp nhận và áp dụng phản hồi.
- Tiếp tục cải thiện bản thân.

Em trân trọng cơ hội được tham gia **First Cloud AI Journey – AWS Workforce Bootcamp**. Em hy vọng chương trình sẽ tiếp tục phát triển và mang đến cho nhiều sinh viên hơn cơ hội học tập thực tế cũng như trải nghiệm môi trường làm việc chuyên nghiệp.