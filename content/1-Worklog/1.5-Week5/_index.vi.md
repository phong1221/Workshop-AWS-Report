---
title: "Worklog Tuần 5: Triển khai tích hợp Cognito Auth với Backend FastAPI"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu:
* Xây dựng các cổng giao tiếp API cho luồng Đăng ký, Xác nhận OTP và Đăng nhập người dùng.
* Thực hiện giải mã và xác minh tính hợp lệ của mã thông báo JWT phát hành từ Amazon Cognito.
* Triển khai lớp bảo vệ Middleware ngăn chặn các truy cập không hợp lệ vào Backend.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Thiết lập kết nối giữa ứng dụng Backend xử lý với dịch vụ Amazon Cognito.<br>- Sử dụng bộ công cụ phát triển phần mềm chính thức từ AWS SDK.<br>- Chuẩn bị các cấu hình dịch vụ xác thực cho Backend. | 20/07/2026 | 20/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Lập trình API Đăng ký tài khoản tiếp nhận thông tin từ phía giao diện.<br>- Gửi yêu cầu khởi tạo tài khoản người dùng lên dịch vụ Cognito.<br>- Đưa tài khoản vào trạng thái chờ kích hoạt bằng mã OTP. | 21/07/2026 | 21/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Lập trình API Xác nhận mã OTP kiểm tra tính hợp lệ của mã người dùng nhập.<br>- Gọi dịch vụ Cognito đối chiếu mã xác thực nhận qua Email.<br>- Chuyển trạng thái tài khoản sang kích hoạt chính thức khi thành công. | 22/07/2026 | 22/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Lập trình API Đăng nhập tiếp nhận thông tin Email và Mật khẩu.<br>- Gửi yêu cầu xác thực tới dịch vụ Amazon Cognito.<br>- Nhận về và cấp phát bộ chuỗi mã thông báo bảo mật JWT Token. | 23/07/2026 | 23/07/2026 | [Cognito Tokens Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/amazon-cognito-user-pools-using-tokens-verifying-a-jwt.html) |
| - Xây dựng lớp bảo vệ Middleware tự động giải mã và kiểm tra mã thông báo JWT.<br>- Xác minh chữ ký mã thông báo tại điểm kiểm tra công khai của Cognito.<br>- Trích xuất thông tin định danh hợp lệ để bảo vệ các API riêng tư. | 24/07/2026 | 24/07/2026 | [Cognito Tokens Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/amazon-cognito-user-pools-using-tokens-verifying-a-jwt.html) |
| - Thực hiện kiểm thử toàn bộ chuỗi tính năng xác thực người dùng (Đăng ký, OTP, Đăng nhập nhận JWT Token).<br>- Họp nhóm: Đánh giá tổng thể hệ thống, review toàn bộ mã nguồn và rà soát lỗi trong bài báo cáo giữa các thành viên. | 25/07/2026 | 25/07/2026 | |

### Kết quả đạt được:
* Tích hợp thành công chuỗi API xác thực người dùng kết nối trực tiếp với Amazon Cognito.
* Luồng nghiệp vụ Đăng ký, Xác nhận OTP và Đăng nhập vận hành trơn tru.
* Lớp bảo vệ Middleware hoạt động hiệu quả, đảm bảo an toàn cho các API của ứng dụng.
