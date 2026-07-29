---
title: "Worklog Tuần 7: Triển khai tích hợp DynamoDB Data Layer & Profile Management"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu:
* Lập trình các API quản lý hồ sơ người dùng kết nối giữa ứng dụng Backend, Cognito, DynamoDB và S3.
* Xử lý tự động khởi tạo hồ sơ người dùng trên DynamoDB khi kích hoạt tài khoản thành công.
* Triển khai tính năng cập nhật thông tin và tải ảnh đại diện Avatar tích hợp giữa S3 Presigned URL và DynamoDB.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Tìm hiểu lý thuyết: Nguyên tắc tự động khởi tạo dữ liệu hồ sơ đồng bộ giữa xác thực và CSDL.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Tích hợp luồng tự động tạo bản ghi hồ sơ mới trên DynamoDB khi xác thực OTP thành công.<br>&emsp;+ Bước 2: Lưu trữ các thông tin ban đầu gồm định danh, Email và mốc thời gian khởi tạo.<br>&emsp;+ Bước 3: Kiểm tra bản ghi dữ liệu xuất hiện chính xác trên CSDL DynamoDB. | 03/08/2026 | 03/08/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Tìm hiểu lý thuyết: Luồng nghiệp vụ trích xuất và xem thông tin hồ sơ cá nhân.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xây dựng luồng xử lý xem thông tin hồ sơ cá nhân trên Backend.<br>&emsp;+ Bước 2: Tự động giải mã JWT Token trong yêu cầu HTTP Header để lấy định danh người dùng.<br>&emsp;+ Bước 3: Truy xuất dữ liệu hồ sơ tương ứng từ CSDL DynamoDB và trả về cho giao diện. | 04/08/2026 | 04/08/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| - Tìm hiểu lý thuyết: Luồng nghiệp vụ cập nhật thông tin hồ sơ cá nhân.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xây dựng luồng tiếp nhận thông tin cập nhật (Họ tên, SĐT) từ phía giao diện.<br>&emsp;+ Bước 2: Kiểm tra tính hợp lệ của dữ liệu đầu vào trên Backend.<br>&emsp;+ Bước 3: Cập nhật thông tin mới vào CSDL DynamoDB kèm mốc thời gian chỉnh sửa. | 05/08/2026 | 05/08/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Tìm hiểu lý thuyết: Tích hợp giữa S3 Presigned URL và DynamoDB cho tính năng cập nhật ảnh đại diện Avatar.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xây dựng luồng sinh địa chỉ Presigned URL dành riêng cho tệp ảnh đại diện.<br>&emsp;+ Bước 2: Cho phép giao diện tải ảnh Avatar trực tiếp từ máy trạm lên kho S3.<br>&emsp;+ Bước 3: Cập nhật đường dẫn ảnh Avatar tương ứng vào hồ sơ người dùng trên CSDL DynamoDB. | 06/08/2026 | 06/08/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Tìm hiểu lý thuyết: Phương pháp viết kiểm thử tự động xác minh tính đúng đắn của các tính năng hồ sơ.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xây dựng kịch bản kiểm thử tự động các thao tác đọc và cập nhật dữ liệu hồ sơ.<br>&emsp;+ Bước 2: Thử nghiệm trường hợp không gửi JWT Token để xác minh cơ chế chặn truy cập trái phép.<br>&emsp;+ Bước 3: Xác nhận tất cả các trường hợp kiểm thử đều vượt qua thành công. | 07/08/2026 | 07/08/2026 | |
| - Tìm hiểu: Đánh giá sự đồng bộ của toàn bộ luồng dữ liệu người dùng end-to-end.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Thực hiện kiểm thử toàn bộ luồng trên giao diện: Đăng ký -> OTP -> Đăng nhập.<br>&emsp;+ Bước 2: Kiểm thử tính năng xem thông tin cá nhân, chỉnh sửa Họ tên/SĐT và đổi Avatar.<br>&emsp;+ Bước 3: Xác nhận dữ liệu hiển thị đồng bộ thời gian thực trên ứng dụng Web. | 08/08/2026 | 08/08/2026 | |

### Kết quả đạt được:
* Tích hợp thành công chuỗi API quản lý hồ sơ cá nhân kết nối giữa Cognito, DynamoDB và S3.
* Dữ liệu người dùng được khởi tạo tự động, lưu trữ nhất quán và cập nhật thời gian thực.
* Chức năng tải ảnh đại diện Avatar qua Presigned URL vận hành ổn định và chính xác.
