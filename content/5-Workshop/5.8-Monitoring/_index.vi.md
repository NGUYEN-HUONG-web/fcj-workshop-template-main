---
title: "5.8. Giám sát với CloudWatch và SNS"
date: 2026-08-09
weight: 8
chapter: false
pre: " <b> 5.8. </b> "
---

## Mục tiêu giám sát

Hệ thống giám sát cần phát hiện áp lực hạ tầng và lỗi ứng dụng trước khi trở thành gián đoạn kéo dài. Workshop kết hợp metric mặc định của EC2 và metric từ CloudWatch Agent.

## CloudWatch Agent

Gán IAM role cho phép gửi metric và log. Chỉ thu thập dữ liệu cần thiết như mức sử dụng bộ nhớ, ổ đĩa, swap và các log được chọn. Khởi động agent và xác nhận dữ liệu xuất hiện tại đúng Region.

![CloudWatch Agent đang hoạt động trên EC2](/images/5-Workshop/5.8-Monitoring/cloudwatch-agent-status.png)

## Dashboard

Tạo dashboard cho các metric thực sự được thu thập:

- CPU và instance status của EC2.
- Bộ nhớ và ổ đĩa từ CloudWatch Agent.
- Lưu lượng mạng.
- Log ứng dụng hoặc Nginx nếu đã cấu hình thu thập log.

![CloudWatch Dashboard của hệ thống](/images/5-Workshop/5.8-Monitoring/cloudwatch-dashboard.png)

## Luồng cảnh báo

Tạo Alarm với ngưỡng và evaluation period phù hợp. Gửi thay đổi trạng thái đến SNS topic, xác nhận email subscription và kiểm thử luồng thông báo an toàn.

![CloudWatch Alarm và trạng thái hiện tại](/images/5-Workshop/5.8-Monitoring/cloudwatch-alarm.png)

![SNS subscription ở trạng thái Confirmed](/images/5-Workshop/5.8-Monitoring/sns-subscription.png)

```text
Metric → CloudWatch Alarm → SNS Topic → Subscriber đã xác nhận
```

## Kiểm tra vận hành

Xác nhận Dashboard có dữ liệu mới, trạng thái Alarm giải thích được, hành vi khi thiếu dữ liệu đã cấu hình và địa chỉ email nhạy cảm được che trong minh chứng công khai.


