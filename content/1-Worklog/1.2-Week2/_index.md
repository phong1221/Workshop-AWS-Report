---
title: "Worklog Week 2: Amazon S3 Backend Infrastructure Research & Design"
date: 2024-01-01
weight: 2
chapter: false
pre: " <b> 1.2. </b> "
---

### Objectives:
* Design detailed Amazon S3 storage architecture dedicated to Backend document assets and user avatars.
* Formulate private access control policies, security restrictions, and CORS resource sharing rules.
* Research secure direct client upload solutions using temporary Presigned URLs.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - Study standardized global bucket naming rules for Amazon S3 storage.<br>- Select optimal cloud deployment region on AWS infrastructure.<br>- Ensure low access latency and cost-effective Backend data storage. | 29/06/2026 | 29/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Explore data encryption methods on Amazon S3 storage.<br>- Study automatic server-side encryption with AWS-managed keys.<br>- Guarantee absolute security for Backend documents stored at rest. | 30/06/2026 | 30/06/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Design private security authorization solutions for S3 storage.<br>- Research enabling Block Public Access safety controls.<br>- Completely isolate private Backend document assets from public internet exposure. | 01/07/2026 | 01/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Formulate Cross-Origin Resource Sharing (CORS) rule policies.<br>- Specify valid HTTP request methods allowed from web application origins.<br>- Enable secure client-side connection and data transfer. | 02/07/2026 | 02/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| - Research time-limited Presigned URL generation mechanisms.<br>- Allow client browsers to upload documents and avatars directly to S3.<br>- Bypass API payload limits and optimize backend server bandwidth. | 03/07/2026 | 03/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Consolidate Backend S3 storage architecture design blueprint.<br>- Thoroughly audit security configuration parameters.<br>- Prepare deployment strategy for actual cloud provisioning. | 04/07/2026 | 04/07/2026 | |

### Results Achieved:
* Completed detailed architecture design for Backend Amazon S3 storage.
* Ensured robust data isolation policies and valid resource sharing mechanisms.
* Fully prepared configuration parameters for cloud deployment in Week 3.
