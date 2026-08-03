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
| 2 | - Tìm hiểu kiến trúc **Amazon Bedrock AgentCore Runtime** – môi trường thực thi và điều phối vòng đời của các AI Agent <br> - **Thực hành:** Lập trình **Coordinator Agent** tiếp nhận yêu cầu từ người dùng, phân tích ý định (intent analysis) và tự động chọn công cụ (tool) xử lý thích hợp | 20/07/2026 | 20/07/2026 | [Hướng dẫn phát triển AI Agents trên Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/agents.html) |
| 3 | - Nghiên cứu giải pháp tách biệt hoàn toàn ranh giới bảo mật ra khỏi mã nguồn ứng dụng trong AgentCore <br> - Tìm hiểu cú pháp và cấu trúc của ngôn ngữ ủy quyền **Cedar** (phân biệt các mệnh đề `permit` cho phép và `forbid` cấm tuyệt đối) | 21/07/2026 | 21/07/2026 | [Ngôn ngữ Phân quyền Cedar (Cedar Policy Specification)](https://www.cedarpolicy.com/en/docs) |
| 4 | - Viết các file chính sách bảo mật bằng ngôn ngữ Cedar trong **Policy Engine** để kiểm soát quyền gọi công cụ (tool invocation) của Agent <br> - Áp dụng kiểm thử chính sách ở chế độ ghi nhật ký (`log-only`) để đánh giá hành vi trước khi chặn thực tế | 22/07/2026 | 22/07/2026 | [Tài liệu quản lý chính sách bảo mật Cedar](https://docs.aws.amazon.com/verifiedpermissions/latest/userguide/policies.html) |
| 5 | - Cấu hình **Bedrock Gateway** làm chốt chặn trung tâm đánh chặn (intercept) mọi lưu lượng truy cập từ Agent <br> - Tích hợp các rào cản an toàn **Guardrails** để lọc các cụm từ độc hại, ngăn chặn tấn công tiêm mã (Prompt Injection) và bảo vệ dữ liệu nhạy cảm | 23/07/2026 | 23/07/2026 | [Cấu hình Bedrock Guardrails bảo vệ ứng dụng AI](https://docs.aws.amazon.com/bedrock/latest/userguide/guardrails.html) |
| 6 | - **Thực hành tổng hợp:** Tiến hành kiểm thử bảo mật tích hợp giữa AgentCore Runtime -> Policy Engine -> Bedrock Gateway <br> - Giả lập các hành vi truy vấn trái phép và xác nhận hệ thống chặn đứng chính xác theo đúng chính sách Cedar đã định nghĩa | 24/07/2026 | 24/07/2026 | [Tài liệu Trung tâm Bảo mật AWS Security Hub](https://docs.aws.amazon.com/securityhub/latest/userguide/what-is-securityhub.html) |

### Kết quả đạt được tuần 5:

* Hiểu sâu kiến trúc Amazon Bedrock AgentCore Runtime và lập trình thành công Coordinator Agent điều phối tác vụ thông minh.
* Thành thạo viết chính sách bảo mật bằng ngôn ngữ Cedar trong Policy Engine, tách biệt hoàn toàn bảo mật khỏi mã nguồn ứng dụng.
* Thiết lập thành công Bedrock Gateway và Guardrails, đảm bảo AI Agent hoạt động an toàn tuyệt đối cấp doanh nghiệp.
