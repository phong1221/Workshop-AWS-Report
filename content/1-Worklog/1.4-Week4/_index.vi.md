---
title: "Worklog Tuần 4: Nghiên cứu & Cấu hình Amazon Cognito User Pool"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Mục tiêu:
* Khởi tạo và cấu hình Amazon Cognito User Pool làm dịch vụ xác thực người dùng tập trung.
* Triển khai cơ chế Đăng ký và tự động gửi mã xác thực OTP qua Email (xác thực qua Email OTP).
* Tạo ứng dụng kết nối (App Client) và quy định các quy tắc bảo mật mật khẩu người dùng.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Phân tích yêu cầu bài toán quản lý định danh người dùng: Mô hình lưu trữ User Profile trong Amazon Cognito User Pools.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Thiết kế sơ đồ các thuộc tính người dùng chuẩn bao gồm: Email (khoá định danh chính), Họ tên, Số điện thoại, Đường dẫn ảnh đại diện và Vai trò người dùng.<br>&emsp;+ Bước 2: Xác định các thuộc tính bắt buộc (required attributes) và thuộc tính tùy chọn (optional attributes).<br>&emsp;+ Bước 3: Chuẩn hóa quy trình mã hóa và lưu trữ thông tin cá nhân tuân thủ tiêu chuẩn an toàn thông tin. | 13/07/2026 | 13/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Khởi tạo và thiết lập trung tâm quản lý định danh Amazon Cognito User Pool.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Truy cập AWS Cognito Console, tạo mới trung tâm quản lý định danh Cognito User Pool cho dự án.<br>&emsp;+ Bước 2: Cấu hình tuỳ chọn đăng nhập chính (Sign-in options) cho phép người dùng đăng nhập bằng địa chỉ Email.<br>&emsp;+ Bước 3: Cấu hình Multi-Factor Authentication (MFA) ở chế độ Optional và thiết lập thông số khôi phục tài khoản qua Email. | 14/07/2026 | 14/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Thiết lập chính sách độ phức tạp mật khẩu & luồng tự động xác nhận mã OTP qua Email.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Cấu hình Password Policy yêu cầu độ dài tối thiểu 8 ký tự, bao gồm chữ hoa, chữ thường, chữ số và ký tự đặc biệt.<br>&emsp;+ Bước 2: Thiết lập luồng xác thực tự động phát hành mã Verification Code OTP 6 chữ số gửi tới hòm thư Email khi đăng ký.<br>&emsp;+ Bước 3: Tùy chỉnh mẫu Email HTML gửi mã OTP với logo dự án SmartDocAI và thời gian hiệu lực mã OTP là 10 phút. | 15/07/2026 | 15/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Khởi tạo ứng dụng kết nối (App Client) trong Cognito User Pool phục vụ Web Application.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Tạo mới ứng dụng kết nối App Client trong Cognito User Pool.<br>&emsp;+ Bước 2: Vô hiệu hóa chế độ Client Secret (Generate client secret = False) do ứng dụng Web Frontend / SPA không lưu trữ bí mật an toàn trên client.<br>&emsp;+ Bước 3: Bật các luồng xác thực cấp phép an toàn hỗ trợ cho ứng dụng giao diện. | 16/07/2026 | 16/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Thử nghiệm luồng Đăng ký và Xác thực mã OTP thời gian thực trên môi trường Sandbox.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Thực hiện cuộc gọi API đăng ký tài khoản mới đính kèm thông tin Email và Mật khẩu thử nghiệm.<br>&emsp;+ Bước 2: Kiểm tra hòm thư Email tiếp nhận mã xác thực OTP 6 chữ số.<br>&emsp;+ Bước 3: Thực hiện gọi API xác nhận mã OTP vừa nhận để chuyển trạng thái tài khoản từ chưa kích hoạt sang đã xác thực chính thức. | 17/07/2026 | 17/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Rà soát các thiết lập an toàn bảo mật trên Cognito User Pool và trích xuất cấu hình tích hợp.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Kiểm tra lại các thuộc tính cấu hình bảo mật trên AWS Console, vô hiệu hóa các luồng xác thực thừa không sử dụng.<br>&emsp;+ Bước 2: Trích xuất các tham số cấu hình quan trọng: User Pool ID, App Client ID và AWS Region.<br>&emsp;+ Bước 3: Lưu trữ bộ thông số vào tệp biến môi trường `.env` sẵn sàng cho việc tích hợp vào Backend FastAPI ở Tuần 5. | 18/07/2026 | 18/07/2026 | |

### Kết quả đạt được:
* Khởi tạo và cấu hình thành công Amazon Cognito User Pool cho bài toán xác thực người dùng tập trung.
* Luồng phát hành và gửi mã OTP xác thực qua Email vận hành ổn định và chính xác.
* Chuẩn bị đầy đủ các thông số tích hợp sẵn sàng kết nối với Backend FastAPI ở tuần tiếp theo.
