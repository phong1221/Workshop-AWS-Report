---
title: "Worklog Tuần 4: Nghiên cứu & Cấu hình Amazon Cognito User Pool"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu:
* Khởi tạo và cấu hình Amazon Cognito User Pool làm dịch vụ xác thực người dùng tập trung.
* Triển khai cơ chế Đăng ký và tự động gửi mã xác thực OTP qua Email (chỉ làm xác thực Email OTP, không áp dụng Google OAuth).
* Tạo ứng dụng kết nối (App Client) và quy định các quy tắc bảo mật mật khẩu người dùng.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Tìm hiểu lý thuyết: Mô hình lưu trữ đối tượng người dùng trong Amazon Cognito User Pools.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Thiết kế bản sơ đồ các trường thuộc tính thông tin người dùng (Email, Họ tên, SĐT, Avatar).<br>&emsp;+ Bước 2: Phân loại thuộc tính định danh bắt buộc và thuộc tính thông tin tùy chọn.<br>&emsp;+ Bước 3: Chuẩn hóa định dạng mã hóa thông tin người dùng. | 13/07/2026 | 13/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Tìm hiểu lý thuyết: Nguyên lý khởi tạo và quản lý trung tâm định danh tập trung bằng Cognito.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Đăng nhập AWS Console và tạo mới trung tâm xác thực Cognito User Pool.<br>&emsp;+ Bước 2: Chọn phương thức đăng nhập chính bằng địa chỉ Email.<br>&emsp;+ Bước 3: Thiết lập các tham số vận hành cho dịch vụ xác thực. | 14/07/2026 | 14/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Tìm hiểu lý thuyết: Tiêu chuẩn độ phức tạp mật khẩu & luồng gửi mã OTP tự động qua Email.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Thiết lập quy tắc độ phức tạp mật khẩu tối thiểu 8 ký tự.<br>&emsp;+ Bước 2: Kích hoạt cơ chế tự động phát hành mã OTP 6 chữ số khi người dùng đăng ký.<br>&emsp;+ Bước 3: Cấu hình mẫu nội dung thông báo gửi mã OTP qua dịch vụ Email của Cognito. | 15/07/2026 | 15/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Tìm hiểu lý thuyết: Cơ chế ủy quyền ứng dụng khách (App Client) trong Cognito.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Tạo mới ứng dụng kết nối App Client trong Cognito User Pool.<br>&emsp;+ Bước 2: Cấu hình chế độ bảo mật không dùng mã bí mật client secret cho ứng dụng Web.<br>&emsp;+ Bước 3: Cấp phép các luồng xác thực tài khoản an toàn cho ứng dụng giao diện. | 16/07/2026 | 16/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Tìm hiểu: Luồng đăng ký tài khoản và nhận mã OTP xác thực thời gian thực.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Thực hiện đăng ký tài khoản người dùng thử nghiệm trên hệ thống.<br>&emsp;+ Bước 2: Trích xuất và nhập mã OTP 6 chữ số gửi về hòm thư Email.<br>&emsp;+ Bước 3: Xác minh trạng thái tài khoản chuyển sang đã kích hoạt chính thức. | 17/07/2026 | 17/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Tìm hiểu: Đánh giá chỉ số an toàn bảo mật của dịch vụ Cognito User Pool.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Rà soát toàn bộ cài đặt an toàn trên Cognito Console.<br>&emsp;+ Bước 2: Vô hiệu hóa các tính năng xác thực không sử dụng để giảm thiểu bề mặt tấn công.<br>&emsp;+ Bước 3: Lưu trữ mã định danh User Pool ID và App Client ID chuẩn bị cho kết nối Backend. | 18/07/2026 | 18/07/2026 | |

### Kết quả đạt được:
* Khởi tạo và cấu hình thành công Amazon Cognito User Pool cho bài toán xác thực người dùng.
* Luồng gửi mã OTP xác thực qua Email vận hành ổn định và chính xác.
* Chuẩn bị đầy đủ các thông số tích hợp sẵn sàng kết nối với Backend ở tuần tiếp theo.
