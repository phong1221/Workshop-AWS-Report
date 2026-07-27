---
title: "Worklog Week 3: Amazon S3 Deployment for Backend Storage"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 1.3. </b> "
---

### Objectives:
* Provision and configure Amazon S3 storage dedicated to Backend data assets and user avatars.
* Enable server-side encryption, enforce Block Public Access, and setup CORS resource sharing rules.
* Test secure file upload capabilities utilizing temporary Presigned URLs.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - Provision Amazon S3 object storage bucket on AWS cloud platform.<br>- Serve centralized management of Backend documents and user avatars.<br>- Setup storage environment in designated cloud deployment region. | 06/07/2026 | 06/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Enable default Server-Side Encryption (SSE) configuration.<br>- Apply secure encryption keys to Backend S3 storage.<br>- Guarantee all uploaded document assets are automatically encrypted. | 07/07/2026 | 07/07/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Enable Block All Public Access security controls.<br>- Isolate Backend S3 storage from unauthorized public access.<br>- Ensure absolute privacy and protection for stored user data. | 08/07/2026 | 08/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Apply CORS configuration rules to Backend S3 storage.<br>- Authorize valid HTTP request methods from application domains.<br>- Support secure frontend data transfer and communication. | 09/07/2026 | 09/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| - Execute test scenarios generating temporary Presigned URLs.<br>- Perform direct file upload tests to Backend S3 storage.<br>- Confirm file upload workflow operates successfully and accurately. | 10/07/2026 | 10/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Perform comprehensive audit of Backend S3 security parameters.<br>- Verify authorization rules and isolation mechanisms.<br>- Confirm storage infrastructure is fully ready for production. | 11/07/2026 | 11/07/2026 | |

### Results Achieved:
* Successfully provisioned AWS S3 Backend storage adhering to cloud security best practices.
* Storage environment safely isolated, preventing unauthorized external access.
* Direct upload workflow using Presigned URLs operating reliably and accurately.
