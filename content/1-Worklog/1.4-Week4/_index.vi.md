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
| - Nghiên cứu mô hình lưu trữ đối tượng người dùng trong Amazon Cognito User Pools.<br>- Lựa chọn địa chỉ Email làm thuộc tính định danh đăng nhập chính.<br>- Khai báo các thuộc tính bổ sung như họ tên và số điện thoại. | 13/07/2026 | 13/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Thực hiện khởi tạo dịch vụ Amazon Cognito User Pool trên đám mây AWS.<br>- Thiết lập trung tâm lưu trữ và quản lý định danh người dùng tập trung.<br>- Cấu hình các tham số vận hành cho dịch vụ xác thực. | 14/07/2026 | 14/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Thiết lập chính sách bảo mật mật khẩu người dùng theo tiêu chuẩn an toàn.<br>- Cấu hình dịch vụ tự động gửi mã xác thực OTP 6 chữ số qua Email.<br>- Đảm bảo quy trình xác thực tài khoản diễn ra tự động khi đăng ký. | 15/07/2026 | 15/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Khởi tạo ứng dụng kết nối (App Client) trong Cognito User Pool.<br>- Cấu hình các luồng xác thực an toàn cho ứng dụng khách.<br>- Cho phép ứng dụng trao đổi thông tin xác thực với Cognito. | 16/07/2026 | 16/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Thực hiện đăng ký tài khoản người dùng thử nghiệm trên hệ thống.<br>- Kiểm tra tính năng tự động gửi mã xác thực OTP 6 chữ số về Email.<br>- Xác minh trạng thái kích hoạt tài khoản chuyển sang thành công. | 17/07/2026 | 17/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Rà soát toàn bộ cấu hình bảo mật của Cognito User Pool.<br>- Đảm bảo chỉ áp dụng xác thực Email OTP (không bật Google OAuth).<br>- Lưu trữ các định danh kết nối chuẩn bị cho công tác tích hợp Backend. | 18/07/2026 | 18/07/2026 | |

### Kết quả đạt được:
* Khởi tạo và cấu hình thành công Amazon Cognito User Pool cho bài toán xác thực người dùng.
* Luồng gửi mã OTP xác thực qua Email vận hành ổn định và chính xác.
* Chuẩn bị đầy đủ các thông số tích hợp sẵn sàng kết nối với Backend ở tuần tiếp theo.
