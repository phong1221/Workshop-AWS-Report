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
| - Nghiên cứu các quy tắc đặt tên chuẩn hóa cho kho lưu trữ Amazon S3 trên toàn cầu.<br>- Lựa chọn vùng địa lý triển khai hạ tầng phù hợp trên đám mây AWS.<br>- Đảm bảo độ trễ truy cập thấp và tối ưu hóa chi phí lưu trữ dữ liệu Backend. | 29/06/2026 | 29/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Tìm hiểu các phương thức mã hóa dữ liệu trên kho lưu trữ Amazon S3.<br>- Nghiên cứu cơ chế mã hóa tự động ở phía máy chủ với chìa khóa quản lý bởi AWS.<br>- Đảm bảo an toàn tuyệt đối cho tài liệu Backend khi lưu trữ ở trạng thái nghỉ. | 30/06/2026 | 30/06/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Thiết kế giải pháp phân quyền bảo mật truy cập riêng tư cho kho lưu trữ S3.<br>- Nghiên cứu kích hoạt tính năng Chặn truy cập công khai (Block Public Access).<br>- Cách ly hoàn toàn dữ liệu tài liệu Backend khỏi nguy cơ rò rỉ trên Internet. | 01/07/2026 | 01/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Xây dựng chính sách quy tắc chia sẻ tài nguyên giữa các nguồn (CORS).<br>- Khai báo các phương thức yêu cầu HTTP hợp lệ từ địa chỉ ứng dụng web.<br>- Cho phép giao diện ứng dụng kết nối và tải dữ liệu an toàn. | 02/07/2026 | 02/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| - Nghiên cứu giải pháp sinh liên kết tải file có thời hạn (Presigned URL).<br>- Cho phép máy trạm tải trực tiếp tài liệu và ảnh đại diện lên kho lưu trữ S3.<br>- Bỏ qua giới hạn kích thước tệp và tối ưu băng thông máy chủ Backend. | 03/07/2026 | 03/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Tổng hợp toàn bộ bản vẽ thiết kế hạ tầng lưu trữ S3 Backend.<br>- Rà soát kỹ lưỡng các thông số cấu hình an toàn bảo mật.<br>- Chuẩn bị sẵn sàng kịch bản cho giai đoạn triển khai thực tế. | 04/07/2026 | 04/07/2026 | |

### Kết quả đạt được:
* Hoàn thành bản thiết kế chi tiết kiến trúc kho lưu trữ Amazon S3 dành riêng cho dữ liệu Backend.
* Đảm bảo đầy đủ các phương án bảo mật cách ly dữ liệu và cơ chế chia sẻ tài nguyên hợp lệ.
* Chuẩn bị sẵn sàng các thông số cấu hình phục vụ cho quá trình khởi tạo ở tuần tiếp theo.
