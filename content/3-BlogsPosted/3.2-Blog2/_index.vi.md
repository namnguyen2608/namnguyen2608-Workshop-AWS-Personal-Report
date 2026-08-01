---
title: "Blog 2: TỪ PDF ĐẾN INSIGHTS: KIẾN TRÚC XỬ LÝ TÀI LIỆU THÔNG MINH VỚI AWS GENERATIVE AI"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---

![Intelligent Document Processing Thumbnail](/images/3-BlogsPosted/3.2-Blog2/thumbnail.png)

### 1. Nút Thắt Của OCR Truyền Thống

Các tổ chức hiện nay phải xử lý hàng triệu tài liệu mỗi ngày, từ hồ sơ yêu cầu bồi thường bảo hiểm, hóa đơn cho đến hợp đồng pháp lý và hồ sơ y tế. Mặc dù các giải pháp nhận dạng ký tự quang học (OCR) truyền thống có thể trích xuất văn bản, nhưng chúng không thể hiểu được ngữ cảnh, các mối quan hệ hoặc ý nghĩa ẩn chứa bên trong các tài liệu phức tạp. Hạn chế này tạo ra các điểm nghẽn đòi hỏi sự can thiệp thủ công, làm tăng thời gian, chi phí xử lý và đồng thời tiềm ẩn nhiều nguy cơ sai sót.

### 2. Giải Pháp Cốt Lõi: Tự Động Hóa Với Amazon Bedrock Data Automation (BDA)

Để giải quyết bài toán trên, AWS cung cấp một kiến trúc đường ống (pipeline) xử lý tài liệu thông minh, có khả năng mở rộng và tiết kiệm chi phí, được trợ lực bởi các tính năng của Amazon Bedrock. Trái tim của giải pháp là Amazon Bedrock Data Automation (BDA) – một dịch vụ quản lý cung cấp trải nghiệm API hợp nhất giúp tự động trích xuất những thông tin có ý nghĩa từ các nội dung đa phương thức (tài liệu, hình ảnh, video và âm thanh). Khác với OCR thông thường, BDA có khả năng hiểu ngữ cảnh tài liệu, tự động phân chia ranh giới logic, xác thực dữ liệu trích xuất và cung cấp điểm số tin cậy cho độ chính xác.

### 3. Cấu Trúc Khối Năng Lực Của Pipeline Xử Lý

Giải pháp này xử lý tài liệu thông qua 4 lớp được tích hợp chặt chẽ:

* **Lớp Xử lý Đầu vào (Input processing layer):** Quá trình được kích hoạt khi người dùng tải tài liệu lên Amazon S3. Hệ thống sử dụng EventBridge và quy trình làm việc của AWS Step Functions để điều phối BDA, cho phép tự động phân tách tài liệu (lên đến 3.000 trang và 500 MB mỗi yêu cầu API) và phân loại từng phần vào đúng loại tài liệu.
* **Lớp Trích xuất và Lưu trữ (Extraction and storage layer):** Đây là nơi biến đổi nội dung thô thành dữ liệu có cấu trúc. BDA trích xuất văn bản, cấu trúc bảng biểu, các trường biểu mẫu (form) và thậm chí phân tích các thành phần trực quan (như đồ thị, biểu đồ, sơ đồ) để tạo ra chú thích và dữ liệu có cấu trúc. Dữ liệu đầu ra có thể là định dạng tiêu chuẩn hoặc được tùy chỉnh chính xác thông qua các "bản thiết kế" (blueprints) dựa trên từng loại tài liệu cụ thể.
* **Lớp Trí tuệ (Intelligence layer):** Nội dung sau khi trích xuất được đưa vào Amazon Bedrock Knowledge Bases kết hợp với Amazon OpenSearch Serverless. Lớp này duy trì các vector nhúng (vector embeddings) để cho phép tìm kiếm ngữ nghĩa và truy xuất thông tin (RAG) qua nhiều tài liệu khác nhau.
* **Lớp Điều phối Agent (Agentic coordination layer):** Strands Agents chạy trên nền tảng Amazon Bedrock AgentCore Runtime sẽ quản lý tổng thể quy trình. Một Coordinator Agent (Agent điều phối) sẽ định tuyến các yêu cầu đến các Agent chuyên biệt như: Agent phân tích thị trường, Agent tư vấn đầu tư, hoặc External API Agent (để tích hợp dữ liệu thời gian thực từ bên thứ ba).

### 4. Quản Trị, Bảo Mật Và Tối Ưu Hóa Chi Phí

Hệ thống được thiết kế để vận hành an toàn và tiết kiệm ở quy mô doanh nghiệp:

* **Bảo mật cấp doanh nghiệp:** Kiến trúc sử dụng khóa AWS KMS để mã hóa tài liệu và kết quả xử lý, kết nối AWS PrivateLink để truy cập API an toàn trong ranh giới VPC, và áp dụng các nguyên tắc quyền tối thiểu qua IAM roles.
* **Tối ưu hóa chi phí:** Hệ thống áp dụng định tuyến thông minh dựa trên độ phức tạp của tài liệu, xử lý hàng loạt (batch processing) và sử dụng các chính sách vòng đời (lifecycle policies) của Amazon S3 để tự động chuyển tài liệu sang các hạng mục lưu trữ chi phí thấp hơn.
* **Khả năng mở rộng:** Nhờ kiến trúc serverless của AWS Step Functions và xử lý bất đồng bộ, giải pháp đã được kiểm chứng có thể xử lý đồng thời hơn 50.000 tài liệu PDF mà không bị suy giảm hiệu suất.

---

**Tài Liệu Tham Khảo:**
* [AWS Machine Learning Blog - From PDFs to insights: Architecting an intelligent document processing pipeline with AWS generative AI services](https://aws.amazon.com/vi/blogs/machine-learning/from-pdfs-to-insights-architecting-an-intelligent-document-processing-pipeline-with-aws-generative-ai-services/)
* [Bài viết trên AWS Study Group FCJ (Facebook)](https://www.facebook.com/groups/awsstudygroupfcj/permalink/2225158074915819/)