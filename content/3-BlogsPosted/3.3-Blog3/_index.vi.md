---
title: "Blog 3: 5 Sai Lầm Khi Triển Khai Serverless"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3.3. </b> "
---

![Sơ đồ so sánh Monolith vs Serverless Microservices với AWS Lambda](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/05/27/Example-1-Monolitic-VS-Microservice-approach-1260x554.png)

### 1. Tổng Quan Về Kiến Trúc Serverless Trên AWS Lambda
Serverless (Điện toán máy chủ ẩn) với trọng tâm là dịch vụ **AWS Lambda** đang trở thành xu hướng hàng đầu nhờ khả năng tự động mở rộng quy mô (Auto-scaling), tối ưu chi phí theo lượng truy cập thực tế (Pay-per-use) và hoàn toàn miễn trừ gánh nặng vận hành máy chủ.

Tuy nhiên, khi chuyển đổi từ kiến trúc máy chủ truyền thống (Monolith trên EC2/VPS) sang Serverless, các kỹ sư thường vô tình mang theo các tư duy lập trình cũ, dẫn đến các sai lầm kiến trúc (Anti-patterns) làm giảm hiệu năng và gây lãng phí chi phí nghiêm trọng.

---

### 2. Chi Tiết 5 Sai Lầm Kinh Điển & Giải Pháp Khắc phục

#### ❌ Sai Lầm 1: Xây Dựng Monolithic Lambda ("Lambda-lith")
* **Vấn đề:** Đóng gói toàn bộ mã nguồn ứng dụng Web vào trong đúng 1 hàm Lambda duy nhất. Điều này làm tăng kích thước tệp Deployment Package, tăng thời gian Cold Start, và làm vi phạm nguyên tắc phân quyền tối thiểu (Least Privilege).
* **Giải pháp:** Tách nhỏ ứng dụng thành các Microservices Serverless độc lập. Mỗi hàm Lambda chỉ đảm nhận đúng 1 trách nhiệm duy nhất (Single Responsibility Principle).

#### ❌ Sai Lầm 2: Gọi Trực Tiếp Giữa Các Hàm Lambda (Lambda Calling Lambda)
* **Vấn đề:** Hàm Lambda A gọi đồng bộ (Synchronous) sang Hàm Lambda B và ngồi chờ phản hồi. Việc này khiến bạn phải trả tiền nhân đôi cho thời gian chờ (Double billing) và dễ gây sụp đổ dây chuyền (Cascading Failure).
* **Giải pháp:** Áp dụng kiến trúc hướng sự kiện (Event-Driven Architecture) với **Amazon SQS**, **Amazon SNS** hoặc **AWS Step Functions** để xử lý bất đồng bộ.

#### ❌ Sai Lầm 3: Quản Lý Kết Nối Cơ Sở Dữ Liệu Quan Hệ Quá Tải (Relational DB Connection Exhaustion)
* **Vấn đề:** Mỗi lần Lambda mở rộng quy mô ra hàng trăm instances, mỗi instance mở 1 kết nối mới tới cơ sở dữ liệu quan hệ (RDS/MySQL/PostgreSQL), dẫn đến cạn kệt Pool kết nối và làm sụp đổ DB.
* **Giải pháp:** Sử dụng cơ sở dữ liệu NoSQL **Amazon DynamoDB** (vốn được tối ưu hóa cho Serverless) hoặc dùng **Amazon RDS Proxy** để quản lý và tái sử dụng connection pool.

#### ❌ Sai Lầm 4: Bỏ Qua Việc Tối Ưu Cấu Hình Bộ Nhớ (Lambda Power Tuning)
* **Vấn đề:** Cấu hình bộ nhớ (RAM) mặc định cho Lambda mà không đo lường thực tế. Cấu hình thiếu RAM khiến Lambda chạy chậm và đắt hơn, còn quá nhiều RAM gây lãng phí.
* **Giải pháp:** Sử dụng công cụ mã nguồn mở **AWS Lambda Power Tuning** để chạy thử nghiệm tự động, tìm ra điểm cân bằng tối ưu giữa hiệu năng (Duration) và chi phí (Cost).

#### ❌ Sai Lầm 5: Thiếu Cơ Chế Xử Lý Lỗi Và Retry Trong Xử Lý Bất Đồng Bộ
* **Vấn đề:** Không cấu hình Dead Letter Queue (DLQ) hoặc Retry Policy, khiến cho các sự kiện bị lỗi bị mất vĩnh viễn mà không có dấu vết truy vết.
* **Giải pháp:** Cấu hình **DLQ (Amazon SQS)**, **Lambda Destinations** hoặc sử dụng **AWS Step Functions** để bắt lỗi, lưu trữ tệp tin lỗi và thử lại tự động (Automatic Retry).

---

### Tài Liệu Tham Khảo
* **Bài viết gốc trên AWS Architecture Blog:** [Issues to Avoid When Implementing Serverless Architecture with AWS Lambda](https://aws.amazon.com/vi/blogs/architecture/mistakes-to-avoid-when-implementing-serverless-architecture-with-lambda/)