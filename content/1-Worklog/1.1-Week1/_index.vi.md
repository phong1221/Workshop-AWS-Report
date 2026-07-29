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
| - Tham gia buổi Kick-off FCJ 2024, nắm quy định thực tập & yêu cầu báo cáo đồ án.<br>- Tìm hiểu lý thuyết: Điện toán máy chủ Serverless trên hạ tầng đám mây AWS. | 22/06/2026 | 22/06/2026 | |
| - Tìm hiểu lý thuyết: Dịch vụ lưu trữ đối tượng Amazon S3, cơ chế phân quyền & quy tắc CORS.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Khởi tạo kho lưu trữ S3 thử nghiệm trên AWS Management Console.<br>&emsp;+ Bước 2: Kích hoạt mã hóa dữ liệu mặc định ở trạng thái nghỉ Server-Side Encryption.<br>&emsp;+ Bước 3: Bật tính năng Chặn toàn bộ truy cập công khai (Block Public Access) để cách ly an toàn. | 23/06/2026 | 23/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Tìm hiểu lý thuyết: Dịch vụ quản lý định danh Amazon Cognito User Pools & mã thông báo JWT.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Khởi tạo trung tâm xác thực Cognito User Pool thử nghiệm.<br>&emsp;+ Bước 2: Cấu hình quy tắc tự động phát hành và gửi mã xác thực OTP 6 chữ số về Email.<br>&emsp;+ Bước 3: Đăng ký ứng dụng khách App Client thử nghiệm phục vụ luồng xác thực. | 24/06/2026 | 24/06/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Thảo luận nhóm: Chốt lựa chọn đề tài đồ án SmartDocAI (Phân tích & Hỏi đáp tài liệu thông minh).<br>- Tìm hiểu lý thuyết: Nguyên lý hoạt động của CSDL NoSQL Amazon DynamoDB (Partition Key, On-Demand mode). | 25/06/2026 | 25/06/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Tìm hiểu lý thuyết: Công nghệ đóng gói container Docker & framework xử lý Backend FastAPI.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Soạn thảo tệp cấu hình Dockerfile tối ưu môi trường ứng dụng.<br>&emsp;+ Bước 2: Thực hiện đóng gói môi trường ứng dụng Backend trên máy trạm local.<br>&emsp;+ Bước 3: Khởi chạy container thử nghiệm và dùng Postman gọi kiểm thử kết nối API. | 26/06/2026 | 26/06/2026 | |
| - Tìm hiểu: Mô hình luồng dữ liệu ứng dụng Web Serverless chuẩn trên đám mây AWS.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Vẽ sơ đồ kiến trúc kết nối luồng dữ liệu tổng thể giữa Frontend, Backend và AWS Cloud.<br>&emsp;+ Bước 2: Tổng hợp toàn bộ hồ sơ nghiên cứu lý thuyết trong tuần.<br>&emsp;+ Bước 3: Thống nhất với các thành viên trong nhóm về kế hoạch triển khai cho giai đoạn tiếp theo. | 27/06/2026 | 27/06/2026 | |

### Kết quả đạt được:
* Nắm vững kiến thức nền tảng và nguyên lý vận hành của các dịch vụ đám mây cốt lõi (S3, Cognito, DynamoDB) cùng framework xử lý Backend.
* Xác định được mô hình kiến trúc tổng thể và luồng dữ liệu chuẩn hóa cho hệ thống.
* Tuân thủ đúng định hướng: chỉ tập trung nghiên cứu tài liệu lý thuyết, không thực hiện bất kỳ thao tác khởi tạo tài nguyên hạ tầng nào trong tuần đầu tiên.
