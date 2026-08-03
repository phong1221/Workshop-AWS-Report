---
title: "Nhật ký Tuần 6: Kiểm thử các công nghệ hiện tại & Toàn bộ dự án"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu:
* Tiến hành kiểm thử thành phần các công nghệ dịch vụ hạ tầng đám mây hiện tại (Amazon S3, Amazon Cognito, Amazon DynamoDB, FastAPI Backend).
* Thực hiện kiểm thử toàn bộ hệ thống dự án End-to-End (E2E Integration Testing) nhằm đánh giá độ ổn định và an toàn thông tin.
* Rà soát hiệu năng hệ thống và chuẩn bị hồ sơ nghiệm thu kỹ thuật.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Xuất bản bài Blog 3 và Kiểm thử công nghệ kho lưu trữ Amazon S3.<br>- **Thực hành & Viết bài Blog 3:**<br>&emsp;+ Bước 1: Biên soạn bài viết kỹ thuật **Blog 3** (*5 Sai Lầm Kinh Điển Khi Triển Khai Kiến Trúc Serverless Trên AWS & Cách Khắc Phục*) và đăng tải lên AWS Study Group VN.<br>&emsp;+ Bước 2: Kiểm thử các tính năng công nghệ S3: quy tắc mã hóa SSE-S3 AES-256, cờ cô lập Block Public Access và chính sách Bucket Policy.<br>&emsp;+ Bước 3: Kiểm thử thời gian sống TTL của Presigned URL và kiểm tra tính hợp lệ của HTTP CORS headers từ phía trình duyệt client. | 27/07/2026 | 27/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) & Blog 3 |
| - Kiểm thử công nghệ dịch vụ quản lý định danh Amazon Cognito User Pools.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Kiểm thử các kịch bản đăng ký tài khoản mới với email hợp lệ và kiểm tra quy tắc bắt lỗi email trùng lặp.<br>&emsp;+ Bước 2: Kiểm thử luồng gửi và xác nhận mã OTP 6 chữ số qua Email, thử nghiệm trường hợp nhập mã OTP sai hoặc mã OTP đã quá hạn 10 phút.<br>&emsp;+ Bước 3: Kiểm thử luồng đăng nhập cấp phát JWT Tokens và đo thời gian phản hồi xác thực. | 28/07/2026 | 28/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Kiểm thử công nghệ cơ sở dữ liệu NoSQL Amazon DynamoDB.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Chạy script kiểm thử hiệu năng đọc/ghi dữ liệu (Read/Write performance benchmark) trên bảng cơ sở dữ liệu người dùng.<br>&emsp;+ Bước 2: Đo đạc độ trễ truy vấn dữ liệu theo Partition Key định danh người dùng ghi nhận kết quả phản hồi trung bình chỉ 6ms.<br>&emsp;+ Bước 3: Thử nghiệm kích hoạt tính năng khôi phục theo thời gian PITR (Point-in-time recovery) và kiểm tra cờ mã hóa Encryption at Rest trên AWS Console. | 29/07/2026 | 29/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Kiểm thử công nghệ FastAPI Backend Framework và Middleware xác thực JWT.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Chạy bộ kiểm thử tự động `pytest` cho các API router xác thực và quản lý hồ sơ cá nhân.<br>&emsp;+ Bước 2: Thử nghiệm gửi các HTTP Request mang JWT Access Token không hợp lệ, Token đã hết hạn hoặc chữ ký RS256 bị can thiệp để xác minh phản hồi lỗi HTTP 401 Unauthorized.<br>&emsp;+ Bước 3: Đánh giá độ ổn định của Middleware giải mã JWKS và kiểm tra log truy vết trên hệ thống backend. | 30/07/2026 | 30/07/2026 | |
| - Kiểm thử toàn bộ hệ thống dự án End-to-End (E2E System Integration Testing).<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xây dựng kịch bản kiểm thử toàn diện kịch bản người dùng từ giao diện Web đến hạ tầng đám mây AWS.<br>&emsp;+ Bước 2: Thực hiện kiểm thử tuần tự toàn bộ luồng: Đăng ký tài khoản -> Nhận OTP Email -> Kích hoạt tài khoản -> Đăng nhập lấy JWT Token -> Xem hồ sơ -> Cập nhật thông tin -> Tải ảnh Avatar trực tiếp lên S3 qua Presigned URL -> Lưu dữ liệu DynamoDB.<br>&emsp;+ Bước 3: Ghi nhận kết quả: 100% kịch bản kiểm thử toàn bộ dự án đều thành công, hệ thống vận hành đồng bộ và ổn định. | 31/07/2026 | 31/07/2026 | |
| - **Họp nhóm:** Đánh giá hiệu năng CSDL DynamoDB & toàn bộ dự án, tổng kết nghiệm thu đồ án SmartDocAI và sẵn sàng báo cáo hội đồng.<br>- **Nội dung họp chi tiết:**<br>&emsp;+ Họp tổng kết kết quả kiểm thử các công nghệ thành phần (S3, Cognito, DynamoDB, FastAPI) và kịch bản E2E toàn hệ thống.<br>&emsp;+ Rà soát các chỉ số độ trễ, an toàn bảo mật và khả năng phục hồi dữ liệu.<br>&emsp;+ Thống nhất hoàn thành nghiệm thu kỹ thuật, sẵn sàng cho Tuần 7 quay video demo và hoàn thiện các phần nội dung còn thiếu. | 01/08/2026 | 01/08/2026 | |

### Kết quả đạt được:
* Hoàn thành kiểm thử chi tiết các công nghệ cốt lõi hiện tại (S3, Cognito, DynamoDB, FastAPI) với kết quả đạt chuẩn kỹ thuật.
* Kiểm thử toàn bộ dự án End-to-End thành công 100%, chứng minh tính đồng bộ và độ tin cậy cao của toàn hệ thống.
* Đội ngũ sẵn sàng cho tuần cuối cùng để quay video demo và đóng gói hồ sơ báo cáo đồ án.
