---
title: "Worklog Tuần 1: Tìm hiểu công nghệ & Hạ tầng AWS Serverless"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu:
* Tìm hiểu lý thuyết tổng quan về mô hình kiến trúc điện toán Serverless trên đám mây AWS.
* Nghiên cứu chi tiết nguyên lý hoạt động của 3 dịch vụ hạ tầng AWS cốt lõi được triển khai trong đồ án: Amazon S3, Amazon Cognito và Amazon DynamoDB.
* Phân tích luồng nghiệp vụ xử lý dữ liệu và môi trường ứng dụng web.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - **Tham gia buổi Kick-off FCJ 2026**, tiếp thu định hướng thực tập, quy định vận hành tài nguyên đám mây và yêu cầu báo cáo đồ án từ các Mentor AWS.<br>- Tìm hiểu lý thuyết chuyên sâu: Mô hình Điện toán Serverless (Serverless Computing) trên hạ tầng AWS Cloud, phân tích ưu nhược điểm so với mô hình Server-based truyền thống, cơ chế tự động mở rộng (Auto-scaling), mô hình thanh toán Pay-as-you-go và kiến trúc Event-driven. | 22/06/2026 | 22/06/2026 | |
| - Tìm hiểu lý thuyết: Dịch vụ lưu trữ đối tượng Amazon Simple Storage Service (Amazon S3), khái niệm Bucket/Object, các lớp lưu trữ (Storage Classes), cơ chế mã hóa phía máy chủ (SSE-S3, SSE-KMS), Access Control Lists (ACLs), Bucket Policy và quy tắc chia sẻ tài nguyên CORS.<br>- **Thực hành thử nghiệm:**<br>&emsp;+ Bước 1: Khởi tạo thử nghiệm kho lưu trữ S3 Bucket trên AWS Management Console.<br>&emsp;+ Bước 2: Kích hoạt mã hóa mặc định Server-Side Encryption (SSE-S3) bằng thuật toán AES-256 bảo vệ dữ liệu ở trạng thái nghỉ.<br>&emsp;+ Bước 3: Đánh dấu bật cấu hình "Block All Public Access" nhằm cô lập truy cập công khai, đảm bảo chỉ có các quyền xác thực hợp lệ mới truy cập được. | 23/06/2026 | 23/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Tìm hiểu lý thuyết: Dịch vụ quản lý định danh Amazon Cognito User Pools và cấu trúc mã thông báo bảo mật OAuth 2.0 / JWT Tokens (ID Token, Access Token, Refresh Token).<br>- **Thực hành thử nghiệm:**<br>&emsp;+ Bước 1: Khởi tạo thử nghiệm Cognito User Pool làm thư mục lưu trữ thông tin người dùng.<br>&emsp;+ Bước 2: Cấu hình quy tắc phát hành và tự động gửi mã OTP 6 chữ số qua Email để xác nhận tài khoản.<br>&emsp;+ Bước 3: Khởi tạo App Client thử nghiệm (không dùng Client Secret) để hỗ trợ luồng xác thực từ ứng dụng Web Client. | 24/06/2026 | 24/06/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - **Thảo luận nhóm:** Chốt lựa chọn đề tài đồ án **SmartDocAI** (Hệ thống Phân tích & Hỏi đáp tài liệu thông minh ứng dụng AWS Cloud & AI), phân công nhiệm vụ cụ thể cho từng thành viên.<br>- Tìm hiểu lý thuyết: Nguyên lý hoạt động của CSDL NoSQL Amazon DynamoDB (Partition Key, Sort Key, GSI/LSI, chế độ On-Demand mode và cơ chế Read/Write Capacity Units). | 25/06/2026 | 25/06/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Tìm hiểu lý thuyết: Công nghệ đóng gói container Docker & framework xử lý RESTful API hiệu năng cao Python FastAPI.<br>- **Thực hành thử nghiệm:**<br>&emsp;+ Bước 1: Viết tệp cấu hình Dockerfile đa tầng (multi-stage build) tối ưu dung lượng image và môi trường Python 3.11.<br>&emsp;+ Bước 2: Thực hiện đóng gói ứng dụng Backend FastAPI thành Docker Image và khởi chạy Container trên môi trường máy trạm local.<br>&emsp;+ Bước 3: Sử dụng Postman gọi kiểm thử các cổng kết nối API kiểm tra trạng thái ứng dụng và đo tốc độ phản hồi. | 26/06/2026 | 26/06/2026 | |
| - Tìm hiểu: Mô hình kiến trúc luồng dữ liệu Serverless chuẩn trên AWS (Client -> Web Frontend -> API Gateway / FastAPI Backend -> Cognito Auth / S3 / DynamoDB).<br>- **Thực hành:**<br>&emsp;+ Bước 1: Vẽ sơ đồ kiến trúc tổng thể (Architecture Diagram) phác thảo chi tiết luồng tương tác giữa Frontend, Backend và tài nguyên AWS.<br>&emsp;+ Bước 2: Tổng hợp toàn bộ hồ sơ nghiên cứu lý thuyết, ghi chú kỹ thuật và bảng định nghĩa API vào tài liệu dự án.<br>&emsp;+ Bước 3: Thống nhất với các thành viên trong nhóm về kế hoạch thiết kế & triển khai hạ tầng S3 ở Tuần 2. | 27/06/2026 | 27/06/2026 | |

### Kết quả đạt được:
* Nắm vững kiến thức nền tảng và nguyên lý vận hành của các dịch vụ đám mây cốt lõi (S3, Cognito, DynamoDB) cùng framework xử lý Backend FastAPI.
* Xác định được mô hình kiến trúc tổng thể và luồng dữ liệu chuẩn hóa cho hệ thống SmartDocAI.
* Tuân thủ đúng định hướng: chỉ tập trung nghiên cứu tài liệu lý thuyết và thử nghiệm môi trường sandbox local, không triển khai bất kỳ tài nguyên sản xuất chính thức nào trong tuần đầu tiên.
