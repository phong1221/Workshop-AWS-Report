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
| - Tìm hiểu lý thuyết: Phương thức kết nối giữa ứng dụng Backend xử lý và Amazon Cognito.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Khai báo các tham số định danh Cognito trong tệp cấu hình biến môi trường Backend.<br>&emsp;+ Bước 2: Khởi tạo module kết nối tới dịch vụ xác thực Cognito trên Backend.<br>&emsp;+ Bước 3: Kiểm thử kết nối mạng giữa máy chủ Backend và dịch vụ Cognito. | 20/07/2026 | 20/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Tìm hiểu lý thuyết: Luồng nghiệp vụ Đăng ký tài khoản người dùng từ giao diện.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xây dựng luồng tiếp nhận thông tin đăng ký (Email, Mật khẩu, Họ tên) trên Backend.<br>&emsp;+ Bước 2: Chuyển tiếp yêu cầu đăng ký tài khoản tới dịch vụ Cognito.<br>&emsp;+ Bước 3: Trả về trạng thái chờ nhập mã OTP kích hoạt cho phía giao diện. | 21/07/2026 | 21/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Tìm hiểu lý thuyết: Luồng nghiệp vụ Xác nhận mã OTP kích hoạt tài khoản.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xây dựng luồng tiếp nhận mã OTP từ người dùng trên Backend.<br>&emsp;+ Bước 2: Chuyển mã OTP tới Cognito để đối chiếu kiểm tra tính hợp lệ.<br>&emsp;+ Bước 3: Kích hoạt tài khoản chính thức và trả về thông báo thành công cho client. | 22/07/2026 | 22/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Tìm hiểu lý thuyết: Luồng nghiệp vụ Đăng nhập và cấu trúc mã thông báo bảo mật JWT Token.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xây dựng luồng tiếp nhận Email và Mật khẩu đăng nhập trên Backend.<br>&emsp;+ Bước 2: Gửi yêu cầu xác thực thông tin tài khoản tới dịch vụ Cognito.<br>&emsp;+ Bước 3: Tiếp nhận bộ mã thông báo JWT Token từ Cognito và cấp phát về cho giao diện. | 23/07/2026 | 23/07/2026 | [Cognito Tokens Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/amazon-cognito-user-pools-using-tokens-verifying-a-jwt.html) |
| - Tìm hiểu lý thuyết: Cơ chế giải mã và kiểm tra mã thông báo bảo mật JWT Token.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xây dựng lớp Middleware tự động chặn và kiểm tra chuỗi JWT Token trong HTTP Header.<br>&emsp;+ Bước 2: Xác minh chữ ký mã hóa của Token tại điểm kiểm tra công khai của Cognito.<br>&emsp;+ Bước 3: Trích xuất thông tin định danh người dùng để bảo vệ các API riêng tư. | 24/07/2026 | 24/07/2026 | [Cognito Tokens Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/amazon-cognito-user-pools-using-tokens-verifying-a-jwt.html) |
| - Họp nhóm: Đánh giá tổng thể hệ thống, review toàn bộ mã nguồn và rà soát lỗi trong bài báo cáo giữa các thành viên. | 25/07/2026 | 25/07/2026 | |

### Kết quả đạt được:
* Tích hợp thành công chuỗi API xác thực người dùng kết nối trực tiếp với Amazon Cognito.
* Luồng nghiệp vụ Đăng ký, Xác nhận OTP và Đăng nhập vận hành trơn tru.
* Lớp bảo vệ Middleware hoạt động hiệu quả, đảm bảo an toàn cho các API của ứng dụng.
