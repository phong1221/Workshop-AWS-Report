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
| - Phân tích yêu cầu lưu trữ các thuộc tính thông tin hồ sơ người dùng trong ứng dụng.<br>- Liệt kê các thông tin cần quản lý (mã định danh, email, họ tên, số điện thoại, ảnh đại diện).<br>- Xác định các mốc thời gian tạo và cập nhật dữ liệu. | 27/07/2026 | 27/07/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| - Thiết kế cấu trúc mô hình dữ liệu NoSQL cho bảng hồ sơ người dùng.<br>- Lựa chọn thuộc tính khóa phân vùng (Partition Key) phù hợp.<br>- Đảm bảo dữ liệu được phân bổ đồng đều trên các máy chủ lưu trữ. | 28/07/2026 | 28/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Thực hiện khởi tạo bảng dữ liệu trên dịch vụ Amazon DynamoDB.<br>- Thiết lập chế độ quản lý dung lượng theo yêu cầu (On-Demand).<br>- Tối ưu chi phí vận hành chỉ tính phí khi có yêu cầu truy xuất. | 29/07/2026 | 29/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Cấu hình tính năng mã hóa dữ liệu ở trạng thái nghỉ (Encryption at rest).<br>- Áp dụng khóa mã hóa an toàn cho bảng cơ sở dữ liệu DynamoDB.<br>- Đảm bảo an toàn tuyệt đối cho thông tin hồ sơ người dùng lưu trữ. | 30/07/2026 | 30/07/2026 | [DynamoDB Encryption at Rest](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/EncryptionAtRest.html) |
| - Lập trình module xử lý dữ liệu đệm tương tác với Amazon DynamoDB.<br>- Xây dựng các hàm trợ giúp thêm mới hồ sơ khi đăng ký thành công.<br>- Xây dựng các hàm truy vấn và cập nhật trường thông tin cá nhân. | 31/07/2026 | 31/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Chạy script kiểm thử thêm và truy xuất dữ liệu mẫu trên DynamoDB.<br>- Theo dõi và kiểm tra chỉ số độ trễ phản hồi của cơ sở dữ liệu.<br>- Xác nhận hiệu năng đọc/ghi dữ liệu đạt độ trễ thấp và ổn định. | 01/08/2026 | 01/08/2026 | |

### Kết quả đạt được:
* Khởi tạo thành công bảng cơ sở dữ liệu Amazon DynamoDB chuẩn cấu hình mã hóa và tối ưu chi phí.
* Xây dựng xong bộ hàm tương tác dữ liệu sẵn sàng phục vụ cho Backend API.
* Đạt hiệu năng phản hồi đọc/ghi dữ liệu nhanh chóng với độ trễ thấp.
