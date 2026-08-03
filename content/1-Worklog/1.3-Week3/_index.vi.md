---
title: "Worklog Tuần 3"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu tuần 3:

* Nghiên cứu dịch vụ lưu trữ container **Amazon ECR (Elastic Container Registry)**.
* Đóng gói ứng dụng Backend (FastAPI) thành Docker Container Image chuẩn tối ưu cho AWS Lambda.
* Khởi tạo AWS Lambda Function từ Docker Image trên ECR và kết nối với API Gateway.

### Các công việc đã thực hiện:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu tổng quan dịch vụ kho lưu trữ container **Amazon ECR (Elastic Container Registry)** <br> - **Thực hành:** Khởi tạo Private ECR Repository trên AWS Console <br> - Học lệnh xác thực Docker CLI với Amazon ECR thông qua AWS CLI: `aws ecr get-login-password --region <region> | 06/07/2026 | 06/07/2026 | [Tài liệu quản lý kho ảnh Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/what-is-ecr.html) |
| 3 | - Thiết kế và viết `Dockerfile` chuẩn tối ưu cho ứng dụng FastAPI Backend <br> - Sử dụng hình ảnh cơ sở (`public.ecr.aws/lambda/python:3.12`), thêm các thư viện phụ thuộc vào `requirements.txt` và cấu hình Handler entrypoint cho Lambda | 07/07/2026 | 07/07/2026 | [Triển khai Lambda với Docker Container Image](https://docs.aws.amazon.com/lambda/latest/dg/images-create.html) |
| 4 | - Thực hiện build Docker Image cục bộ (`docker build -t smartdoc-backend .`) <br> - Gắn tag cho image theo địa chỉ ECR URI (`docker tag ...`) và đẩy (push) image lên Private ECR Repository <br> - Quản lý Image Tags, kiểm tra dung lượng các lớp image (layer size) và bật tính năng Vulnerability Scanning trên ECR | 08/07/2026 | 08/07/2026 | [Tính năng quét lỗ hổng bảo mật Amazon ECR](https://docs.aws.amazon.com/AmazonECR/latest/userguide/image-scanning.html) |
| 5 | - Khởi tạo Lambda Function mới với tùy chọn chọn nguồn từ **Container Image** stored trong ECR Repository vừa push <br> - Cấu hình dung lượng bộ nhớ (Memory Allocation: 1024MB), Timeout (30 giây) và thiết lập IAM Execution Role phù hợp cho Lambda Container | 09/07/2026 | 09/07/2026 | [Cấu hình AWS Lambda chạy từ Container Image](https://docs.aws.amazon.com/lambda/latest/dg/configuration-images.html) |
| 6 | - **Thực hành tổng hợp:** Kết nối API Gateway làm trigger cho Lambda Container Image mới triển khai <br> - Thực hiện kiểm thử toàn bộ API endpoints từ Postman, đánh giá thời gian khởi động lạnh (Cold Start latency) và đo lường hiệu năng phản hồi của hệ thống Serverless Container | 10/07/2026 | 10/07/2026 | [Tích hợp API Gateway với Lambda Container](https://docs.aws.amazon.com/apigateway/latest/developerguide/http-api-develop-integrations-lambda.html) |

### Kết quả đạt được tuần 3:

* Nắm vững cách quản lý Docker Container Images với Amazon ECR (xác thực, push, tag, scan vulnerabilities).
* Đóng gói thành công ứng dụng FastAPI Backend thành Docker Image nhỏ gọn, tối ưu cho môi trường serverless.
* Triển khai thành công AWS Lambda Function chạy từ Container Image trên ECR và kết nối hoàn chỉnh với API Gateway.
