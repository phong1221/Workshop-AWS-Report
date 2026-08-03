---
title: "Worklog Week 1: Technology Overview & AWS Serverless Research"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 1.1. </b> "
---

### Objectives:
* Research theoretical concepts of Serverless Architecture on AWS cloud computing.
* Study fundamental operating principles of core deployed AWS services: Amazon S3, Amazon Cognito, and Amazon DynamoDB.
* Analyze application business data flows and establish functional boundaries.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - **Attend FCJ 2026 Kick-off meeting**, absorbing internship guidelines, cloud resource governance policies, and project reporting requirements from AWS Mentors.<br>- Deep-dive into theoretical foundations of AWS Serverless Computing architecture: pros/cons versus traditional server-based models, auto-scaling mechanisms, pay-as-you-go pricing, and event-driven architecture. | 22/06/2026 | 22/06/2026 | |
| - Detailed research on Amazon Simple Storage Service (Amazon S3): Bucket/Object concepts, Storage Classes, Server-Side Encryption (SSE-S3, SSE-KMS), Access Control Lists (ACLs), Bucket Policy, and Cross-Origin Resource Sharing (CORS).<br>- **Hands-on sandbox practice:**<br>&emsp;+ Step 1: Provision test S3 Bucket on AWS Management Console.<br>&emsp;+ Step 2: Enable default Server-Side Encryption (SSE-S3) with AES-256 algorithm for data-at-rest protection.<br>&emsp;+ Step 3: Enable "Block All Public Access" configuration to isolate public access and enforce strict permissions. | 23/06/2026 | 23/06/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) |
| - Study identity management service Amazon Cognito User Pools and structure of OAuth 2.0 / JWT Tokens (ID Token, Access Token, Refresh Token).<br>- **Hands-on sandbox practice:**<br>&emsp;+ Step 1: Provision test Cognito User Pool directory for user identity management.<br>&emsp;+ Step 2: Configure automated 6-digit Email OTP delivery rules for account verification.<br>&emsp;+ Step 3: Register test App Client (without Client Secret) to support web application authentication flows. | 24/06/2026 | 24/06/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - **Team discussion:** Finalize **SmartDocAI** project selection (Intelligent Document Analysis & QA system leveraging AWS Cloud & AI). Assign specific roles to team members.<br>- Research Amazon DynamoDB NoSQL operational principles: Partition Key, Sort Key, Global Secondary Index (GSI), Local Secondary Index (LSI), On-Demand capacity mode, and Read/Write Capacity Units (RCU/WCU). | 25/06/2026 | 25/06/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Study Docker containerization technology and Python FastAPI framework for high-performance RESTful APIs.<br>- **Hands-on sandbox practice:**<br>&emsp;+ Step 1: Draft multi-stage Dockerfile optimizing image size and Python 3.11 environment.<br>&emsp;+ Step 2: Build FastAPI Backend application into Docker Image and run container on local workstation.<br>&emsp;+ Step 3: Use Postman to test health check endpoints and measure response times. | 26/06/2026 | 26/06/2026 | |
| - Consolidate standard Serverless data flow architecture on AWS (Client -> Web Frontend -> API Gateway / FastAPI Backend -> Cognito Auth / S3 / DynamoDB).<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Draw high-level Architecture Diagram detailing interaction flows between Frontend, Backend, and AWS services.<br>&emsp;+ Step 2: Consolidate weekly theoretical research documentation, technical notes, and API specs.<br>&emsp;+ Step 3: Align next deployment roadmap for S3 Infrastructure Design with team members for Week 2. | 27/06/2026 | 27/06/2026 | |

### Results Achieved:
* Acquired solid theoretical baseline and operating understanding of core AWS cloud services (S3, Cognito, DynamoDB) and FastAPI backend framework.
* Defined overall architecture blueprint and standardized data flow models for the SmartDocAI system.
* Strictly followed project guidelines: focused solely on literature research and sandbox testing without deploying production resources in Week 1.
