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
| - Tìm hiểu: Quy trình khởi tạo kho lưu trữ S3 phục vụ dữ liệu Backend và Avatar.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Khởi tạo chính thức kho S3 Backend trên hạ tầng AWS Region us-east-1.<br>&emsp;+ Bước 2: Biên soạn nội dung bài Blog 1 (*RAG Đa Phân Quyền Bảo Mật*) theo định dạng Markdown.<br>&emsp;+ Bước 3: Đăng tải bài Blog 1 lên diễn đàn cộng đồng AWS Study Group VN. | 06/07/2026 | 06/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) & Blog 1 |
| - Tìm hiểu lý thuyết: Cơ chế mã hóa tự động ở phía máy chủ (SSE-S3).<br>- **Thực hành:**<br>&emsp;+ Bước 1: Áp dụng quy tắc mã hóa phía máy chủ SSE-S3 cho kho lưu trữ chính thức.<br>&emsp;+ Bước 2: Chạy script tự động đẩy danh sách tệp thử nghiệm lên kho S3.<br>&emsp;+ Bước 3: Kiểm tra tham số ServerSideEncryption trong thuộc tính Metadata để xác nhận mã hóa. | 07/07/2026 | 07/07/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Tìm hiểu lý thuyết: Nguyên tắc cách ly hoàn toàn dữ liệu Backend khỏi các kết nối trái phép.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Kích hoạt tính năng Block Public Access ở cấp độ kho lưu trữ S3.<br>&emsp;+ Bước 2: Kiểm tra chính sách phân vùng cách ly dữ liệu.<br>&emsp;+ Bước 3: Đảm bảo ngăn chặn triệt để mọi rủi ro rò rỉ dữ liệu người dùng ra bên ngoài. | 08/07/2026 | 08/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Tìm hiểu lý thuyết: Giao tiếp giữa ứng dụng Web và kho lưu trữ S3 qua HTTP Headers.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Cập nhật cấu hình CORS hoàn chỉnh cho kho lưu trữ S3 Backend.<br>&emsp;+ Bước 2: Biên soạn nội dung bài Blog 2 (*Kiến Trúc Cơ Sở Cho Amazon Bedrock Trong Môi Trường AWS Landing Zone*).<br>&emsp;+ Bước 3: Xuất bản bài Blog 2 lên cộng đồng AWS Study Group VN. | 09/07/2026 | 09/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) & Blog 2 |
| - Tìm hiểu lý thuyết: Cơ chế kiểm tra thời hạn và chữ ký bảo mật của Presigned URL.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Lập trình hàm sinh địa chỉ liên kết tạm thời Presigned URL trong ứng dụng Backend.<br>&emsp;+ Bước 2: Thử nghiệm kết nối truyền nhận tệp giữa giao diện ứng dụng và kho S3 qua Presigned URL.<br>&emsp;+ Bước 3: Đo đạc thời gian tải tệp dữ liệu đạt tốc độ tối ưu dưới 1.2 giây. | 10/07/2026 | 10/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Tìm hiểu: Đánh giá tổng thể hiệu năng và an toàn thông tin của hạ tầng lưu trữ.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Kiểm thử an toàn thông tin đối với các liên kết Presigned URL đã hết hạn.<br>&emsp;+ Bước 2: Rà soát toàn bộ cấu hình phân quyền và cách ly tài nguyên S3.<br>&emsp;+ Bước 3: Lập bản biên bản nghiệm thu hạ tầng S3 Backend sẵn sàng kết nối. | 11/07/2026 | 11/07/2026 | |

### Kết quả đạt được:
* Khởi tạo thành công hạ tầng lưu trữ Backend S3 trên đám mây AWS đáp ứng tiêu chuẩn bảo mật.
* Kho lưu trữ dữ liệu được cách ly an toàn, bảo vệ dữ liệu khỏi các truy cập trái phép.
* Cơ chế tải dữ liệu trực tiếp bằng Presigned URL vận hành ổn định và chính xác.
