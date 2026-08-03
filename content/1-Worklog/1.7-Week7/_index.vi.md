---
title: "Nhật ký Tuần 7: Quay Video Demo & Hoàn thiện nốt các phần báo cáo còn thiếu"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Mục tiêu:
* Xây dựng kịch bản và tiến hành quay video demo minh họa toàn bộ hoạt động của hệ thống SmartDocAI.
* Rà soát, biên soạn bổ sung và hoàn thiện nốt các phần tài liệu nội dung báo cáo thực tập còn thiếu.
* Đóng gói toàn bộ bài báo cáo đồ án trên trang web Hugo và kiểm tra chất lượng hiển thị cuối cùng.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Xây dựng kịch bản chi tiết (Script & Outline) phục vụ công tác quay Video Demo hệ thống.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Phác thảo kịch bản quay video demo gồm 4 phân đoạn chính: Giới thiệu tổng quan kiến trúc Serverless AWS -> Luồng Đăng ký & Kích hoạt tài khoản qua Email OTP với Cognito -> Quản lý Hồ sơ & Tải ảnh Avatar trực tiếp lên S3 qua Presigned URL -> Lưu trữ và đồng bộ dữ liệu NoSQL DynamoDB.<br>&emsp;+ Bước 2: Chuẩn bị môi trường dữ liệu thử nghiệm chuẩn và kiểm tra kết nối thiết bị thu âm, quay màn hình chất lượng cao.<br>&emsp;+ Bước 3: Duyệt kịch bản quay video với các thành viên trong nhóm để đảm bảo truyền tải đầy đủ hàm lượng kỹ thuật. | 03/08/2026 | 03/08/2026 | |
| - Tiến hành quay hình thực tế các phân đoạn tính năng cho Video Demo hệ thống.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Thao tác thực tế trên giao diện ứng dụng Web: thực hiện các bước Đăng ký, nhập mã OTP gửi về Email, Đăng nhập và trải nghiệm các tính năng quản lý hồ sơ.<br>&emsp;+ Bước 2: Thực hiện thao tác tải ảnh đại diện Avatar lên S3 qua Presigned URL và mở giao diện AWS Management Console minh họa trực quan các đối tượng tệp trên S3 Bucket và bản ghi dữ liệu trên bảng DynamoDB.<br>&emsp;+ Bước 3: Kiểm tra chất lượng hình ảnh, độ phân giải sắc nét và âm thanh thuyết minh của các đoạn video đã quay. | 04/08/2026 | 04/08/2026 | |
| - Biên tập và xử lý hậu kỳ hoàn thiện Video Demo sản phẩm.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Thực hiện cắt ghép, chỉnh sửa các phân đoạn video đảm bảo thời lượng tối ưu và mạch lạc.<br>&emsp;+ Bước 2: Chèn các nhãn chú thích kỹ thuật (Callouts & Subtitles) giải thích chi tiết luồng tương tác giữa Web Client, FastAPI Backend, Cognito, S3 và DynamoDB.<br>&emsp;+ Bước 3: Xuất bản video bản hoàn chỉnh định dạng Full HD (1080p) và tải video lên dịch vụ lưu trữ để nhúng vào bài báo cáo. | 05/08/2026 | 05/08/2026 | |
| - Rà soát và hoàn thiện nốt các phần nội dung báo cáo thực tập còn thiếu.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Rà soát toàn bộ các mục báo cáo trên trang web Hugo, đối chiếu với danh mục yêu cầu đồ án.<br>&emsp;+ Bước 2: Biên soạn hoàn thiện nốt các nội dung còn thiếu: bổ sung chi tiết sơ đồ kiến trúc tổng thể, bảng kê khai công cụ, các bài blog đã đăng và phần chia sẻ đóng góp ý kiến.<br>&emsp;+ Bước 3: Chỉnh sửa các lỗi chính tả, chuẩn hóa văn phong kỹ thuật và thống nhất định dạng hiển thị Markdown giữa hai phiên bản Tiếng Việt và Tiếng Anh. | 06/08/2026 | 06/08/2026 | |
| - Đóng gói nội dung báo cáo đồ án và kiểm tra liên kết trên trang báo cáo Hugo.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Khởi chạy máy chủ thử nghiệm Hugo địa phương để rà soát tổng thể toàn bộ trang web.<br>&emsp;+ Bước 2: Kiểm tra tính hoạt động của 100% các đường dẫn liên kết tài liệu tham khảo, liên kết bài viết Blog và nhúng video demo vào trang báo cáo.<br>&emsp;+ Bước 3: Thực hiện lệnh đóng gói trang web báo cáo tĩnh Hugo đảm bảo không phát sinh bất kỳ cảnh báo hoặc lỗi liên kết hỏng. | 07/08/2026 | 07/08/2026 | |
| - Kiểm tra tổng thể cuối cùng và hoàn tất đợt thực tập đúng tiến độ.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Tổng kiểm tra lại toàn bộ hồ sơ báo cáo đồ án SmartDocAI trên cả hai phiên bản giao diện Tiếng Việt và Tiếng Anh.<br>&emsp;+ Bước 2: Xác nhận hoàn tất 100% các hạng mục công việc trong 7 tuần thực tập theo đúng định hướng từ các Mentor AWS.<br>&emsp;+ Bước 3: Sẵn sàng tài liệu báo cáo và video demo phục vụ cho buổi báo cáo chính thức trước hội đồng. | 08/08/2026 | 08/08/2026 | |

### Kết quả đạt được:
* Quay và hoàn thiện video demo sản phẩm chuyên nghiệp, minh họa trực quan luồng vận hành kiến trúc AWS Serverless.
* Hoàn thành nốt 100% các phần nội dung báo cáo còn thiếu với chất lượng cao và trình bày khoa học.
* Trang web báo cáo Hugo được đóng gói hoàn chỉnh, hoạt động trơn tru và sẵn sàng phục vụ cho buổi báo cáo đồ án.
