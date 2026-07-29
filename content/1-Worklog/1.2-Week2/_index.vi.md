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
| - Tìm hiểu lý thuyết: Quy tắc đặt tên S3 Bucket chuẩn hóa & lựa chọn AWS Region tối ưu độ trễ.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Đăng nhập AWS Management Console và khởi tạo kho S3 Backend chính thức tại Region us-east-1.<br>&emsp;+ Bước 2: Thiết lập cấu trúc các thư mục chứa tệp tài liệu và thư mục chứa ảnh đại diện.<br>&emsp;+ Bước 3: Kiểm tra quyền quản trị kho lưu trữ trên tài khoản cá nhân. | 29/06/2026 | 29/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Tìm hiểu lý thuyết: Các phương thức mã hóa dữ liệu S3 bảo vệ dữ liệu ở trạng thái nghỉ.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Truy cập mục cấu hình thuộc tính Properties của kho lưu trữ S3.<br>&emsp;+ Bước 2: Bật tính năng mã hóa mặc định Server-Side Encryption (SSE-S3) sử dụng thuật toán AES-256.<br>&emsp;+ Bước 3: Tải tệp thử nghiệm lên và rà soát thuộc tính mã hóa trong tệp chi tiết. | 30/06/2026 | 30/06/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Tìm hiểu lý thuyết: Giải pháp phân quyền bảo mật riêng tư, cách ly dữ liệu khỏi Internet.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Truy cập mục cấu hình Permissions trên S3 Console.<br>&emsp;+ Bước 2: Bật tính năng Block All Public Access để ngăn chặn kết nối công khai.<br>&emsp;+ Bước 3: Áp dụng bản Bucket Policy riêng tư chỉ cho phép ứng dụng Backend truy xuất. | 01/07/2026 | 01/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Tìm hiểu lý thuyết: Quy tắc chia sẻ tài nguyên giữa các nguồn (CORS - Cross-Origin Resource Sharing).<br>- **Thực hành:**<br>&emsp;+ Bước 1: Soạn thảo bản tệp quy tắc cấu hình CORS JSON cho kho S3.<br>&emsp;+ Bước 2: Khai báo các nguồn HTTP cấp phép và danh sách phương thức HTTP hợp lệ (GET, PUT, POST).<br>&emsp;+ Bước 3: Áp dụng cấu hình CORS lên kho S3 và kiểm tra phản hồi HTTP Header từ máy trạm. | 02/07/2026 | 02/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| - Tìm hiểu lý thuyết: Giải pháp sinh địa chỉ tải tệp tạm thời Presigned URL có thời hạn.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Viết script trợ giúp sinh địa chỉ liên kết tạm thời Presigned URL trên máy trạm.<br>&emsp;+ Bước 2: Cấu hình khoảng thời gian hết hạn an toàn cho liên kết tạm thời.<br>&emsp;+ Bước 3: Dùng Postman kiểm thử tải tệp thử nghiệm qua Presigned URL trực tiếp lên kho S3. | 03/07/2026 | 03/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Tìm hiểu: Rà soát tổng thể các tham số bảo mật của kho lưu trữ S3 Backend.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Kiểm thử thử nghiệm truy cập công khai để xác nhận hệ thống chặn kết nối (403 Forbidden).<br>&emsp;+ Bước 2: Tổng hợp bản vẽ kiến trúc thiết kế hạ tầng S3 Backend.<br>&emsp;+ Bước 3: Lưu trữ hồ sơ cấu hình bảo mật sẵn sàng cho công tác vận hành. | 04/07/2026 | 04/07/2026 | |

### Kết quả đạt được:
* Hoàn thành bản thiết kế chi tiết kiến trúc kho lưu trữ Amazon S3 dành riêng cho dữ liệu Backend.
* Đảm bảo đầy đủ các phương án bảo mật cách ly dữ liệu và cơ chế chia sẻ tài nguyên hợp lệ.
* Chuẩn bị sẵn sàng các thông số cấu hình phục vụ cho quá trình khởi tạo ở tuần tiếp theo.
