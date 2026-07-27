---
title: "Worklog Tuần 1: Tìm hiểu công nghệ & Hạ tầng AWS Serverless"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Mục tiêu:
* Tìm hiểu lý thuyết tổng quan về mô hình kiến trúc điện toán Serverless trên đám mây AWS.
* Nghiên cứu chi tiết nguyên lý hoạt động của 3 dịch vụ hạ tầng AWS cốt lõi được triển khai trong đồ án: Amazon S3, Amazon Cognito và Amazon DynamoDB.
* Phân tích luồng nghiệp vụ xử lý dữ liệu và môi trường ứng dụng web.

### Các công việc đã thực hiện:

| Công việc | Ngày bắt đầu | Ngày kết thúc | Tài liệu tham khảo |
| --- | --- | --- | --- |
| - Nghiên cứu lý thuyết tổng quan về điện toán máy chủ Serverless trên hạ tầng đám mây AWS.<br>- Phân tích ưu điểm tự động mở rộng quy mô theo lưu lượng truy cập thực tế.<br>- Đánh giá mô hình tính phí theo mức độ sử dụng và khả năng giảm thiểu gánh nặng quản trị máy chủ. | 22/06/2026 | 22/06/2026 | |
| - Tìm hiểu chi tiết dịch vụ lưu trữ đối tượng Amazon S3.<br>- Nghiên cứu mô hình tổ chức dữ liệu theo kho lưu trữ và các chính sách phân quyền an toàn.<br>- Tìm hiểu tính năng mã hóa dữ liệu, chặn truy cập công khai và quy tắc chia sẻ tài nguyên giữa các nguồn (CORS). | 23/06/2026 | 23/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Tìm hiểu dịch vụ quản lý định danh người dùng Amazon Cognito User Pools.<br>- Nghiên cứu luồng xác thực tài khoản qua chuỗi mã xác thực OTP gửi về Email.<br>- Tìm hiểu quy tắc bảo mật mật khẩu và quy trình phát hành, kiểm tra mã thông báo JWT. | 24/06/2026 | 24/06/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Nghiên cứu nguyên lý hoạt động của cơ sở dữ liệu NoSQL Amazon DynamoDB.<br>- Tìm hiểu cơ chế phân tán dữ liệu dựa trên khóa phân vùng (Partition Key).<br>- Nghiên cứu phương thức quản lý dung lượng theo yêu cầu (On-Demand) và tư duy thiết kế dữ liệu NoSQL. | 25/06/2026 | 25/06/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Tìm hiểu giải pháp đóng gói ứng dụng xử lý Backend bằng công nghệ container Docker.<br>- Nghiên cứu tích hợp framework FastAPI để vận hành trên môi trường Serverless.<br>- Đánh giá khả năng đóng gói đồng nhất môi trường và mở rộng linh hoạt. | 26/06/2026 | 26/06/2026 | |
| - Tổng hợp toàn bộ tài liệu và kết quả nghiên cứu lý thuyết.<br>- Phác thảo sơ đồ mô hình luồng dữ liệu tổng thể cho ứng dụng.<br>- Thống nhất định hướng và kế hoạch triển khai hạ tầng với các thành viên. | 27/06/2026 | 27/06/2026 | |

### Kết quả đạt được:
* Nắm vững kiến thức nền tảng và nguyên lý vận hành của các dịch vụ đám mây cốt lõi (S3, Cognito, DynamoDB) cùng framework xử lý Backend.
* Xác định được mô hình kiến trúc tổng thể và luồng dữ liệu chuẩn hóa cho hệ thống.
* Tuân thủ đúng định hướng: chỉ tập trung nghiên cứu tài liệu lý thuyết, không thực hiện bất kỳ thao tác khởi tạo tài nguyên hạ tầng nào trong tuần đầu tiên.
