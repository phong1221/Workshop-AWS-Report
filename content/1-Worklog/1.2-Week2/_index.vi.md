---
title: "Worklog Tuần 2: Nghiên cứu & Thiết kế hạ tầng Amazon S3 cho Backend"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Mục tiêu:
* Thiết kế chi tiết sơ đồ kho lưu trữ Amazon S3 phục vụ lưu trữ tài liệu Backend và ảnh đại diện người dùng.
* Xây dựng giải pháp bảo mật cách ly dữ liệu, mã hóa và cấu hình chia sẻ tài nguyên CORS.
* Nghiên cứu luồng tải file an toàn từ ứng dụng lên kho lưu trữ bằng liên kết tạm thời Presigned URL.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Tìm hiểu lý thuyết: Quy tắc đặt tên S3 Bucket chuẩn hóa tuân thủ hướng dẫn của AWS và lựa chọn AWS Region tối ưu chi phí & khả năng tương thích dịch vụ.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Đăng nhập AWS Management Console và tiến hành khởi tạo kho lưu trữ S3 chính thức cho hệ thống Backend.<br>&emsp;+ Bước 2: Quy hoạch cấu trúc phân vùng thư mục bên trong kho lưu trữ: thư mục chứa tài liệu đính kèm, thư mục chứa ảnh đại diện người dùng và thư mục chứa tệp tạm.<br>&emsp;+ Bước 3: Cấu hình phân quyền quản trị IAM Role/User và rà soát quyền truy cập tài khoản cá nhân. | 29/06/2026 | 29/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Tìm hiểu lý thuyết: Các giải pháp mã hóa dữ liệu S3 ở trạng thái nghỉ: SSE-S3 (Server-Side Encryption with Amazon S3 Managed Keys) vs SSE-KMS (AWS Key Management Service).<br>- **Thực hành:**<br>&emsp;+ Bước 1: Truy cập mục thuộc tính Properties của kho lưu trữ S3 Backend sản xuất.<br>&emsp;+ Bước 2: Bật chế độ mã hóa mặc định Server-Side Encryption SSE-S3 sử dụng thuật toán AES-256.<br>&emsp;+ Bước 3: Tải thử nghiệm tệp mẫu lên kho S3, kiểm tra phần Header metadata để xác nhận mã hóa tự động được áp dụng thành công. | 30/06/2026 | 30/06/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Tìm hiểu lý thuyết: Chiến lược cách ly an toàn dữ liệu: Ngăn chặn triệt để rò rỉ dữ liệu qua Internet bằng chính sách Block Public Access và Bucket Policy.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Kích hoạt cài đặt "Block All Public Access" ở cấp độ S3 Bucket để chặn mọi truy cập public ngẫu nhiên.<br>&emsp;+ Bước 2: Soạn thảo bản tệp S3 Bucket Policy dạng JSON tuân thủ nguyên tắc quyền tối thiểu (Least Privilege).<br>&emsp;+ Bước 3: Áp dụng Bucket Policy chỉ cho phép các yêu cầu có chữ ký hợp lệ từ IAM Credentials của Backend API truy xuất dữ liệu. | 01/07/2026 | 01/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Tìm hiểu lý thuyết: Cơ chế chia sẻ tài nguyên giữa các nguồn Cross-Origin Resource Sharing (CORS) cho kho S3 khi ứng dụng Web chạy trên domain/origin riêng biệt.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Soạn thảo file cấu hình CORS JSON quy định các miền nguồn HTTP cấp phép (môi trường máy trạm local và domain sản xuất), danh sách phương thức HTTP cho phép (GET, PUT, POST, DELETE, HEAD) và danh sách header hợp lệ.<br>&emsp;+ Bước 2: Cập nhật cấu hình CORS vào phần Permissions của S3 Bucket trên AWS Console.<br>&emsp;+ Bước 3: Sử dụng cURL từ máy trạm thực hiện gửi Preflight OPTIONS Request tới S3 Endpoint để kiểm tra các HTTP Header trả về. | 02/07/2026 | 02/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| - Tìm hiểu lý thuyết: Giải pháp tải/đọc tệp an toàn thông qua Presigned URL mà không cần công khai S3 Bucket.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Viết script Python thử nghiệm dùng SDK `boto3` để khởi tạo Presigned URL cho thao tác tải tệp và đọc tệp.<br>&emsp;+ Bước 2: Cấu hình tham số thời gian sống (TTL / Expiration) cho Presigned URL ở mức 900 giây (15 phút) nhằm đảm bảo an toàn tối đa.<br>&emsp;+ Bước 3: Dùng Postman gửi yêu cầu HTTP PUT đính kèm tệp nhị ảnh/tài liệu trực tiếp lên Presigned URL vừa sinh và xác nhận tệp đã lưu vào S3 thành công. | 03/07/2026 | 03/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Tìm hiểu: Rà soát tổng thể và đánh giá an toàn hạ tầng S3 Backend đã thiết kế.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Thử nghiệm truy cập trực tiếp URL của S3 Object qua trình duyệt web mà không có Presigned URL để xác nhận trả về lỗi từ chối kết nối (403 Forbidden).<br>&emsp;+ Bước 2: Tổng hợp sơ đồ thiết kế hạ tầng S3, bảng quy định thư mục và bộ quy tắc CORS/Bucket Policy.<br>&emsp;+ Bước 3: Lưu trữ toàn bộ tệp cấu hình infrastructure dưới dạng tài liệu kỹ thuật phục vụ cho khâu triển khai thực tế ở Tuần 3. | 04/07/2026 | 04/07/2026 | |

### Kết quả đạt được:
* Hoàn thành bản thiết kế chi tiết kiến trúc kho lưu trữ Amazon S3 dành riêng cho dữ liệu Backend SmartDocAI.
* Đảm bảo đầy đủ các phương án bảo mật cách ly dữ liệu và cơ chế chia sẻ tài nguyên hợp lệ.
* Chuẩn bị sẵn sàng các thông số cấu hình phục vụ cho quá trình khởi tạo chính thức ở Tuần 3.
