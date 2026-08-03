---
title: "Worklog Tuần 3: Triển khai hạ tầng Amazon S3 cho Backend"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Mục tiêu:
* Triển khai khởi tạo kho lưu trữ Amazon S3 phục vụ dữ liệu Backend và ảnh đại diện người dùng.
* Cấu hình mã hóa dữ liệu, chặn truy cập công khai và thiết lập quy tắc chia sẻ tài nguyên CORS.
* Thực hiện kiểm thử tính năng tải file an toàn thông qua cơ chế Presigned URL.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Triển khai thực tế kho lưu trữ Amazon S3 chính thức cho hệ thống SmartDocAI Backend.<br>- **Thực hành & Viết bài Blog 1:**<br>&emsp;+ Bước 1: Khởi tạo chính thức kho S3 Bucket trên hạ tầng AWS Region đã lựa chọn với đầy đủ tham số cấu hình đã thiết kế ở Tuần 2.<br>&emsp;+ Bước 2: Biên soạn bài viết kỹ thuật **Blog 1** với chủ đề: *"Xây dựng Kiến trúc RAG Đa Phân Quyền Bảo Mật trên Hạ tầng AWS Cloud"* theo định dạng Markdown.<br>&emsp;+ Bước 3: Đăng tải bài Blog 1 lên diễn đàn cộng đồng AWS Study Group VN và thu nhận phản hồi từ cộng đồng. | 06/07/2026 | 06/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) & Blog 1 |
| - Thực thi áp dụng quy tắc mã hóa phía máy chủ SSE-S3 trên kho S3 chính thức.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Kích hoạt mã hóa SSE-S3 (AES-256) trên toàn bộ kho S3 bằng giao diện CLI/Console.<br>&emsp;+ Bước 2: Chạy script tự động hóa tải lên bộ 50 tệp mẫu dữ liệu kiểm thử (PDF, PNG, JPEG).<br>&emsp;+ Bước 3: Thực hiện trích xuất thuộc tính Metadata của các tệp trên S3 để kiểm tra cờ mã hóa phía máy chủ. | 07/07/2026 | 07/07/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Áp dụng chính sách cách ly bảo mật dữ liệu tuyệt đối trên hạ tầng S3.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Bật chính sách Block Public Access ở mức Bucket và Account level.<br>&emsp;+ Bước 2: Cài đặt S3 Bucket Policy siết chặt quyền truy cập chỉ cho phép IAM User/Role của FastAPI Backend.<br>&emsp;+ Bước 3: Tiến hành kiểm tra an toàn bằng công cụ AWS Trusted Advisor và CloudWatch Metrics để xác nhận không có bất kỳ lỗ hổng truy cập public nào. | 08/07/2026 | 08/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Cấu hình hoàn chỉnh quy tắc CORS và viết bài Blog 2 chia sẻ kiến thức.<br>- **Thực hành & Viết bài Blog 2:**<br>&emsp;+ Bước 1: Áp dụng bản cấu hình CORS JSON chuẩn vào kho S3 Backend, hỗ trợ đầy đủ các HTTP Header xác thực và định dạng nội dung.<br>&emsp;+ Bước 2: Biên soạn bài viết kỹ thuật **Blog 2** với chủ đề: *"Kiến Trúc Cơ Sở Cho Amazon Bedrock Trong Môi Trường AWS Landing Zone Enterprise"*.<br>&emsp;+ Bước 3: Đăng tải bài Blog 2 lên diễn đàn cộng đồng AWS Study Group VN. | 09/07/2026 | 09/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) & Blog 2 |
| - Xây dựng module tích hợp Presigned URL trong ứng dụng Backend FastAPI.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Lập trình dịch vụ lưu trữ S3 trong FastAPI hỗ trợ phương thức tạo Presigned URL cho upload và download.<br>&emsp;+ Bước 2: Tích hợp cơ chế tự động tạo tên tệp ngẫu nhiên UUIDv4 để tránh trùng lặp tệp dữ liệu người dùng tải lên.<br>&emsp;+ Bước 3: Thực hiện kiểm thử truyền tải dữ liệu giữa ứng dụng client và S3: ghi nhận tốc độ phản hồi trung bình chỉ 0.85 giây cho tệp 10MB. | 10/07/2026 | 10/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Đánh giá toàn diện hiệu năng và mức độ an toàn của hạ tầng S3 Backend.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Kiểm thử tấn công thử nghiệm bằng cách sử dụng các Presigned URL đã hết hạn (quá 15 phút) để xác nhận hệ thống từ chối kết nối.<br>&emsp;+ Bước 2: Đánh giá khả năng đáp ứng đồng thời nhiều kết nối đọc/ghi dữ liệu.<br>&emsp;+ Bước 3: Lập biên bản hoàn thành nghiệm thu hạ tầng Amazon S3 sẵn sàng kết nối với module Xác thực ở Tuần 4. | 11/07/2026 | 11/07/2026 | |

### Kết quả đạt được:
* Khởi tạo thành công hạ tầng lưu trữ Backend S3 trên đám mây AWS đáp ứng tiêu chuẩn bảo mật enterprise.
* Kho lưu trữ dữ liệu được cách ly an toàn, bảo vệ dữ liệu khỏi các truy cập trái phép.
* Cơ chế tải dữ liệu trực tiếp bằng Presigned URL vận hành ổn định và đạt hiệu năng phản hồi cao.
