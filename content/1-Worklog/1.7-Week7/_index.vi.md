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
| - Tích hợp logic tự động lưu dữ liệu khởi tạo thông tin người dùng vào DynamoDB.<br>- Kích hoạt chèn record hồ sơ ngay khi xác nhận OTP Email thành công.<br>- Đồng bộ thông tin tài khoản giữa dịch vụ xác thực và cơ sở dữ liệu. | 03/08/2026 | 03/08/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Lập trình API xem thông tin hồ sơ cá nhân của người dùng.<br>- Giải mã mã thông báo JWT để lấy mã định danh người dùng hợp lệ.<br>- Truy vấn dữ liệu hồ sơ tương ứng từ DynamoDB trả về phía giao diện. | 04/08/2026 | 04/08/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| - Lập trình API cập nhật thông tin cá nhân người dùng.<br>- Cho phép chỉnh sửa các trường thông tin họ tên, số điện thoại.<br>- Lưu thông tin mới vào DynamoDB kèm mốc thời gian cập nhật. | 05/08/2026 | 05/08/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Triển khai tính năng tải ảnh đại diện Avatar qua kho S3 Backend.<br>- Lập trình API sinh liên kết Presigned URL tải ảnh trực tiếp lên S3.<br>- Lưu đường dẫn ảnh đại diện tương ứng vào hồ sơ người dùng trên DynamoDB. | 06/08/2026 | 06/08/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Viết bộ kiểm thử tự động xác minh tính đúng đắn của các API quản lý hồ sơ.<br>- Kiểm tra chính xác các thao tác đọc, cập nhật dữ liệu trên DynamoDB.<br>- Xử lý các trường hợp ngoại lệ liên quan đến quyền truy cập không hợp lệ. | 07/08/2026 | 07/08/2026 | |
| - Thực hiện kiểm thử tích hợp liên hoàn toàn bộ luồng thông tin người dùng.<br>- Kiểm tra chuỗi: Đăng ký -> OTP -> Đăng nhập -> Profile -> Upload Avatar.<br>- Xác nhận các tính năng kết nối đồng bộ và vận hành trơn tru. | 08/08/2026 | 08/08/2026 | |

### Kết quả đạt được:
* Tích hợp thành công chuỗi API quản lý hồ sơ cá nhân kết nối giữa Cognito, DynamoDB và S3.
* Dữ liệu người dùng được khởi tạo tự động, lưu trữ nhất quán và cập nhật thời gian thực.
* Chức năng tải ảnh đại diện Avatar qua Presigned URL vận hành ổn định và chính xác.
