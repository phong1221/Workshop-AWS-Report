---
title: "Worklog Tuần 8: Kiểm thử tổng thể, Đóng gói Báo cáo & Dọn dẹp tài nguyên"
date: 2024-01-01
weight: 8
chapter: false
pre: " <b> 1.8. </b> "
---

### Mục tiêu:
* Thực hiện kiểm thử toàn diện End-to-End (E2E) các dịch vụ hạ tầng đã triển khai (S3, Cognito, DynamoDB).
* Tổng hợp, biên soạn và đóng gói hoàn thiện nội dung báo cáo đồ án.
* Xây dựng kịch bản hướng dẫn dọn dẹp tài nguyên hạ tầng đám mây để tránh phát sinh chi phí.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Tìm hiểu lý thuyết: Quy trình kiểm thử toàn diện End-to-End (E2E) trên môi trường ứng dụng Serverless.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Khởi chạy bộ kịch bản kiểm thử tự động End-to-End toàn hệ thống.<br>&emsp;+ Bước 2: Mô phỏng nhiều phiên người dùng đồng thời thực hiện thao tác trên hệ thống.<br>&emsp;+ Bước 3: Kiểm tra độ ổn định kết nối giữa kho S3, trung tâm xác thực Cognito và CSDL DynamoDB. | 10/08/2026 | 10/08/2026 | |
| - Tìm hiểu lý thuyết: Tiêu chí rà soát chỉ số hiệu năng và cấu hình an toàn bảo mật trên quản trị AWS.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Đăng nhập AWS Console rà soát lại toàn bộ cấu hình an toàn của các dịch vụ hạ tầng.<br>&emsp;+ Bước 2: Kiểm tra trạng thái mã hóa dữ liệu S3/DynamoDB và chính sách mật khẩu Cognito.<br>&emsp;+ Bước 3: Xác nhận 100% tài nguyên đám mây đều đáp ứng tiêu chuẩn an toàn bảo mật. | 11/08/2026 | 11/08/2026 | |
| - Tìm hiểu lý thuyết: Quy chuẩn biên soạn tài liệu báo cáo thực tập trên hệ thống Hugo.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Biên soạn chi tiết nội dung các trang Nhật ký công việc từ Tuần 1 đến Tuần 8.<br>&emsp;+ Bước 2: Cập nhật bộ mã nguồn trang báo cáo Hugo với định dạng hiển thị danh sách rõ ràng.<br>&emsp;+ Bước 3: Đảm bảo tính nhất quán dữ liệu giữa phiên bản Tiếng Việt và Tiếng Anh. | 12/08/2026 | 12/08/2026 | |
| - Tìm hiểu lý thuyết: Nguyên tắc dọn dẹp tài nguyên đám mây an toàn sau khi hoàn thành báo cáo.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Biên soạn tài liệu Hướng dẫn Quy trình Dọn dẹp Tài nguyên đám mây (Cleanup Guide).<br>&emsp;+ Bước 2: Liệt kê các bước xóa dữ liệu kho S3, xóa Cognito User Pool và CSDL DynamoDB.<br>&emsp;+ Bước 3: Đảm bảo dọn dẹp hạ tầng an toàn sau báo cáo, ngăn ngừa chi phí phát sinh ngoài ý muốn. | 13/08/2026 | 13/08/2026 | |
| - Tìm hiểu: Kiểm tra chất lượng hiển thị và liên kết của trang web báo cáo đồ án.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Khởi chạy máy chủ báo cáo Hugo địa phương để kiểm tra giao diện tổng thể.<br>&emsp;+ Bước 2: Rà soát toàn bộ đường dẫn liên kết, tài liệu tham khảo và hình ảnh hiển thị.<br>&emsp;+ Bước 3: Hoàn tất đợt thực tập đúng tiến độ và sẵn sàng cho buổi báo cáo chính thức. | 14/08/2026 | 14/08/2026 | |

### Kết quả đạt được:
* Hệ thống hoàn thành 100% kiểm thử tính năng và bảo mật đối với các dịch vụ S3, Cognito và DynamoDB.
* Đóng gói hoàn chỉnh nội dung báo cáo đồ án với bố cục khoa học, chi tiết.
* Xây dựng kịch bản dọn dẹp hạ tầng an toàn phục vụ công tác quản lý chi phí sau báo cáo.
