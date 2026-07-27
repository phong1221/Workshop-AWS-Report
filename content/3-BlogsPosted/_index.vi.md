---
title: "Các bài blogs đã đăng"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Tại đây là danh sách tổng hợp 3 bài blog kỹ thuật về hạ tầng đám mây và kiến trúc serverless trên AWS đã đăng tải trong cộng đồng [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj):

---

### [Blog 1 - Xây Dựng Hệ Thống RAG Đa Phân Quyền Bảo Mật Với Amazon Bedrock Và Amazon Verified Permissions](3.1-Blog1/)

![Sơ đồ kiến trúc Secure Multi-Tenant RAG với Amazon Bedrock](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2026/07/09/secure-rag-featured-image.png)

Blog này giới thiệu giải pháp xây dựng hệ thống RAG (Retrieval-Augmented Generation) dùng chung cho doanh nghiệp kết hợp Amazon Bedrock và Amazon Verified Permissions. Giải pháp áp dụng cơ chế cô lập dữ liệu ở mức độ logic thông qua metadata và kiến trúc bảo mật chiều sâu 2 lớp (Defense-in-Depth) tại API Gateway và Middleware Lambda để đảm bảo phân quyền truy cập tài liệu nghiêm ngặt.

---

### [Blog 2 - Kiến Trúc Cơ Sở Cho Amazon Bedrock Trong Môi Trường AWS Landing Zone](3.2-Blog2/)

![Sơ đồ kiến trúc Amazon Bedrock Baseline Architecture trong AWS Landing Zone](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2025/06/18/ARCHBLOG-1133-image-1-960x630.png)

Blog này trình bày nền tảng kiến trúc cơ sở (baseline architecture) khi triển khai Amazon Bedrock trong môi trường AWS Landing Zone (AWS Control Tower). Giải pháp phân tách môi trường đa tài khoản (multi-account), bảo mật kết nối qua AWS PrivateLink, quản lý định danh IAM Identity Center, và áp dụng quy trình kiểm soát tập trung qua SCPs và CloudWatch/CloudTrail logging.

---

### [Blog 3 - 5 Sai Lầm Kinh Điển Khi Triển Khai Kiến Trúc Serverless Với AWS Lambda](3.3-Blog3/)

![Sơ đồ so sánh Monolith vs Serverless Microservices với AWS Lambda](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/05/27/Example-1-Monolitic-VS-Microservice-approach-1260x554.png)

Blog này tổng hợp 5 sai lầm phổ biến mà các lập trình viên thường mắc phải khi chuyển từ tư duy máy chủ truyền thống (EC2/VPS) sang kiến trúc Serverless hướng sự kiện (Event-Driven) trên AWS Lambda, kèm theo giải pháp khắc phục bằng Amazon SQS, RDS Proxy, AWS Lambda Power Tuning và AWS Step Functions.