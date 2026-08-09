---
title: "Sự kiện 2"
date: 2026-08-08
weight: 2
chapter: false
pre: "<b>2. </b>"
---

# Báo cáo tham dự “Agent Forge – Deepdive Day 2”

## 1. Thông tin sự kiện

| Hạng mục | Thông tin |
|---|---|
| **Tên sự kiện** | Agent Forge – Deepdive Day 2 |
| **Chủ đề chính** | Advanced Amazon Bedrock AgentCore |
| **Ngày tổ chức** | Ngày 8 tháng 8 năm 2026 |
| **Thời gian** | 09:00–12:00 |
| **Địa điểm** | Bitexco Financial Tower, số 2 đường Hải Triều, TP. Hồ Chí Minh |
| **Người tổ chức** | Huỳnh Hoàng Long |
| **Vai trò** | Người tham dự |
| **Trạng thái** | Đã tham dự |
| **Hình thức** | Trình bày kỹ thuật kết hợp thực hành |
| **Trang sự kiện** | [Xem trên Luma](https://luma.com/8qewnfuu) |

## 2. Tổng quan sự kiện

**Agent Forge – Deepdive Day 2** là buổi thứ hai trong chuỗi workshop Agent Forge kéo dài ba ngày.

Trong khi Day 1 giới thiệu nền tảng và cách thiết lập AI Agent, Day 2 tập trung vào chủ đề:

> **Personalization, Evaluation & Optimization**

Nội dung chính của sự kiện là **Advanced Amazon Bedrock AgentCore**, bao gồm cách xây dựng bộ nhớ, theo dõi quá trình hoạt động, đánh giá chất lượng và tối ưu hóa AI Agent trên AWS.

Sự kiện kết hợp giữa phần trình bày kỹ thuật, thực hành và trao đổi trực tiếp với người hướng dẫn.

## 3. Lý do tham dự

Nội dung sự kiện có liên quan trực tiếp đến dự án **AI Learning Assistant Platform**.

Nền tảng này cho phép người dùng:

- Tải tài liệu học tập.
- Xử lý nội dung PDF, DOCX và TXT.
- Chia tài liệu thành các đoạn dữ liệu.
- Tạo vector embedding.
- Tìm kiếm thông tin trong Dataset.
- Đặt câu hỏi dựa trên tài liệu.
- Tạo quiz và flashcard.
- Nhận câu trả lời từ mô hình AI.

Dự án cần quản lý dữ liệu của từng người dùng, truy xuất đúng tài liệu và hạn chế câu trả lời không có căn cứ.

Các nội dung Memory, Evaluations và Observability có thể hỗ trợ trực tiếp cho những yêu cầu này.

## 4. Nội dung chương trình

### 4.1 Amazon Bedrock AgentCore nâng cao

Phiên trình bày chính giới thiệu:

- **Memory:** Lưu thông tin để cá nhân hóa Agent.
- **Evaluations:** Đánh giá chất lượng và hiệu quả hoạt động.
- **Observability:** Theo dõi quá trình xử lý yêu cầu.
- **Registry:** Quản lý Agent và công cụ.
- **Harness:** Hỗ trợ phát triển và kiểm thử.
- **Tools:** Kết nối Agent với dịch vụ bên ngoài.
- **Optimization:** Tối ưu độ chính xác, tốc độ và chi phí.
- **Policy:** Kiểm soát quyền truy cập và hành vi.

### 4.2 Phiên thực hành

Các hoạt động thực hành tập trung vào:

1. Thêm Memory cho AI Agent.
2. Cá nhân hóa hành vi theo người dùng.
3. Khám phá Agent Observability.
4. Theo dõi quá trình thực thi.
5. Sử dụng AgentCore Evaluations.
6. Tìm hiểu AgentCore Harness.
7. Kiểm tra vai trò của Harness trong phát triển Agent.

### 4.3 Lịch trình

| Thời gian | Hoạt động | Kết quả |
|---|---|---|
| **08:30–09:00** | Đăng ký và chuẩn bị | Sẵn sàng môi trường AWS |
| **09:00–10:00** | Trình bày AgentCore nâng cao | Hiểu các thành phần chính |
| **10:00–11:00** | Thực hành | Trải nghiệm Memory và Evaluations |
| **11:00–12:00** | Thảo luận và giao lưu | Giải đáp vấn đề kỹ thuật |

## 5. Kiến thức thu nhận được

### 5.1 Memory

Memory giúp Agent lưu lại thông tin cần thiết từ các lần tương tác trước.

Đối với nền tảng học tập, Memory có thể lưu:

- Ngôn ngữ người dùng ưu tiên.
- Mục tiêu học tập.
- Môn học đang theo dõi.
- Tài liệu thường xuyên sử dụng.
- Kết quả làm quiz.
- Chủ đề cần cải thiện.
- Phong cách trả lời mong muốn.
- Lịch sử câu hỏi.

Memory cần được phân tách theo từng người dùng và không nên lưu thông tin nhạy cảm khi không cần thiết.

### 5.2 Evaluations

Evaluations giúp đo lường chất lượng hoạt động của Agent dựa trên các tiêu chí cụ thể:

- Độ chính xác của câu trả lời.
- Mức độ liên quan.
- Khả năng bám sát tài liệu.
- Độ chính xác của trích dẫn.
- Chất lượng truy xuất dữ liệu.
- Thời gian phản hồi.
- Tỷ lệ gọi công cụ thành công.
- Khả năng từ chối khi thiếu thông tin.

Evaluations giúp nhóm phát triển xác định những trường hợp Agent trả lời chưa đạt yêu cầu và đưa ra phương án cải thiện phù hợp.

### 5.3 Observability

Observability giúp theo dõi toàn bộ quá trình Agent xử lý yêu cầu.

Các dữ liệu cần theo dõi gồm:

- Câu hỏi của người dùng.
- Model được sử dụng.
- Dataset được lựa chọn.
- Các đoạn tài liệu được truy xuất.
- Prompt gửi đến mô hình.
- Công cụ được gọi.
- Token sử dụng.
- Thời gian xử lý.
- Lỗi và số lần thử lại.
- Câu trả lời cuối cùng.

Thông tin này giúp xác định nguyên nhân khi Agent chọn sai Dataset, truy xuất thiếu dữ liệu hoặc trả lời không đúng tài liệu.

### 5.4 Registry và Harness

Registry hỗ trợ quản lý các Agent, công cụ và thành phần liên quan trong hệ thống.

Registry có thể được sử dụng để quản lý:

- Danh sách Agent.
- Danh sách công cụ.
- Phiên bản công cụ.
- Mô tả chức năng.
- Schema đầu vào và đầu ra.
- Trạng thái hoạt động.
- Quyền truy cập.

Harness hỗ trợ phát triển và kiểm thử Agent theo một quy trình có cấu trúc.

Harness có thể giúp:

- Cung cấp dữ liệu kiểm thử.
- Theo dõi từng bước xử lý.
- So sánh kết quả thực tế với kết quả mong đợi.
- Tái hiện lỗi.
- Kiểm tra sau khi thay đổi prompt.
- Kiểm tra sau khi thay đổi model.
- Tự động hóa các test case.

### 5.5 Tools và Policy

Tools cho phép Agent thực hiện các tác vụ bên ngoài mô hình ngôn ngữ.

Các công cụ có thể áp dụng cho dự án gồm:

- Tìm kiếm Dataset.
- Tóm tắt tài liệu.
- Tạo quiz.
- Tạo flashcard.
- Truy xuất file từ Amazon S3.
- Gọi AWS Lambda.
- Tra cứu DynamoDB.
- Gọi API bên ngoài.
- Gửi thông báo cho người dùng.

Policy giúp giới hạn quyền truy cập và hành động của Agent.

Mỗi công cụ chỉ nên được cấp quyền IAM tối thiểu cần thiết. Không nên sử dụng quyền Administrator cho các tác vụ thông thường.

Các chính sách cần xác định rõ:

- Agent được phép gọi công cụ nào.
- Người dùng được truy cập tài liệu nào.
- Công cụ được truy cập tài nguyên AWS nào.
- Hành động nào cần người dùng xác nhận.
- Cách ngăn chặn yêu cầu không an toàn.
- Cách ghi log phục vụ kiểm tra.

### 5.6 Optimization

Optimization tập trung cải thiện hiệu quả hoạt động của Agent.

Các nội dung cần tối ưu gồm:

- Độ chính xác của câu trả lời.
- Chất lượng truy xuất dữ liệu.
- Cấu trúc prompt.
- Khả năng lựa chọn công cụ.
- Kích thước context.
- Thời gian phản hồi.
- Lượng token sử dụng.
- Chi phí vận hành.
- Khả năng xử lý lỗi.
- Trải nghiệm người dùng.

## 6. Ứng dụng vào dự án

Kiến thức từ sự kiện có thể được áp dụng vào workflow của **AI Learning Assistant Platform**:

```text
Câu hỏi người dùng
→ Chọn kho kiến thức
→ Tìm kiếm Dataset
→ Truy xuất đoạn tài liệu
→ Tạo prompt
→ Gọi mô hình AI
→ Đánh giá kết quả
→ Trả lời người dùng
### Các hướng áp dụng cụ thể

- Cá nhân hóa trải nghiệm học tập.
- Ghi nhớ mục tiêu của người dùng.
- Theo dõi tiến độ học tập.
- Lựa chọn đúng Dataset.
- Theo dõi nội dung được truy xuất.
- Đánh giá chất lượng câu trả lời.
- Phát hiện lỗi trong workflow.
- Giảm hiện tượng AI hallucination.
- Tối ưu token và thời gian phản hồi.
- Kiểm soát quyền truy cập tài liệu.
- Theo dõi hoạt động của công cụ.
- Đánh giá hiệu quả của mô hình AI.

### Vai trò của các thành phần AgentCore

- **Memory:** Giúp hệ thống ghi nhớ ngôn ngữ, mục tiêu học tập, môn học và những chủ đề người dùng cần cải thiện.
- **Evaluations:** Kiểm tra độ chính xác, mức độ liên quan và khả năng bám sát tài liệu của câu trả lời.
- **Observability:** Theo dõi Dataset ID, các đoạn tài liệu được tìm thấy, prompt, lượng token, thời gian phản hồi và lỗi phát sinh.
- **Tools:** Hỗ trợ tìm kiếm tài liệu, tạo quiz, tạo flashcard, gọi AWS Lambda và truy xuất dữ liệu từ các dịch vụ AWS.
- **Policy:** Bảo đảm Agent và công cụ chỉ được truy cập những dữ liệu và dịch vụ cần thiết.

## 7. Kết luận

Việc tham dự **Agent Forge – Deepdive Day 2** đã giúp tôi hiểu rõ hơn về quá trình xây dựng, vận hành, theo dõi và đánh giá một AI Agent trên nền tảng AWS.

Thông qua các nội dung về **Memory, Evaluations, Observability, Registry, Harness, Tools, Optimization và Policy**, tôi nhận thấy chất lượng của một AI Agent không chỉ phụ thuộc vào mô hình ngôn ngữ lớn. Một hệ thống hoàn chỉnh còn cần có dữ liệu phù hợp, công cụ hỗ trợ, cơ chế theo dõi, phương pháp đánh giá và chính sách bảo mật rõ ràng.

Trong đó:

- **Memory** giúp Agent cá nhân hóa trải nghiệm cho từng người dùng.
- **Evaluations** hỗ trợ đo lường độ chính xác và mức độ phù hợp của câu trả lời.
- **Observability** giúp theo dõi toàn bộ quá trình xử lý để phát hiện và khắc phục lỗi.

Những kiến thức này có thể được áp dụng trực tiếp vào **AI Learning Assistant Platform**, đặc biệt trong các hoạt động:

- Cá nhân hóa trải nghiệm học tập.
- Ghi nhớ mục tiêu và tiến độ của người dùng.
- Tìm kiếm đúng tài liệu trong Dataset.
- Đánh giá mức độ chính xác của câu trả lời.
- Kiểm tra câu trả lời có bám sát tài liệu hay không.
- Theo dõi các bước trong workflow.
- Phát hiện lỗi khi gọi model hoặc công cụ.
- Giảm hiện tượng AI hallucination.
- Kiểm soát quyền truy cập vào dữ liệu và dịch vụ AWS.
- Tối ưu thời gian phản hồi, token và chi phí vận hành.

Bên cạnh kiến thức kỹ thuật, sự kiện còn tạo cơ hội trao đổi với người hướng dẫn và những người cùng quan tâm đến AI Agent. Điều này giúp tôi có thêm góc nhìn thực tế về những khó khăn có thể gặp khi triển khai Agent trong môi trường thật.

Nhìn chung, **Agent Forge – Deepdive Day 2** là một sự kiện hữu ích, có nội dung chuyên sâu và phù hợp với định hướng phát triển dự án. Những kiến thức thu nhận được sẽ là nền tảng để tôi tiếp tục nghiên cứu Amazon Bedrock AgentCore, hoàn thiện **AI Learning Assistant Platform** và phát triển các ứng dụng AI Agent an toàn, đáng tin cậy hơn trong tương lai.