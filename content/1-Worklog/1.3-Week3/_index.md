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
| - Research overview: Provisioning procedures for Backend S3 Bucket and user avatar storage.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Provision official Backend S3 Bucket in AWS Region us-east-1.<br>&emsp;+ Step 2: Draft Blog 1 (*Secure Multi-Tenant RAG*) content in Markdown format.<br>&emsp;+ Step 3: Publish Blog 1 on AWS Study Group VN community forum. | 06/07/2026 | 06/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) & Blog 1 |
| - Research theoretical concepts: Automated server-side data encryption mechanisms (SSE-S3).<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Apply SSE-S3 server-side encryption rules to production S3 bucket.<br>&emsp;+ Step 2: Execute automated script uploading test files to S3 bucket.<br>&emsp;+ Step 3: Verify ServerSideEncryption parameter in object Metadata attributes. | 07/07/2026 | 07/07/2026 | [Amazon S3 Encryption Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html) |
| - Research theoretical concepts: Complete isolation of Backend storage assets from public connections.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Enable Bucket-level Block Public Access security controls.<br>&emsp;+ Step 2: Verify storage partition isolation policies.<br>&emsp;+ Step 3: Ensure total prevention of user data asset leakage to external environments. | 08/07/2026 | 08/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Research theoretical concepts: HTTP Header communications between web clients and S3 storage.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Apply updated production CORS JSON configuration to Backend S3 bucket.<br>&emsp;+ Step 2: Draft Blog 2 (*Amazon Bedrock Baseline Architecture*) content.<br>&emsp;+ Step 3: Publish Blog 2 on AWS Study Group VN community forum. | 09/07/2026 | 09/07/2026 | [Amazon S3 CORS Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/cors.html) & Blog 2 |
| - Research theoretical concepts: Expiration timelines and security signature verification for Presigned URLs.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Program temporary Presigned URL generator in Backend application.<br>&emsp;+ Step 2: Test file transfer connection between React Frontend and S3 via Presigned URL.<br>&emsp;+ Step 3: Measure file upload performance latency under 1.2s. | 10/07/2026 | 10/07/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Research overview: Evaluating overall performance and information security of storage.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Conduct security testing against expired Presigned URL links.<br>&emsp;+ Step 2: Audit authorization rules and resource isolation on S3 Bucket.<br>&emsp;+ Step 3: Complete Backend S3 storage infrastructure acceptance record. | 11/07/2026 | 11/07/2026 | |

### Results Achieved:
* Successfully provisioned AWS S3 Backend storage adhering to cloud security best practices.
* Storage environment safely isolated, preventing unauthorized external access.
* Direct upload workflow using Presigned URLs operating reliably and accurately.
