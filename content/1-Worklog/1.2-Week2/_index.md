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
| - Research theoretical concepts: Global naming conventions for Amazon S3 Buckets & AWS Region selection.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Log into AWS Management Console and provision official Backend S3 Bucket in Region us-east-1.<br>&emsp;+ Step 2: Establish directory tree structures for documents and user profile avatars.<br>&emsp;+ Step 3: Verify storage administration permissions on personal AWS account. | 29/06/2026 | 29/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Research theoretical concepts: S3 data encryption mechanisms protecting assets at rest.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Navigate to Properties configuration tab on S3 Bucket Console.<br>&emsp;+ Step 2: Enable default Server-Side Encryption (SSE-S3) using AES-256 algorithm.<br>&emsp;+ Step 3: Upload sample file and inspect encryption metadata attributes. | 30/06/2026 | 30/06/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Research theoretical concepts: Secure authorization policies isolating storage assets from Internet.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Open Permissions configuration tab on S3 Console.<br>&emsp;+ Step 2: Turn on Block All Public Access to prevent public Internet exposure.<br>&emsp;+ Step 3: Apply private Bucket Policy restricting access strictly to Backend service. | 01/07/2026 | 01/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Research theoretical concepts: Cross-Origin Resource Sharing (CORS) rules for cross-domain web communication.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Draft CORS JSON configuration rule file for S3 Bucket.<br>&emsp;+ Step 2: Specify allowed HTTP origins and authorized HTTP request methods (GET, PUT, POST).<br>&emsp;+ Step 3: Apply CORS configuration to S3 Bucket and inspect HTTP Header responses. | 02/07/2026 | 02/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| - Research theoretical concepts: Generating temporary Presigned URLs for direct S3 client uploads.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Write helper script generating temporary Presigned URL addresses on local workstation.<br>&emsp;+ Step 2: Configure secure expiration window for temporary links.<br>&emsp;+ Step 3: Test direct file upload to S3 via Presigned URL using Postman. | 03/07/2026 | 03/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Research overview: Comprehensive audit of Backend S3 storage security parameters.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Perform public URL access test verifying connection block (403 Forbidden).<br>&emsp;+ Step 2: Consolidate S3 Backend infrastructure architectural blueprints.<br>&emsp;+ Step 3: Archive security configuration records ready for production. | 04/07/2026 | 04/07/2026 | |

### Results Achieved:
* Completed detailed architecture design for Backend Amazon S3 storage.
* Ensured robust data isolation policies and valid resource sharing mechanisms.
* Fully prepared configuration parameters for cloud deployment in Week 3.
