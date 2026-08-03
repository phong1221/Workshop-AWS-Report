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
| - Research S3 bucket architecture standards: AWS naming conventions, selecting AWS Region for cost efficiency & service compatibility.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Log in to AWS Console and create production S3 bucket for Backend storage.<br>&emsp;+ Step 2: Design folder structure inside the bucket: dedicated folders for user documents, profile avatars, and temporary file uploads.<br>&emsp;+ Step 3: Configure IAM Role/User permissions and verify access policies. | 29/06/2026 | 29/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Research S3 data encryption options at rest: SSE-S3 (Amazon S3 Managed Keys) vs SSE-KMS (AWS KMS).<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Access Properties configuration for the production Backend S3 bucket.<br>&emsp;+ Step 2: Enable default Server-Side Encryption using SSE-S3 (AES-256 encryption standard).<br>&emsp;+ Step 3: Upload sample object and inspect object metadata headers to confirm automatic encryption. | 30/06/2026 | 30/06/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Research data isolation strategy: Prevent internet data leaks via Block Public Access settings and S3 Bucket Policies.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Enable "Block All Public Access" at bucket level to block unauthorized public HTTP requests.<br>&emsp;+ Step 2: Draft JSON-formatted S3 Bucket Policy adhering to Principle of Least Privilege.<br>&emsp;+ Step 3: Apply policy restricting access exclusively to authenticated IAM credentials of the Backend API. | 01/07/2026 | 01/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Research Cross-Origin Resource Sharing (CORS) rules for S3 buckets when web applications operate from distinct web domains/origins.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Draft CORS JSON configuration specifying allowed origins (local workstation environment and production web domain), allowed HTTP request methods (GET, PUT, POST, DELETE, HEAD), and allowed headers.<br>&emsp;+ Step 2: Update CORS configuration under bucket Permissions tab on AWS Console.<br>&emsp;+ Step 3: Execute cURL Preflight OPTIONS Request from workstation to verify returned CORS headers. | 02/07/2026 | 02/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) |
| - Research secure object upload/download mechanism using Presigned URLs without exposing public S3 bucket access.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Write test Python script using `boto3` SDK to generate Presigned URLs for object upload and download operations.<br>&emsp;+ Step 2: Configure Time-To-Live (TTL / Expiration) for Presigned URLs to 900 seconds (15 minutes) for optimal security.<br>&emsp;+ Step 3: Use Postman to issue HTTP PUT requests carrying document payload directly to generated Presigned URLs, confirming object arrival in S3. | 03/07/2026 | 03/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Overall audit and safety assessment of the designed S3 Backend infrastructure.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Test direct HTTP URL access to S3 objects via browser without Presigned URL to verify mandatory access restriction (403 Forbidden).<br>&emsp;+ Step 2: Compile S3 infrastructure design blueprint, folder naming conventions, and CORS/Bucket policy specifications.<br>&emsp;+ Step 3: Archive all infrastructure configuration artifacts for formal deployment in Week 3. | 04/07/2026 | 04/07/2026 | |

### Results Achieved:
* Completed detailed architecture design for Backend Amazon S3 storage dedicated to SmartDocAI system.
* Ensured robust data isolation policies and valid resource sharing mechanisms.
* Fully prepared configuration parameters for cloud deployment in Week 3.
