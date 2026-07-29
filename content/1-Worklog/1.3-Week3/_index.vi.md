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
| - Thực hiện khởi tạo kho lưu trữ đối tượng Amazon S3 trên đám mây AWS.<br>- Phục vụ quản lý tập trung toàn bộ tài liệu Backend và ảnh đại diện người dùng.<br>- Thiết lập môi trường lưu trữ trên vùng dịch vụ đám mây được lựa chọn.<br>- Đăng bài Blog 1: RAG Đa Phân Quyền Bảo Mật lên AWS Study Group VN. | 06/07/2026 | 06/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Kích hoạt cấu hình mã hóa mặc định ở phía máy chủ (Server-Side Encryption).<br>- Áp dụng khóa mã hóa an toàn cho kho lưu trữ S3 Backend.<br>- Bảo đảm mọi dữ liệu tài liệu khi tải lên đều được tự động mã hóa. | 07/07/2026 | 07/07/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Thiết lập bật tính năng Chặn toàn bộ truy cập công khai (Block Public Access).<br>- Cách ly hoàn toàn kho lưu trữ S3 Backend khỏi mọi kết nối trái phép.<br>- Đảm bảo tính bảo mật và riêng tư tuyệt đối cho dữ liệu người dùng. | 08/07/2026 | 08/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Áp dụng tệp cấu hình quy tắc CORS cho kho lưu trữ S3 Backend.<br>- Cấp phép cho các lệnh yêu cầu HTTP hợp lệ từ domain ứng dụng.<br>- Hỗ trợ giao tiếp và trao đổi dữ liệu an toàn với phía giao diện.<br>- Đăng bài Blog 2: Kiến Trúc Cơ Sở Cho Amazon Bedrock Trong Môi Trường AWS Landing Zone lên AWS Study Group VN. | 09/07/2026 | 09/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| - Thực thi kịch bản kiểm thử tính năng sinh địa chỉ liên kết tạm thời Presigned URL.<br>- Thực hiện tải tệp thử nghiệm trực tiếp lên kho lưu trữ S3 Backend.<br>- Xác nhận quy trình upload file vận hành thành công và chính xác. | 10/07/2026 | 10/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Rà soát tổng thể các tham số bảo mật của kho lưu trữ S3 Backend.<br>- Kiểm tra phân quyền và các cơ chế cách ly an toàn.<br>- Xác nhận hạ tầng lưu trữ đã sẵn sàng vận hành ổn định. | 11/07/2026 | 11/07/2026 | |

### Kết quả đạt được:
* Khởi tạo thành công hạ tầng lưu trữ Backend S3 trên đám mây AWS đáp ứng tiêu chuẩn bảo mật.
* Kho lưu trữ dữ liệu được cách ly an toàn, bảo vệ dữ liệu khỏi các truy cập trái phép.
* Cơ chế tải dữ liệu trực tiếp bằng Presigned URL vận hành ổn định và chính xác.
