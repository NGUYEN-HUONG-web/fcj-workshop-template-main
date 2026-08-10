---
title: "5.9. Tự động hóa và tối ưu chi phí"
date: 2026-08-09
weight: 9
chapter: false
pre: " <b> 5.9. </b> "
---

## Bật/tắt EC2 theo lịch

Tạo Lambda riêng cho Start/Stop EC2 hoặc một function nhận tham số. Execution role chỉ được cấp quyền EC2 cần thiết đối với instance mục tiêu.

EventBridge Scheduler kích hoạt function theo lịch:

```text
EventBridge schedule → Lambda → EC2 StartInstances/StopInstances
```

Chọn đúng múi giờ, cấu hình retry và chạy thử từng function trước khi bật lịch. Việc stop EC2 không loại bỏ chi phí EBS, Elastic IP, S3 hoặc các tài nguyên vẫn tồn tại.

![Lambda Start Stop EC2 và kết quả kiểm thử](/images/5-Workshop/5.9-Automation-Cost/lambda-start-stop.png)

> **⚠️ Ảnh chưa có:** EventBridge schedule, múi giờ và lần chạy tiếp theo.  
> File: `/images/5-Workshop/5.9-Automation-Cost/eventbridge-schedule.png`
<!-- ![EventBridge schedule](/images/5-Workshop/5.9-Automation-Cost/eventbridge-schedule.png) -->

## AWS Budgets

Tạo monthly cost budget và các ngưỡng cảnh báo cho chi phí thực tế, chi phí dự báo. Gửi cảnh báo đến địa chỉ được theo dõi và kiểm tra phân bổ chi phí định kỳ.

> **⚠️ Ảnh chưa có:** AWS Budget, ngưỡng cảnh báo và trạng thái hiện tại; che dữ liệu thanh toán.  
> File: `/images/5-Workshop/5.9-Automation-Cost/aws-budget.png`
<!-- ![AWS Budget của dự án](/images/5-Workshop/5.9-Automation-Cost/aws-budget.png) -->

## Cơ cấu chi phí

Chi phí thực tế phụ thuộc Region, kích thước instance, dung lượng lưu trữ, lưu lượng, thời gian giữ dữ liệu và thời gian sử dụng. Cần ghi nhận giá hiện hành từ AWS Pricing Calculator hoặc Billing Console trước khi nộp báo cáo.

| Nhóm chi phí | Yếu tố tính phí chính | Cách kiểm soát |
|---|---|---|
| Amazon EC2 | Instance type và số giờ chạy | Right-size và đặt lịch Start/Stop |
| Amazon EBS | Dung lượng volume và snapshot | Xóa volume, snapshot không sử dụng |
| Amazon ECR | Dung lượng image và data transfer | Lifecycle policy cho image cũ |
| Amazon S3 | Lưu trữ, request và truyền dữ liệu | Lifecycle rule và chính sách lưu giữ |
| CloudWatch | Custom metric, log, dashboard, alarm | Chỉ thu thập dữ liệu cần thiết, giới hạn retention |
| Data transfer | Lưu lượng Internet đầu ra | Theo dõi mức dùng, tránh tải xuống không cần thiết |

Ước tính theo tháng chỉ là giá trị lập kế hoạch, không phải hóa đơn cố định. Trong quá trình vận hành cần so sánh với Cost Explorer và AWS Budgets.

> **⚠️ Ảnh chưa có:** Cost Explorer theo dịch vụ, đã che Account ID và thông tin thanh toán.  
> File: `/images/5-Workshop/5.9-Automation-Cost/cost-explorer.png`
<!-- ![Chi phí trên Cost Explorer](/images/5-Workshop/5.9-Automation-Cost/cost-explorer.png) -->

## Biện pháp tối ưu bổ sung

- Chọn kích thước EC2 dựa trên CPU và bộ nhớ đo được.
- Tắt môi trường không production khi không sử dụng.
- Xóa EBS snapshot, Elastic IP và ECR image không còn cần thiết.
- Áp dụng lifecycle policy cho S3 và ECR.
- Giới hạn thời gian lưu CloudWatch Logs.
- Kiểm tra Cost Explorer và Budget trước khi tăng tài nguyên.

## Kiểm tra kết quả

Xác nhận kết quả chạy Lambda, thời gian kích hoạt tiếp theo của EventBridge, thay đổi trạng thái EC2, ngưỡng Budget và thông báo được gửi mà không lộ Account ID hoặc dữ liệu thanh toán.

## Ảnh minh chứng cần bổ sung

1. Lambda function dùng để Start và Stop EC2.
2. Kết quả test Lambda hoặc CloudWatch execution log thành công.
3. EventBridge schedule, múi giờ và thời gian kích hoạt tiếp theo.
4. AWS Budget, các ngưỡng cảnh báo và trạng thái hiện tại.
5. Tổng quan Cost Explorer đã che Account ID và dữ liệu thanh toán.

<!-- Thư mục đề xuất: /static/images/5-Workshop/5.9-Automation-Cost/ -->
