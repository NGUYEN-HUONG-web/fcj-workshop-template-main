---
title: "Tự đánh giá"
date: 2026-08-09
weight: 6
chapter: false
pre: "<b>6. </b>"
---


Trong quá trình tham gia chương trình **First Cloud AI Journey – AWS Workforce Bootcamp**, em đã có cơ hội củng cố kiến thức về điện toán đám mây, tìm hiểu quy trình xây dựng ứng dụng Retrieval-Augmented Generation (RAG) và áp dụng kiến thức vào dự án **“Triển khai hệ thống RAG Chat Kotaemon trên AWS”**.

Thông qua quá trình viết worklog, bài blog, tham gia các sự kiện chuyên môn và thực hiện dự án nhóm, em từng bước hình thành phương pháp học tập và làm việc có kế hoạch hơn.

Em không chỉ tập trung vào việc triển khai ứng dụng mà còn chú ý đến các yếu tố quan trọng khi vận hành hệ thống, bao gồm:

- Tính bền vững của dữ liệu.
- Phân quyền truy cập.
- Sao lưu và khôi phục dữ liệu.
- Giám sát tài nguyên.
- Kiểm soát chi phí.
- Bảo vệ thông tin nhạy cảm.
- Trình bày bằng chứng kỹ thuật rõ ràng.

Để nhìn nhận khách quan quá trình tham gia chương trình, em thực hiện tự đánh giá dựa trên các nội dung dưới đây.

## 1. Kiến thức và kỹ năng đạt được

### 1.1 Kiến thức chuyên môn

Sau quá trình học tập và thực hiện dự án, em đã đạt được một số kiến thức chuyên môn sau:

- Hiểu nguyên lý của **standard Hybrid RAG**, bao gồm chia tài liệu thành các đoạn nhỏ, tạo embedding, truy xuất kết hợp và sinh câu trả lời có trích dẫn.
- Phân biệt được vai trò của **Kotaemon application/framework**, **Gemini chat model** và **Gemini embedding model**.
- Hiểu vai trò của Amazon EC2 trong việc cung cấp máy chủ chạy ứng dụng.
- Hiểu cách Amazon EBS lưu trữ dữ liệu lâu dài cho EC2.
- Hiểu cách Amazon S3 được sử dụng để lưu trữ bản sao lưu.
- Hiểu vai trò của IAM Role trong việc cấp quyền cho EC2.
- Hiểu cách Security Group kiểm soát lưu lượng truy cập.
- Biết sử dụng Amazon CloudWatch để theo dõi các chỉ số của EC2.
- Biết sử dụng AWS Budgets để hỗ trợ kiểm soát chi phí.
- Hiểu cách các dịch vụ AWS phối hợp trong một kiến trúc demo.
- Nhận thức được sự khác nhau giữa **demo-ready MVP** và một hệ thống **production-ready**.
- Hiểu tầm quan trọng của HTTPS, quản lý secret, logging, backup và khả năng mở rộng.

### 1.2 Kỹ năng thực hành

Trong quá trình triển khai dự án, em đã thực hành các kỹ năng sau:

- Sử dụng Git để quản lý và đồng bộ mã nguồn.
- Sử dụng Docker để đóng gói và chạy ứng dụng.
- Sử dụng PowerShell trên máy Windows.
- Sử dụng Ubuntu Bash trên máy chủ EC2.
- Build Docker image cho ứng dụng Kotaemon.
- Khởi chạy và quản lý Docker container.
- Ánh xạ cổng để truy cập ứng dụng từ bên ngoài.
- Kiểm tra trạng thái và log của container.
- Sử dụng bind mount trên root EBS volume.
- Tách dữ liệu ứng dụng khỏi vòng đời container.
- Thiết lập sao lưu dữ liệu lên Amazon S3.
- Sử dụng IAM Role thay cho Access Key dài hạn trên EC2.
- Theo dõi các chỉ số EC2 bằng Amazon CloudWatch.
- Thiết lập AWS Budgets để theo dõi chi phí.
- Viết tài liệu Hugo bằng tiếng Việt và tiếng Anh.
- Trình bày quy trình triển khai theo từng bước.
- Kiểm tra lỗi tài liệu bằng lệnh Hugo build.
- Thu thập ảnh và kết quả làm bằng chứng kỹ thuật.

### 1.3 Kỹ năng làm việc

Bên cạnh kiến thức chuyên môn, em đã cải thiện các kỹ năng làm việc sau:

- Chủ động tìm hiểu tài liệu khi gặp vấn đề mới.
- Đối chiếu nhiều nguồn trước khi đưa ra kết luận.
- Kiểm tra vấn đề theo từng lớp thay vì thay đổi nhiều thành phần cùng lúc.
- Phối hợp với các thành viên trong nhóm.
- Trao đổi tiến độ và thống nhất nội dung chung.
- Viết báo cáo theo cấu trúc rõ ràng hơn.
- Trình bày kiến trúc và giải thích quyết định kỹ thuật.
- Chú ý hơn đến thời gian và tiến độ công việc.
- Cẩn thận khi xử lý API key và thông tin AWS.
- Kiểm tra ảnh minh chứng trước khi chia sẻ.
- Tiếp nhận phản hồi và điều chỉnh nội dung.

