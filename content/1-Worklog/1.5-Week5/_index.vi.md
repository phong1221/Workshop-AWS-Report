---
title: "Nhật ký Tuần 5: Biên soạn báo cáo đồ án"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Mục tiêu:
* Tập trung tổng hợp tài liệu, biên soạn và hoàn thiện các phần báo cáo đồ án cho Workshop kiến trúc Serverless AWS.
* Biên soạn chi tiết các mục nội dung: Mục 5.1.5 (Giao diện & Chức năng hệ thống), Mục 5.4.1 (Cognito User Pool), Mục 5.4.2 (DynamoDB Database), Mục 5.4.3 (S3 Document Storage) và Mục 5.3.2 (Static Web Hosting).
* Rà soát chất lượng nội dung báo cáo và thống nhất tài liệu giữa các thành viên trong nhóm.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Biên soạn nội dung báo cáo **Mục 5.1.5 (Giao diện & Chức năng hệ thống - UI Function)**.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Mô tả chi tiết trải nghiệm người dùng UI/UX, luồng giao diện Đăng ký, Xác nhận OTP Email, Đăng nhập và Trang chủ quản lý tài liệu.<br>&emsp;+ Bước 2: Chụp ảnh màn hình giao diện ứng dụng Web thực tế và chèn chú thích sơ đồ tương tác UI vào bài báo cáo.<br>&emsp;+ Bước 3: Rà soát định dạng hiển thị Markdown đảm bảo cấu trúc trang chuẩn hóa trên hệ thống Hugo. | 20/07/2026 | 20/07/2026 | |
| - Biên soạn nội dung báo cáo **Mục 5.4.1 (Khởi tạo & Cấu hình Amazon Cognito User Pool)**.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Trình bày quy trình cấu hình trung tâm xác thực định danh Amazon Cognito User Pool trên AWS Management Console.<br>&emsp;+ Bước 2: Viết chi tiết các bước thiết lập thuộc tính người dùng, quy tắc mật khẩu tối thiểu 8 ký tự, mẫu Email OTP 6 chữ số và tạo App Client không dùng Client Secret.<br>&emsp;+ Bước 3: Đính kèm sơ đồ luồng xác thực JWT Tokens (Access Token, ID Token, Refresh Token) vào nội dung báo cáo. | 21/07/2026 | 21/07/2026 | |
| - Biên soạn nội dung báo cáo **Mục 5.4.2 (Khởi tạo & Cấu hình cơ sở dữ liệu Amazon DynamoDB)**.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Trình bày lý thuyết và các bước triển khai tạo bảng cơ sở dữ liệu người dùng trên dịch vụ NoSQL Amazon DynamoDB.<br>&emsp;+ Bước 2: Giải thích chi tiết lựa chọn Partition Key định danh người dùng tối ưu phân bổ dữ liệu, chế độ quản lý dung lượng On-Demand mode (Pay-per-request) tối ưu chi phí.<br>&emsp;+ Bước 3: Tài liệu hóa các cấu hình an toàn: mã hóa ở trạng thái nghỉ Encryption at Rest (AWS Owned Key) và tính năng tự động sao lưu PITR. | 22/07/2026 | 22/07/2026 | |
| - Biên soạn nội dung báo cáo **Mục 5.4.3 (Khởi tạo & Cấu hình Amazon S3 cho lưu trữ tài liệu)**.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Viết chi tiết quy trình khởi tạo kho lưu trữ S3 Backend tại AWS Region được chọn.<br>&emsp;+ Bước 2: Mô tả quy hoạch cây thư mục chứa tài liệu đính kèm, thư mục chứa ảnh đại diện, thư mục tệp tạm, cờ mã hóa mặc định SSE-S3 AES-256 và chính sách cô lập Block Public Access.<br>&emsp;+ Bước 3: Trình bày cơ chế sinh và tải tệp an toàn thông qua liên kết tạm thời Presigned URL thời hạn 900 giây. | 23/07/2026 | 23/07/2026 | |
| - Biên soạn nội dung báo cáo **Mục 5.3.2 (Triển khai lưu trữ Static Website trên Amazon S3)**.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Trình bày các bước kích hoạt tính năng Static Web Hosting cho S3 Bucket giao diện Frontend.<br>&emsp;+ Bước 2: Hướng dẫn cấu hình trang chủ Index Document, trang thông báo lỗi Error Document và bản quy tắc CORS cấp phép Cross-Domain Requests.<br>&emsp;+ Bước 3: Kiểm tra định dạng hiển thị các đoạn mã lệnh (Code snippets) và hình ảnh minh họa trong bài viết. | 24/07/2026 | 24/07/2026 | |
| - **Họp nhóm:** Đánh giá tổng thể hệ thống, review toàn bộ mã nguồn và rà soát lỗi trong bài báo cáo giữa các thành viên.<br>- **Nội dung họp chi tiết:**<br>&emsp;+ Họp rà soát kỹ lưỡng toàn bộ các phần nội dung báo cáo đã biên soạn (5.1.5, 5.4.1, 5.4.2, 5.4.3, 5.3.2).<br>&emsp;+ Đóng góp ý kiến chỉnh sửa thuật ngữ kỹ thuật, định dạng Markdown và đường dẫn liên kết hình ảnh.<br>&emsp;+ Thống nhất kế hoạch triển khai công tác kiểm thử công nghệ và toàn bộ hệ thống dự án ở Tuần 6. | 25/07/2026 | 25/07/2026 | |

### Kết quả đạt được:
* Hoàn thành xuất sắc việc biên soạn nội dung báo cáo đồ án cho 5 mục quan trọng: 5.1.5, 5.4.1, 5.4.2, 5.4.3 và 5.3.2.
* Hồ sơ báo cáo đạt chất lượng cao về mặt lý thuyết, các bước hướng dẫn triển khai thực hành và hình ảnh minh họa.
* Toàn đội thống nhất nội dung báo cáo, sẵn sàng bước vào giai đoạn kiểm thử toàn diện ở Tuần 6.
