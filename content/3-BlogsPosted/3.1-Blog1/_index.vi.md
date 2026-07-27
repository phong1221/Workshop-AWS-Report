---
title: "Blog 1: RAG Đa Phân Quyền Bảo Mật"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

![Sơ đồ kiến trúc Secure Multi-Tenant RAG với Amazon Bedrock và Amazon Verified Permissions](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2026/07/09/secure-rag-featured-image.png)

### 1. Mục Đích Hệ Thống Và Bài Toán Triển Khai
Trong môi trường tổ chức thực tế, yêu cầu truy cập dữ liệu thường phức tạp: nhân viên thông thường chỉ được phép tiếp cận tài liệu nội bộ của bộ phận mình, trong khi các cấp quản lý hoặc ban điều hành lại cần quyền truy cập chéo để tổng hợp thông tin từ nhiều phòng ban khác nhau.

Hệ thống RAG (Retrieval-Augmented Generation) là một giải pháp lý tưởng để cân bằng giữa hiệu năng phân tích tài liệu và chi phí. Tuy nhiên, nếu áp dụng phương pháp truyền thống là xây dựng cho mỗi phòng ban một Hệ thống tri thức (Knowledge Base) riêng biệt, tổ chức sẽ phải đối mặt với việc nhân bản hạ tầng, kéo theo chi phí lưu trữ và gánh nặng quản trị hệ thống tăng cao. Do đó, bài toán đặt ra là cần xây dựng một phiên bản hệ thống tri thức dùng chung duy nhất nhưng vẫn phải có cơ chế phân quyền truy cập cực kỳ nghiêm ngặt và chính xác.

---

### 2. Giải Pháp: Cô Lập Dữ Liệu Ở Mức Độ Logic
Thay vì chia cắt vật lý, hệ thống này áp dụng phương pháp cô lập ở cấp độ logic thông qua bộ lọc metadata (siêu dữ liệu) ngay tại thời điểm truy xuất.
* Tài nguyên vector bên dưới vẫn là một cơ sở dữ liệu dùng chung.
* Dựa vào thông tin người dùng, hệ thống sẽ giới hạn phạm vi tìm kiếm tài liệu. Đây là giải pháp hoàn hảo cho việc phân quyền nội bộ trong cùng một tổ chức.

> ⚠️ **Lưu ý kỹ thuật:** Giải pháp cô lập logic này không dùng để thay thế cho việc cô lập hạ tầng vật lý bằng quyền IAM (vốn là bắt buộc nếu áp dụng cho mô hình SaaS với nhiều khách hàng hoặc tổ chức hoàn toàn độc lập).

---

### 3. Kiến Trúc Bảo Mật Chiều Sâu Hai Lớp (Defense-in-Depth)
Hệ thống được thiết kế với hai ranh giới ủy quyền hoạt động hoàn toàn độc lập và tuân thủ nghiêm ngặt nguyên tắc từ chối theo mặc định (default deny):

* **Lớp 1: Bảo mật cổng giao tiếp (API Gateway)**
  Khi có một yêu cầu truy vấn gửi đến API Gateway, một hàm Lambda Authorizer sẽ đứng ra tiếp nhận và giải mã token JWT do Amazon Cognito cấp. Authorizer này sau đó sẽ gọi dịch vụ Amazon Verified Permissions để đánh giá các chính sách Cedar (Cedar policies) nhằm xác định xem người dùng này có quyền thực thi lệnh gọi API hay không. Nếu dịch vụ Verified Permissions không phản hồi hoặc người dùng không có quyền, yêu cầu sẽ bị chặn ngay lập tức tại cổng và trả về mã lỗi HTTP 403.

* **Lớp 2: Kiểm soát dữ liệu truy xuất (Middleware Lambda)**
  Nếu vượt qua lớp 1, yêu cầu sẽ đi vào một Middleware Lambda. Tại đây, hệ thống thực hiện cuộc đánh giá thứ hai, cụ thể hơn về mặt tài nguyên: *Nhóm người dùng này được phép đọc những tài liệu thuộc bộ phận nào?* Kết quả đánh giá từ chính sách Cedar sẽ được hệ thống biên dịch thành một bộ lọc metadata dạng cấu trúc (Ví dụ: `department = dept-a`). Bộ lọc này sau đó được đẩy vào payload của lệnh gọi API `RetrieveAndGenerate` đến Amazon Bedrock. Nhờ vậy, quá trình tìm kiếm vector sẽ lọc bỏ hoàn toàn các tài liệu không hợp lệ **trước khi** ngữ cảnh được đưa vào cho Mô hình ngôn ngữ lớn (LLM) xử lý.

---

### 4. Luồng Nạp Dữ Liệu Tự Động Và Gắn Metadata An Toàn
Để bộ lọc ở Lớp 2 hoạt động chính xác, mọi tài liệu đưa vào hệ thống phải được dán nhãn chuẩn xác. Quá trình này được tự động hóa qua hai pha nhằm tránh lỗi con người:
* **Pha 1 (Xử lý hướng sự kiện - Event-driven):** Khi có tài liệu mới được tải lên một thư mục (đại diện cho phòng ban) trên Amazon S3, sự kiện này sẽ kích hoạt EventBridge, đẩy thông báo qua SQS và gọi một hàm Lambda. Hàm này sẽ tự động tạo ra một tệp cấu hình `.metadata.json` chứa thông tin phân quyền của phòng ban đó, đặt ngay cạnh tệp tài liệu gốc.
* **Pha 2 (Xử lý theo lịch trình - Scheduled):** Cứ mỗi 5 phút, một EventBridge Scheduler sẽ kích hoạt một hàm Lambda khác để gọi API `StartIngestionJob` của Amazon Bedrock, tiến hành số hóa tài liệu thành vector và đính kèm metadata. **Cơ chế an toàn:** Hàm này được lập trình để quét và tự động bỏ qua (skip) bất kỳ tài liệu nào chưa có tệp `.metadata.json`, đảm bảo không có tài liệu nào lọt vào hệ thống mà không có nhãn phân quyền.

---

### 5. Kiểm Duyệt Phản Hồi Với Amazon Bedrock Guardrails
Ngoài việc bảo vệ dữ liệu đầu vào, hệ thống còn thiết lập chốt chặn đầu ra thông qua tính năng Guardrails của Amazon Bedrock:
* **Tính trung thực của ngữ cảnh (Contextual Grounding):** Guardrails sẽ đối chiếu câu trả lời của AI với các tài liệu đã được trích xuất hợp lệ, giúp hạn chế triệt để hiện tượng AI "ảo giác" (tự bịa ra thông tin không có trong tài liệu của bộ phận).
* **Kiểm soát nội dung (Content Filtering):** Tự động lọc, che dấu hoặc chặn các phản hồi chứa thông tin độc hại, không phù hợp, giúp doanh nghiệp duy trì tiêu chuẩn giao tiếp an toàn.

---

### Tài Liệu Tham Khảo
* **Bài viết gốc trên AWS Architecture Blog:** [Secure multi-tenant RAG with Amazon Bedrock and Verified Permissions](https://aws.amazon.com/vi/blogs/architecture/secure-multi-tenant-rag-with-amazon-bedrock-and-verified-permissions/)