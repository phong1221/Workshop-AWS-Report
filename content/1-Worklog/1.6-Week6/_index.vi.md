---
title: "Worklog Tuần 6: Nghiên cứu & Triển khai cơ sở dữ liệu Amazon DynamoDB"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Mục tiêu:
* Phân tích nhu cầu lưu trữ dữ liệu người dùng và thiết kế cấu trúc NoSQL cho cơ sở dữ liệu.
* Khởi tạo bảng dữ liệu trên dịch vụ Amazon DynamoDB với phương án tối ưu chi phí và bảo mật.
* Cấu hình chế độ mã hóa dữ liệu và xây dựng các hàm tương tác dữ liệu cơ bản.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Tìm hiểu lý thuyết: Nhu cầu lưu trữ các thuộc tính thông tin hồ sơ người dùng trong ứng dụng.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Soạn thảo nội dung bài Blog 3 (*5 Sai Lầm Kinh Điển Khi Triển Khai Kiến Trúc Serverless*).<br>&emsp;+ Bước 2: Xuất bản bài Blog 3 lên diễn đàn cộng đồng AWS Study Group VN.<br>&emsp;+ Bước 3: Thiết kế mô hình dữ liệu chi tiết cho thông tin hồ sơ cá nhân người dùng. | 27/07/2026 | 27/07/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) & Blog 3 |
| - Tìm hiểu lý thuyết: Cấu trúc mô hình dữ liệu NoSQL cho hồ sơ người dùng và nguyên tắc chọn khóa phân vùng.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Xác định sơ đồ lưu trữ dữ liệu NoSQL trên CSDL Amazon DynamoDB.<br>&emsp;+ Bước 2: Chọn thuộc tính định danh người dùng làm khóa phân vùng (Partition Key) chính.<br>&emsp;+ Bước 3: Quy hoạch các thuộc tính thông tin đi kèm (Họ tên, SĐT, đường dẫn Avatar). | 28/07/2026 | 28/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Tìm hiểu lý thuyết: Phương thức quản lý dung lượng theo yêu cầu (On-Demand Mode) trên Amazon DynamoDB.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Khởi tạo vùng lưu trữ cơ sở dữ liệu hồ sơ người dùng trên AWS Console.<br>&emsp;+ Bước 2: Thiết lập chế độ quản lý dung lượng On-Demand để tự động mở rộng theo lưu lượng truy cập.<br>&emsp;+ Bước 3: Tối ưu chi phí chỉ tính phí theo số lượng yêu cầu đọc/ghi thực tế. | 29/07/2026 | 29/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Tìm hiểu lý thuyết: Cơ chế mã hóa dữ liệu ở trạng thái nghỉ bảo vệ cơ sở dữ liệu.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Truy cập mục cấu hình an toàn trên giao diện quản trị CSDL DynamoDB.<br>&emsp;+ Bước 2: Bật tính năng mã hóa dữ liệu ở trạng thái nghỉ (Encryption at Rest).<br>&emsp;+ Bước 3: Xác nhận trạng thái mã hóa bảo vệ toàn bộ dữ liệu hồ sơ người dùng lưu trữ. | 30/07/2026 | 30/07/2026 | [DynamoDB Encryption at Rest](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/EncryptionAtRest.html) |
| - Tìm hiểu lý thuyết: Xây dựng module xử lý dữ liệu giao tiếp với Amazon DynamoDB.<br>- **Thực hành:**<br>&emsp;+ Bước 1: Viết module kết nối ứng dụng Backend với CSDL DynamoDB.<br>&emsp;+ Bước 2: Xây dựng các luồng xử lý: khởi tạo hồ sơ, đọc thông tin và cập nhật thuộc tính.<br>&emsp;+ Bước 3: Thêm các cơ chế xử lý ngoại lệ khi kết nối hoặc truy vấn dữ liệu thất bại. | 31/07/2026 | 31/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Họp nhóm: Đánh giá hiệu năng CSDL DynamoDB, tổng kết nghiệm thu đồ án SmartDocAI và sẵn sàng báo cáo hội đồng. | 01/08/2026 | 01/08/2026 | |

### Kết quả đạt được:
* Khởi tạo thành công bảng cơ sở dữ liệu Amazon DynamoDB chuẩn cấu hình mã hóa và tối ưu chi phí.
* Xây dựng xong bộ hàm tương tác dữ liệu sẵn sàng phục vụ cho Backend API.
* Đạt hiệu năng phản hồi đọc/ghi dữ liệu nhanh chóng với độ trễ thấp.