## 2. Bảng tự đánh giá

| STT | Tiêu chí | Nhận xét | Tốt | Khá | Trung bình |
|:---:|---|---|:---:|:---:|:---:|
| 1 | **Kiến thức AWS và RAG** | Đã hiểu và áp dụng được các thành phần chính; cần tiếp tục học về kiến trúc có tính sẵn sàng cao và bảo mật chuyên sâu. | ☐ | ✅ | ☐ |
| 2 | **Khả năng học hỏi** | Có khả năng tự đọc tài liệu, thử nghiệm và điều chỉnh khi tiếp cận công nghệ mới. | ✅ | ☐ | ☐ |
| 3 | **Tinh thần trách nhiệm** | Hoàn thành các phần việc được giao và chú ý đến tính chính xác của nội dung báo cáo. | ✅ | ☐ | ☐ |
| 4 | **Tính chủ động** | Chủ động tìm nguyên nhân và đề xuất hướng xử lý; đôi lúc cần thêm thời gian để lựa chọn giải pháp tối ưu. | ✅ | ☐ | ☐ |
| 5 | **Làm việc nhóm** | Phối hợp, chia sẻ thông tin và hỗ trợ hoàn thiện nội dung chung của nhóm. | ✅ | ☐ | ☐ |
| 6 | **Giao tiếp và trình bày** | Đã tiến bộ trong việc diễn giải nội dung kỹ thuật; cần trình bày ngắn gọn và tự tin hơn khi thuyết trình. | ☐ | ✅ | ☐ |
| 7 | **Giải quyết vấn đề** | Biết kiểm tra theo từng lớp và dựa trên bằng chứng; cần rèn luyện thêm với các sự cố phức tạp. | ✅ | ☐ | ☐ |
| 8 | **Quản lý thời gian** | Có theo dõi tiến độ bằng worklog; cần phân bổ thời gian kiểm thử và hoàn thiện bằng chứng sớm hơn. | ☐ | ✅ | ☐ |
| 9 | **Mức độ hoàn thành tổng thể** | Đã hoàn thành một demo-ready MVP và tài liệu workshop, nhưng vẫn còn một số hạng mục cần tiếp tục xác nhận. | ✅ | ☐ | ☐ |

## 3. Điểm mạnh

### 3.1 Khả năng học hỏi

Em có khả năng chủ động đọc tài liệu, tìm hiểu công nghệ mới và áp dụng kiến thức vào bài toán thực tế.

Khi gặp nội dung chưa hiểu, em cố gắng:

- Tìm tài liệu chính thức.
- Đối chiếu nhiều nguồn.
- Thử nghiệm từng bước.
- Ghi nhận kết quả.
- Điều chỉnh khi giải pháp chưa phù hợp.

### 3.2 Tinh thần trách nhiệm

Em cố gắng hoàn thành các phần việc được giao và chịu trách nhiệm với kết quả công việc.

Trong quá trình viết tài liệu, em chú ý kiểm tra:

- Tính chính xác của nội dung.
- Cấu trúc Markdown.
- Đường dẫn hình ảnh.
- Lỗi Hugo build.
- Thông tin nhạy cảm trong ảnh.
- Sự nhất quán giữa bản tiếng Việt và tiếng Anh.

### 3.3 Tính chủ động

Khi gặp lỗi triển khai, em chủ động tìm nguyên nhân thay vì chỉ chờ hướng dẫn.

Em từng bước kiểm tra:

- Trạng thái máy chủ EC2.
- Kết nối mạng.
- Security Group.
- Docker container.
- Cổng dịch vụ.
- Log ứng dụng.
- Quyền IAM.
- Trạng thái dữ liệu.
- Khả năng truy cập Amazon S3.

### 3.4 Khả năng làm việc nhóm

Em có thể phối hợp với các thành viên, chia sẻ tiến độ và hỗ trợ hoàn thiện nội dung chung.

Em cố gắng lắng nghe ý kiến, trao đổi khi có vấn đề và điều chỉnh phần việc để phù hợp với mục tiêu chung của nhóm.

## 4. Điểm cần cải thiện

### 4.1 Kiến thức Cloud và DevOps

Em cần tiếp tục nâng cao kiến thức về:

- HTTPS và chứng chỉ TLS.
- Quản lý domain.
- Quản lý secret.
- Centralized logging.
- Tự động hóa triển khai.
- Tự động hóa backup.
- Giám sát và cảnh báo.
- High Availability.
- Auto Scaling.
- Load Balancer.
- Kiến trúc có khả năng mở rộng.

### 4.2 Đánh giá chất lượng RAG

Quá trình đánh giá hiện tại vẫn chủ yếu dựa trên một số câu hỏi thủ công.

