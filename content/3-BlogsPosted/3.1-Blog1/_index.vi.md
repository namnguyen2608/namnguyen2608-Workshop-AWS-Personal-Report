---
title: "Blog 1: XÂY DỰNG AI AGENT TOÀN DIỆN VỚI AMAZON BEDROCK AGENTCORE"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

![Amazon Bedrock AgentCore Thumbnail](/images/3-BlogsPosted/3.1-Blog1/thumbnail.png)

### 1. Bài Toán Thực Tế: Giới Hạn Của Các Mô Hình AI Độc Lập

Hiện nay, các mô hình ngôn ngữ lớn (LLM) đã sở hữu khả năng suy luận và xử lý ngôn ngữ tự nhiên cực kỳ xuất sắc. Tuy nhiên, khi được đưa vào vận hành thực tế tại doanh nghiệp, hiệu suất của chúng thường bị suy giảm nghiêm trọng. Nguyên nhân không nằm ở trí thông minh của mô hình, mà là sự thiếu hụt ngữ cảnh cục bộ và cơ chế phản hồi. Một Agent chăm sóc khách hàng không thể giải quyết yêu cầu nếu bị ngắt kết nối với cơ sở dữ liệu nội bộ, và một trợ lý phân tích sẽ đưa ra lời khuyên lỗi thời nếu chỉ dựa vào tập dữ liệu huấn luyện tĩnh.

### 2. Giải Pháp Cốt Lõi: Khai Thác Tri Thức Đa Tầng Và Học Tập Liên Tục

Để giải quyết giới hạn trên, AWS giới thiệu bản cập nhật mới cho Amazon Bedrock AgentCore. Nền tảng này không chỉ cung cấp sức mạnh tính toán, mà còn đóng vai trò là kiến trúc trung tâm giúp Agent "kết nối" (connect) và "tiến hóa" (optimize). Giải pháp cốt lõi dựa trên việc mở rộng khả năng tiếp cận tri thức của Agent ra ba tầng khác nhau và thiết lập một vòng lặp cải tiến liên tục dựa trên dữ liệu vận hành thực tế.

### 3. Cấu Trúc Khối Năng Lực Của AgentCore

Để tạo ra một AI Agent hoàn chỉnh, AgentCore cung cấp khả năng truy cập vào ba khối tri thức chuyên biệt:

* **Khối Tri Thức Tổ Chức (Organizational Knowledge):** Trọng tâm của khối này là Amazon Bedrock Managed Knowledge Base. Hệ thống tự động kết nối Agent với các nguồn dữ liệu phân tán của doanh nghiệp như SharePoint, Google Drive, Confluence, và S3. Điều này loại bỏ hoàn toàn yêu cầu xây dựng các đường ống (pipeline) nạp dữ liệu thủ công, cho phép Agent khai thác dữ liệu độc quyền ngay lập tức.
* **Khối Tri Thức Mở Rộng (Web Knowledge):** Để khắc phục độ trễ của dữ liệu huấn luyện, Agent được trang bị khả năng tìm kiếm web theo thời gian thực, giúp truy xuất thông tin mới nhất trên internet để phản hồi các sự kiện hoặc xu hướng tức thời.
* **Khối Dữ Liệu Chuyên Sâu (Paid Knowledge):** Agent có khả năng tích hợp trực tiếp với các cổng dữ liệu trả phí (ví dụ: thông tin thị trường tài chính, báo cáo ngành), giúp nâng cao chất lượng và độ sâu của các phân tích chuyên môn.

### 4. Cơ Chế Giám Sát Và Kiểm Soát Rủi Ro (Governance & Guardrails)

Khi mức độ tự chủ và quyền truy cập dữ liệu của Agent được mở rộng, hệ thống đòi hỏi một cơ chế kiểm soát chặt chẽ:

* **Continuous Learning (Học tập liên tục):** AgentCore cung cấp các công cụ phân tích luồng thực thi (tracing) giúp đội ngũ phát triển quan sát chi tiết cách Agent lập luận và ra quyết định trong môi trường production. Dựa trên dữ liệu giám sát này, nhà phát triển có thể thiết lập các vòng lặp phản hồi để liên tục tinh chỉnh và tối ưu hóa hiệu suất.
* **Scalable Guardrails (Rào cản an toàn):** Hệ thống tích hợp các lớp rào cản bảo mật để đảm bảo Agent hoạt động trong khuôn khổ các quy định của doanh nghiệp, ngăn chặn việc xử lý các yêu cầu không an toàn hoặc truy cập dữ liệu vượt quá thẩm quyền.

---

**Tài Liệu Tham Khảo:**
* [AWS Machine Learning Blog - Build agents with broader knowledge and continuous learning](https://aws.amazon.com/vi/blogs/machine-learning/new-in-amazon-bedrock-agentcore-build-agents-with-broader-knowledge-and-continuous-learning/)
* [Bài viết trên AWS Study Group FCJ (Facebook)](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2212632786168348/)