---
title: "Worklog Tuần 4"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu tuần 4:

* Nghiên cứu dịch vụ **Amazon Bedrock Data Automation (BDA)** – giải pháp tự động trích xuất thông tin ngữ cảnh từ tài liệu đa phương thức.
* Tích hợp BDA API Client vào ứng dụng Lambda Backend để xử lý các tệp tài liệu PDF/DOCX phức tạp.
* Xây dựng đường ống tự động hóa ép kiểu dữ liệu trích xuất thành định dạng JSON có cấu trúc bằng Custom Blueprints.

### Các công việc đã thực hiện:

| Thứ | Công việc | Ngày bắt đầu | Ngày hoàn thành | Nguồn tài liệu |
| --- | --- | --- | --- | --- |
| 2 | - Tìm hiểu tổng quan **Amazon Bedrock Data Automation (BDA)** và các tính năng API hợp nhất trích xuất văn bản <br> - **Thực hành:** Khởi tạo BDA Client trong Python SDK (`boto3`) và cấu hình IAM permissions phù hợp để gọi BDA service | 13/07/2026 | 13/07/2026 | [Tổng quan Amazon Bedrock Data Automation](https://docs.aws.amazon.com/bedrock/latest/userguide/data-automation.html) |
| 3 | - Viết mô-đun Python xử lý tài liệu đa trang (PDF/DOCX) bằng BDA API (`document_processor.py`) <br> - Nghiên cứu cơ chế tự động nhận diện ranh giới các trang, nhóm các phần nội dung logic và duy trì ngữ cảnh tài liệu mà không cần cắt thủ công | 14/07/2026 | 14/07/2026 | [Tài liệu Amazon Bedrock Developer Guide](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html) |
| 4 | - Nghiên cứu và thiết lập **Custom Blueprints** trong BDA để định nghĩa rõ cấu trúc dữ liệu đầu ra cần trích xuất <br> - Cấu hình trích xuất tự động các phần tử phức tạp như bảng biểu (tables), trường biểu mẫu (form fields) và định dạng kết quả ra JSON chuẩn | 15/07/2026 | 15/07/2026 | [Thiết lập Custom Blueprints trong Amazon Bedrock BDA](https://docs.aws.amazon.com/bedrock/latest/userguide/data-automation-blueprints.html) |
| 5 | - Nhúng luồng gọi BDA API vào các API endpoints của Lambda Backend ECR Container <br> - Đánh giá và kiểm tra chỉ số tin cậy (**Confidence Scores**) do BDA trả về cho từng trường dữ liệu trích xuất để đảm bảo chất lượng dữ liệu | 16/07/2026 | 16/07/2026 | [Xây dựng Ứng dụng Serverless với Amazon Bedrock](https://aws.amazon.com/bedrock/) |
| 6 | - **Thực hành tổng hợp:** Gửi tài liệu PDF từ Client -> API Gateway -> Lambda ECR Container xử lý -> BDA API trích xuất -> nhận kết quả JSON có cấu trúc hoàn chỉnh | 17/07/2026 | 17/07/2026 | [Hướng dẫn tích hợp Amazon Bedrock End-to-End](https://docs.aws.amazon.com/bedrock/latest/userguide/welcome.html) |

### Kết quả đạt được tuần 4:

* Nắm vững nguyên lý hoạt động của Amazon Bedrock Data Automation (BDA) trong xử lý tài liệu thông minh.
* Tích hợp thành công BDA API vào Lambda Backend, tự động phân tích và trích xuất dữ liệu từ các tài liệu PDF/DOCX đa trang.
* Áp dụng Custom Blueprints giúp định dạng dữ liệu đầu ra thành chuẩn JSON có cấu trúc với độ chính xác cao.
