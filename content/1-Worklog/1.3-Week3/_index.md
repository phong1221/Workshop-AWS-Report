---
title: "Worklog Week 3: Amazon S3 Deployment for Backend Storage"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Objectives:
* Provision and configure Amazon S3 storage bucket dedicated to Backend assets and user profile avatars.
* Configure data-at-rest encryption, public access block settings, and Cross-Origin Resource Sharing (CORS) rules.
* Perform integration testing of secure file uploads via temporary Presigned URLs.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - Production deployment of official Amazon S3 storage bucket for SmartDocAI Backend.<br>- **Practice & Blog 1 Publishing:**<br>&emsp;+ Step 1: Formally provision production S3 Bucket on AWS Region applying architectural parameters designed in Week 2.<br>&emsp;+ Step 2: Draft technical article **Blog 1** titled: *"Building a Multi-Tenant Secure RAG Architecture on AWS Cloud Infrastructure"* in Markdown.<br>&emsp;+ Step 3: Publish Blog 1 on AWS Study Group VN community platform and receive community feedback. | 06/07/2026 | 06/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) & Blog 1 |
| - Enforce Server-Side Encryption (SSE-S3) rules on the production S3 bucket.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Enable SSE-S3 (AES-256) encryption across production S3 bucket via AWS CLI/Console.<br>&emsp;+ Step 2: Run automation script uploading 50 test sample files (PDF, PNG, JPEG).<br>&emsp;+ Step 3: Inspect object metadata via AWS CLI to verify server-side encryption flags on all objects. | 07/07/2026 | 07/07/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Implement strict data security isolation policies on S3 infrastructure.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Enable Block Public Access configuration at both Bucket and Account levels.<br>&emsp;+ Step 2: Configure tight S3 Bucket Policy granting access exclusively to FastAPI Backend IAM credentials.<br>&emsp;+ Step 3: Conduct security compliance checks via AWS Trusted Advisor and CloudWatch Metrics to verify zero public exposure risks. | 08/07/2026 | 08/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Finalize S3 CORS configuration and publish technical Blog 2.<br>- **Practice & Blog 2 Publishing:**<br>&emsp;+ Step 1: Apply validated CORS policy supporting authorized authentication headers and content types.<br>&emsp;+ Step 2: Draft technical article **Blog 2** titled: *"Foundation Architecture for Amazon Bedrock in AWS Enterprise Landing Zone Environment"*.<br>&emsp;+ Step 3: Publish Blog 2 on AWS Study Group VN community platform. | 09/07/2026 | 09/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) & Blog 2 |
| - Develop Presigned URL integration module in FastAPI Backend application.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Implement S3 storage service in FastAPI providing Presigned URL upload and download methods.<br>&emsp;+ Step 2: Incorporate UUIDv4 random file naming convention to prevent object key collisions upon user upload.<br>&emsp;+ Step 3: Perform end-to-end payload transmission benchmarks: average upload response time recorded at 0.85s for 10MB files. | 10/07/2026 | 10/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Comprehensive security and performance evaluation of S3 Backend storage layer.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Test security enforcement using expired Presigned URLs (>15 min) to confirm mandatory signature expiration rejection.<br>&emsp;+ Step 2: Benchmark concurrent read/write throughput capacity under simulated load.<br>&emsp;+ Step 3: Complete formal S3 Infrastructure Acceptance Sign-off, declaring S3 storage ready for Authentication module integration in Week 4. | 11/07/2026 | 11/07/2026 | |

### Results Achieved:
* Successfully deployed Backend S3 storage infrastructure on AWS adhering to enterprise security standards.
* Storage bucket strictly isolated against unauthorized public internet access.
* Direct upload/download mechanism using Presigned URLs operating reliably with low latency.
