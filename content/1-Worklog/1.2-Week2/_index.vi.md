---
title: "Worklog Tuần 2"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu tuần 2:

* Nghiên cứu chuyên sâu dịch vụ tính toán không máy chủ **AWS Lambda**: Handler, Triggers, Execution Role, Environment Variables.
* Nghiên cứu dịch vụ **Amazon API Gateway** (HTTP API & REST API) và cơ chế Proxy Routing (`/{proxy+}`).
* Triển khai mô hình Serverless Backend đơn giản kết hợp giữa API Gateway và AWS Lambda Function.

### Các công việc đã thực hiện:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu chuyên sâu kiến trúc **AWS Lambda**: Cơ chế Stateless Execution, mô hình tính giá Pay-as-you-go, cấu hình Memory Allocation (128MB đến 10GB) và Ephemeral Storage (`/tmp`) <br> - **Thực hành:** Viết hàm Lambda Function đơn giản bằng Python 3.12 trên AWS Console, tìm hiểu cú pháp `event` và `context` object trong Handler function | 29/06/2026 | 29/06/2026 | [Tự động hóa bằng Serverless với AWS Lambda](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |
| 3 | - Nghiên cứu phương thức quản lý quyền truy cập của Lambda thông qua **IAM Execution Role** và cấu hình chính sách `AWSLambdaBasicExecutionRole` <br> - Tìm hiểu cách thiết lập **Environment Variables** để quản lý tham số cấu hình tĩnh của ứng dụng mà không cần hardcode trong mã nguồn <br> - Viết mã xử lý dữ liệu JSON trong Handler function và kiểm thử với các mẫu Event từ AWS Console | 30/06/2026 | 30/06/2026 | [Quản lý quyền hạn với IAM Policies](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |
| 4 | - Tìm hiểu dịch vụ **Amazon API Gateway**, so sánh sự khác biệt về tính năng và chi phí giữa HTTP API và REST API <br> - Nghiên cứu cơ chế **Proxy Integration (`/{proxy+}`)**: Cho phép API Gateway chuyển tiếp nguyên vẹn toàn bộ HTTP Request (headers, query params, body) tới AWS Lambda xử lý | 01/07/2026 | 01/07/2026 | [Xây dựng API Serverless với API Gateway](https://cloudjourney.awsstudygroup.com/vi/4-modernize/) |
| 5 | - Khởi tạo Amazon API Gateway (HTTP API) và thiết lập làm Trigger kích hoạt trực tiếp cho AWS Lambda Function <br> - Cấu hình **CORS (Cross-Origin Resource Sharing)** trên API Gateway để cho phép các ứng dụng Frontend kết nối an toàn từ trình duyệt | 02/07/2026 | 02/07/2026 | [Backend Serverless với Lambda](https://cloudjourney.awsstudygroup.com/vi/4-modernize/) |
| 6 | - **Thực hành tổng hợp:** Sử dụng Postman gửi các request HTTP (GET, POST) tới URL endpoint của API Gateway <br> - Kiểm tra luồng định tuyến request -> Lambda xử lý -> trả phản hồi JSON thành công, đồng thời theo dõi log thực thi trên Amazon CloudWatch Logs | 03/07/2026 | 03/07/2026 | [Giám sát với CloudWatch Logs](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |

### Kết quả đạt được tuần 2:

* Hiểu rõ nguyên lý hoạt động của AWS Lambda và cách quản lý tài nguyên tính toán serverless.
* Làm chủ Amazon API Gateway, hiểu cơ chế Proxy Routing `/{proxy+}` để tiếp nhận và chuyển tiếp HTTP request.
* Xây dựng thành công hệ thống Serverless API Backend hoàn chỉnh (API Gateway -> AWS Lambda).