Em cần xây dựng phương pháp đánh giá định lượng gồm:

- Bộ câu hỏi kiểm thử.
- Câu trả lời mong đợi.
- Độ chính xác truy xuất.
- Mức độ liên quan.
- Độ chính xác của trích dẫn.
- Mức độ bám sát tài liệu.
- Tỷ lệ câu trả lời không có căn cứ.
- Thời gian phản hồi.

### 4.3 Kiểm thử dữ liệu

Em cần hoàn thiện kiểm thử persistence và restore với bằng chứng rõ ràng.

Quy trình kiểm thử cần thể hiện:

1. Trạng thái dữ liệu trước khi dừng container.
2. Vị trí dữ liệu trên EBS.
3. Trạng thái sau khi khởi động lại container.
4. Kết quả sao lưu lên Amazon S3.
5. Kết quả khôi phục từ bản sao lưu.
6. So sánh dữ liệu trước và sau khi khôi phục.

### 4.4 Quản lý thời gian

Em cần cải thiện khả năng ước lượng thời gian thực hiện công việc.

Trong các giai đoạn tiếp theo, em sẽ phân bổ thời gian riêng cho:

- Nghiên cứu.
- Triển khai.
- Kiểm thử.
- Xử lý lỗi.
- Thu thập bằng chứng.
- Viết tài liệu.
- Rà soát nội dung.
- Chuẩn bị thuyết trình.

### 4.5 Giao tiếp và trình bày

Em cần rèn luyện cách trình bày ngắn gọn, rõ ràng và tập trung vào nội dung chính.

Khi gặp trở ngại, em cần chủ động:

- Mô tả vấn đề sớm.
- Cung cấp log hoặc bằng chứng.
- Trình bày những bước đã kiểm tra.
- Nêu rõ kết quả mong đợi.
- Đề xuất hướng xử lý.
- Yêu cầu hỗ trợ khi cần thiết.

### 4.6 Bảo mật thông tin

Em cần tiếp tục hình thành thói quen bảo mật khi làm việc với hệ thống Cloud.

Trước khi chia sẻ nội dung, cần kiểm tra và che:

- AWS Account ID.
- API key.
- Access Key ID.
- Secret Access Key.
- Session token.
- IP hoặc domain nội bộ.
- Thông tin đăng nhập.
- Dữ liệu cá nhân.
- Thông tin nhạy cảm trong log.

Nếu một API key bị hiển thị công khai, cần vô hiệu hóa và tạo key mới thay vì tiếp tục sử dụng.

## 5. Kế hoạch cải thiện

Trong thời gian tới, em dự kiến:

1. Nghiên cứu sâu hơn về bảo mật trên AWS.
2. Tìm hiểu AWS Secrets Manager và Systems Manager Parameter Store.
3. Cấu hình HTTPS cho ứng dụng.
4. Hoàn thiện quy trình backup và restore.
5. Xây dựng bộ test case cho hệ thống RAG.
6. Đánh giá chất lượng retrieval và generation.
7. Cải thiện hệ thống logging và monitoring.
8. Tìm hiểu Infrastructure as Code.
9. Thực hành tự động hóa triển khai.
10. Cải thiện kỹ năng thuyết trình.
11. Chủ động phản hồi sớm khi gặp khó khăn.
12. Tiếp tục ghi lại tiến độ bằng worklog.

## 6. Kết luận tự đánh giá

Em đánh giá bản thân đã có sự tiến bộ rõ rệt về kiến thức AWS, kỹ năng triển khai và tư duy vận hành hệ thống.

Kết quả quan trọng nhất không chỉ là hoàn thành một ứng dụng có thể trình diễn mà còn là hiểu được những giới hạn của kiến trúc hiện tại và biết cách đề xuất lộ trình cải tiến phù hợp.

Thông qua dự án, em hiểu rằng một hệ thống RAG hoạt động được chưa đồng nghĩa với việc hệ thống đã sẵn sàng cho production. Một hệ thống production-ready còn cần bảo mật, giám sát, sao lưu, kiểm thử, khả năng mở rộng và quy trình vận hành rõ ràng.

Trong thời gian tới, em sẽ tiếp tục bổ sung kiến thức về:

- Bảo mật Cloud.
- Tự động hóa.
- Giám sát hệ thống.
- Đánh giá chất lượng RAG.
- Kiểm thử phần mềm.
- Kiến trúc có khả năng mở rộng.
- Giao tiếp và làm việc nhóm.

Chương trình **First Cloud AI Journey – AWS Workforce Bootcamp** đã giúp em kết nối kiến thức lý thuyết với quá trình triển khai thực tế. Đây là nền tảng quan trọng để em tiếp tục phát triển kỹ năng Cloud, AI và DevOps trong tương lai.

> Em sẽ tiếp tục duy trì tinh thần học hỏi, chủ động cải thiện những điểm còn hạn chế và hướng đến việc xây dựng các hệ thống AI an toàn, ổn định và có giá trị thực tiễn.