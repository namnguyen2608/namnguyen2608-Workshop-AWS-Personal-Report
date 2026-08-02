---
title: "Worklog Tuần 5"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu tuần 5:

* Nghiên cứu môi trường thực thi **Amazon Bedrock AgentCore Runtime** và lập trình Coordinator Agent điều phối các tác vụ AI.
* Nghiên cứu ngôn ngữ phân quyền **Cedar** và xây dựng chính sách an toàn trong **AgentCore Policy Engine**.
* Cấu hình **Bedrock Gateway** và các lớp rào cản **Guardrails** để kiểm soát rủi ro và ngăn chặn tấn công tiêm mã (Prompt Injection).

### Các công việc đã thực hiện:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu kiến trúc **Amazon Bedrock AgentCore Runtime** – môi trường thực thi và điều phối vòng đời của các AI Agent <br> - **Thực hành:** Lập trình **Coordinator Agent** tiếp nhận yêu cầu từ người dùng, phân tích ý định (intent analysis) và tự động chọn công cụ (tool) xử lý thích hợp | 20/07/2026 | 20/07/2026 | [Dịch vụ AI/ML trên AWS](https://cloudjourney.awsstudygroup.com/vi/7-aimlservice/) |
| 3 | - Nghiên cứu giải pháp tách biệt hoàn toàn ranh giới bảo mật ra khỏi mã nguồn ứng dụng trong AgentCore <br> - Tìm hiểu cú pháp và cấu trúc của ngôn ngữ ủy quyền **Cedar** (phân biệt các mệnh đề `permit` cho phép và `forbid` cấm tuyệt đối) | 21/07/2026 | 21/07/2026 | [Quản lý quyền hạn với IAM Policies](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |
| 4 | - Viết các file chính sách bảo mật bằng ngôn ngữ Cedar trong **Policy Engine** để kiểm soát quyền gọi công cụ (tool invocation) của Agent <br> - Áp dụng kiểm thử chính sách ở chế độ ghi nhật ký (`log-only`) để đánh giá hành vi trước khi chặn thực tế | 22/07/2026 | 22/07/2026 | [IAM Permission Boundaries](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |
| 5 | - Cấu hình **Bedrock Gateway** làm chốt chặn trung tâm đánh chặn (intercept) mọi lưu lượng truy cập từ Agent <br> - Tích hợp các rào cản an toàn **Guardrails** để lọc các cụm từ độc hại, ngăn chặn tấn công tiêm mã (Prompt Injection) và bảo vệ dữ liệu nhạy cảm | 23/07/2026 | 23/07/2026 | [Bảo vệ ứng dụng với AWS WAF](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |
| 6 | - **Thực hành tổng hợp:** Tiến hành kiểm thử bảo mật tích hợp giữa AgentCore Runtime -> Policy Engine -> Bedrock Gateway <br> - Giả lập các hành vi truy vấn trái phép và xác nhận hệ thống chặn đứng chính xác theo đúng chính sách Cedar đã định nghĩa | 24/07/2026 | 24/07/2026 | [AWS Security Hub & Bảo mật](https://cloudjourney.awsstudygroup.com/vi/3-optimize/) |

### Kết quả đạt được tuần 5:

* Hiểu sâu kiến trúc Amazon Bedrock AgentCore Runtime và lập trình thành công Coordinator Agent điều phối tác vụ thông minh.
* Thành thạo viết chính sách bảo mật bằng ngôn ngữ Cedar trong Policy Engine, tách biệt hoàn toàn bảo mật khỏi mã nguồn ứng dụng.
* Thiết lập thành công Bedrock Gateway và Guardrails, đảm bảo AI Agent hoạt động an toàn tuyệt đối cấp doanh nghiệp.
