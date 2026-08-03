---
title: "Nhật ký công việc Tuần 1"
date: 2026-06-22
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu tuần 1

* Làm quen với môi trường thực tập, quy trình làm việc và các thành viên của First Cloud AI Journey.
* Xây dựng kiến thức nền tảng về điện toán đám mây và Amazon Web Services.
* Hiểu cấu trúc hạ tầng toàn cầu của AWS.
* Làm quen với AWS Management Console và các nhóm dịch vụ AWS chính.
* Tìm hiểu IAM và thực hành bảo mật tài khoản AWS.
* Thiết lập AWS Budgets để giám sát và kiểm soát chi phí.

### Công việc thực hiện trong tuần

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Tài liệu tham khảo |
| --- | --- | --- | --- | --- |
| **2** | - Tham gia buổi định hướng chương trình thực tập.<br>- Giới thiệu bản thân và làm quen với các thành viên First Cloud AI Journey.<br>- Tìm hiểu nội quy, thời gian làm việc, phương thức trao đổi và cách báo cáo tiến độ.<br>- Làm quen với cấu trúc báo cáo Worklog, Proposal, Blog và Workshop. | 22/06/2026 | 22/06/2026 | <https://cloudjourney.awsstudygroup.com/> |
| **3** | - Tìm hiểu khái niệm Cloud Computing và các mô hình IaaS, PaaS, SaaS.<br>- Nghiên cứu AWS Global Infrastructure gồm Region, Availability Zone và Edge Location.<br>- Tìm hiểu các nhóm dịch vụ chính: Compute, Storage, Networking, Database, Security và Management.<br>- Thực hành vẽ sơ đồ AWS cơ bản bằng Draw.io và AWS Architecture Icons. | 23/06/2026 | 23/06/2026 | <https://aws.amazon.com/about-aws/global-infrastructure/> |
| **4** | - Tạo và cấu hình tài khoản AWS.<br>- Kiểm tra thông tin thanh toán và các quyền truy cập tài khoản.<br>- Kích hoạt Multi-Factor Authentication cho Root User.<br>- Tìm hiểu AWS Shared Responsibility Model và các nguyên tắc bảo mật tài khoản Cloud. | 24/06/2026 | 24/06/2026 | <https://000001.awsstudygroup.com/> |
| **5** | - Tìm hiểu AWS Identity and Access Management.<br>- Phân biệt IAM User, User Group, Policy và Role.<br>- Tạo IAM Admin Group và IAM Admin User.<br>- Gán Policy phù hợp và kiểm tra quyền đăng nhập.<br>- Tìm hiểu nguyên tắc Least Privilege và tránh sử dụng Root User cho công việc hằng ngày. | 25/06/2026 | 25/06/2026 | <https://000002.awsstudygroup.com/> |
| **6** | - Tìm hiểu AWS Billing and Cost Management.<br>- Kiểm tra Free Tier Usage và chi phí theo từng dịch vụ.<br>- Tạo Cost Budget và cấu hình cảnh báo qua email.<br>- Tìm hiểu Cost Explorer và AWS Support.<br>- Tổng hợp kiến thức và hoàn thiện báo cáo tuần 1. | 26/06/2026 | 26/06/2026 | <https://docs.aws.amazon.com/cost-management/> |

### Kết quả đạt được

#### Làm quen với môi trường thực tập

* Hiểu nội quy, quy trình làm việc và phương thức báo cáo trong chương trình thực tập.
* Làm quen với các thành viên và xác định được lộ trình học tập trong tám tuần.
* Hiểu cấu trúc cơ bản của website báo cáo thực tập FCAJ.

#### Kiến thức nền tảng về AWS

* Hiểu những đặc điểm cơ bản của điện toán đám mây.
* Phân biệt được IaaS, PaaS và SaaS.
* Hiểu vai trò của Region, Availability Zone và Edge Location.
* Nhận biết được các nhóm dịch vụ AWS quan trọng.
* Biết sử dụng Draw.io và AWS Architecture Icons để trình bày kiến trúc.

#### Bảo mật và quản lý quyền truy cập

* Tạo và bảo mật thành công tài khoản AWS bằng MFA.
* Phân biệt được IAM User, Group, Policy và Role.
* Tạo IAM Admin User để sử dụng thay cho Root User.
* Hiểu nguyên tắc Least Privilege trong quá trình cấp quyền.

#### Quản lý chi phí

* Tạo AWS Budget và cấu hình cảnh báo chi phí qua email.
* Biết cách kiểm tra chi phí theo dịch vụ và khu vực.
* Hiểu tầm quan trọng của việc xóa tài nguyên sau khi hoàn thành bài thực hành.

### Khó khăn và cách khắc phục

| Khó khăn | Cách khắc phục |
| --- | --- |
| Chưa phân biệt rõ IAM User và IAM Role | Tìm hiểu lại tài liệu và xác định: User đại diện cho người dùng, còn Role cung cấp quyền tạm thời cho dịch vụ hoặc ứng dụng. |
| Gặp khó khăn khi lựa chọn AWS Region | Lựa chọn Singapore `ap-southeast-1` vì gần Việt Nam và có độ trễ thấp. |
| Chưa quen với giao diện AWS Billing | Kiểm tra từng mục Bills, Cost Explorer, Budgets và Free Tier Usage theo tài liệu hướng dẫn. |

---

### Đánh giá tuần

Tuần đầu tiên giúp tôi có cái nhìn tổng quan về AWS Cloud và môi trường thực tập tại First Cloud AI Journey. Tôi đã hiểu cách AWS tổ chức hạ tầng toàn cầu, cách quản lý danh tính bằng IAM và cách bảo vệ tài khoản bằng MFA.

Bài học quan trọng nhất trong tuần là bảo mật và kiểm soát chi phí phải được thực hiện ngay từ khi bắt đầu sử dụng AWS. Việc tạo Budget và hạn chế sử dụng Root User giúp tôi hình thành thói quen quản trị Cloud an toàn hơn.