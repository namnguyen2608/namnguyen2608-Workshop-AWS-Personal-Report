---
title: "Blog 3: BẢO MẬT AI AGENT VỚI CHÍNH SÁCH TRONG AMAZON BEDROCK AGENTCORE"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.3. </b> "
---

![Secure AI Agents Thumbnail](/images/3-BlogsPosted/3.3-Blog3/thumbnail.png)

### 1. Rủi Ro Bảo Mật Từ Sự Tự Chủ Của AI Agent

Việc triển khai các AI Agent an toàn trong các ngành bị quản lý nghiêm ngặt (như y tế) là một thách thức lớn. Sự tự chủ của Agent trong việc đưa ra quyết định gọi công cụ, truy cập dữ liệu và thích ứng với môi trường chính là sức mạnh của chúng, nhưng cũng đồng thời tạo ra rủi ro bảo mật lớn nếu không có ranh giới rõ ràng. Do phụ thuộc vào mô hình ngôn ngữ lớn, Agent có thể bị ảo giác hoặc bị tấn công tiêm mã để vượt qua các rào cản an toàn. Việc nhúng các quy tắc bảo mật vào mã nguồn của ứng dụng thường tạo ra các rủi ro ngầm, khiến hệ thống khó kiểm toán và độ an toàn chỉ phụ thuộc vào tính chính xác của đoạn mã đó.

### 2. Giải Pháp Cốt Lõi: Lớp Kiểm Soát Chính Sách Độc Lập

Để giải quyết tận gốc rủi ro này, Amazon Bedrock AgentCore đưa ra giải pháp tách biệt hoàn toàn ranh giới bảo mật ra khỏi mã nguồn của Agent. Giải pháp tạo ra một lớp thực thi mang tính tất định, hoạt động hoàn toàn độc lập với khả năng suy luận của Agent. Cơ chế này sử dụng ngôn ngữ ủy quyền Cedar – một ngôn ngữ phân quyền vừa hiệu quả cho máy tính xử lý, vừa dễ dàng cho con người đọc và kiểm toán. Nhờ đó, Agent bị "cô lập" với thế giới bên ngoài, và mọi quy tắc an toàn được áp đặt trước khi Agent có thể thực thi bất kỳ công cụ nào.

### 3. Cấu Trúc Khối Năng Lực Bảo Mật Của AgentCore

Kiến trúc bảo mật của AgentCore xoay quanh sự kết hợp của các thành phần sau:

* **Động cơ chính sách (Policy Engine):** Là nơi tập hợp các chính sách được viết bằng ngôn ngữ Cedar. Nhà phát triển có thể tạo chính sách bằng ba cách: viết trực tiếp mã Cedar, sử dụng biểu mẫu, hoặc mô tả bằng ngôn ngữ tự nhiên (tiếng Anh) để hệ thống tự động dịch sang mã Cedar.
* **Cổng giao tiếp (Gateway):** Đóng vai trò là chốt chặn trung tâm, đánh chặn (intercept) mọi lưu lượng truy cập của Agent. Gateway sẽ đánh giá mọi yêu cầu gọi công cụ dựa trên Policy Engine trước khi quyết định cấp hoặc từ chối quyền truy cập.
* **Cơ chế kiểm thử an toàn:** Hệ thống cho phép gán Policy Engine vào Gateway ở chế độ chỉ ghi nhật ký (log-only). Điều này giúp đánh giá xem các chính sách hoạt động ra sao trên lưu lượng thực tế mà không gây gián đoạn quy trình, trước khi bật chế độ thực thi chặn đứng.

### 4. Cơ Chế Giám Sát Và Thiết Lập Rào Chắn

Hệ thống áp dụng mô hình bảo mật "mặc định từ chối" (default deny), nghĩa là mọi yêu cầu không khớp với chính sách cho phép (permit) sẽ tự động bị chặn lại. Dưới đây là các cơ chế kiểm soát rủi ro điển hình:

* **Kiểm soát dựa trên danh tính:** Đảm bảo nguyên tắc người dùng nào chỉ được truy cập dữ liệu của người đó. Ví dụ: Trong ứng dụng y tế, Policy đảm bảo tham số `patient_id` mà Agent gọi phải khớp chính xác với ID của bệnh nhân đã được xác thực.
* **Phân tách quyền Đọc/Ghi:** Doanh nghiệp có thể thiết lập chính sách cho phép quyền truy cập đọc rộng rãi nhưng giới hạn cực kỳ khắt khe đối với các tác vụ ghi/thay đổi dữ liệu.
* **Kiểm soát rủi ro bằng quy tắc cấm (Forbid rules):** Ngôn ngữ Cedar thiết lập quy tắc "từ chối luôn thắng". Các quy tắc forbid có thể được dùng để chặn cứng các hành vi rủi ro như gọi công cụ đặt lịch hẹn ngoài giờ hành chính (chỉ cho phép từ 9am đến 9pm), bất kể LLM có cố gắng viện lý do gì.

---

**Tài Liệu Tham Khảo:**
* [AWS Machine Learning Blog - Secure AI agents with Policy in Amazon Bedrock AgentCore](https://aws.amazon.com/vi/blogs/machine-learning/secure-ai-agents-with-policy-in-amazon-bedrock-agentcore/)
* [Bài viết trên AWS Study Group FCJ (Facebook)](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2226907561407537/)