---
title: "Workshop"
date: 2026-07-17
weight: 5
chapter: false
pre: " <b> 5. </b> "
---

# Triển khai AI Learning Assistant Platform trên Amazon Web Services

#### Tổng quan

**AI Learning Assistant Platform** là một nền tảng học tập thông minh được xây dựng dựa trên kiến trúc **Retrieval-Augmented Generation (RAG)**, cho phép người dùng tải tài liệu học tập, xây dựng Knowledge Base và tương tác với mô hình AI để nhận câu trả lời dựa trên nội dung tài liệu.

Trong Workshop này, chúng ta sẽ từng bước triển khai hệ thống trên **Amazon Web Services (AWS)** bằng **Docker Compose** chạy trên **Amazon EC2**. Đồng thời, Workshop cũng hướng dẫn cấu hình **GitHub Actions** và **Amazon ECR** để xây dựng quy trình **CI/CD**, sử dụng **Amazon CloudWatch** để giám sát hệ thống và **Amazon S3** để sao lưu dữ liệu.

Sau khi hoàn thành Workshop, bạn sẽ có thể triển khai, vận hành và quản lý một ứng dụng Generative AI trên AWS theo mô hình **Production Lite**, đồng thời áp dụng các dịch vụ AWS để đảm bảo khả năng mở rộng, giám sát và tối ưu chi phí.

#### Nội dung

1. [Tổng quan hệ thống](5.1-Workshop-overview/)
2. [Chuẩn bị môi trường](5.2-Prerequisite/)
3. [Triển khai Amazon EC2](5.3-Deploy-EC2/)
4. [Cài đặt Docker và Docker Compose](5.4-Docker/)
5. [Triển khai AI Learning Assistant Platform](5.5-Deploy-Application/)
6. [Thiết lập CI/CD với GitHub Actions và Amazon ECR](5.6-CICD/)
7. [Giám sát hệ thống bằng Amazon CloudWatch](5.7-Monitoring/)
8. [Kiểm thử hệ thống](5.8-Testing/)
9. [Dọn dẹp tài nguyên AWS](5.9-Cleanup/)