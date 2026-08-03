---
title: "Worklog Week 6: Technology Component Testing & End-to-End System Testing"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Objectives:
* Conduct component testing for deployed cloud infrastructure technologies (Amazon S3, Amazon Cognito, Amazon DynamoDB, FastAPI Backend).
* Execute End-to-End System Integration Testing (E2E Testing) across the entire project to verify stability and security.
* Audit overall system performance and finalize technical acceptance sign-off.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - Publish technical Blog 3 and conduct Amazon S3 technology testing.<br>- **Practice & Blog 3 Publishing:**<br>&emsp;+ Step 1: Draft technical article **Blog 3** (*5 Classic Pitfalls When Deploying Serverless Architecture on AWS & How to Avoid Them*) and publish on AWS Study Group VN.<br>&emsp;+ Step 2: Test S3 technological features: SSE-S3 AES-256 encryption enforcement, Block Public Access isolation flag, and S3 Bucket Policy constraints.<br>&emsp;+ Step 3: Test Presigned URL TTL expiration handling and verify valid HTTP CORS response headers from client browsers. | 27/07/2026 | 27/07/2026 | [Amazon S3 User Guide](https://docs.aws.amazon.com/s3/) & Blog 3 |
| - Component testing of Amazon Cognito User Pools identity management service.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Test account registration API calls supplying valid user emails and verify duplicate email constraint handling.<br>&emsp;+ Step 2: Test 6-digit Email OTP delivery and confirmation flows, simulating invalid OTP attempts or expired OTP codes (>10 mins).<br>&emsp;+ Step 3: Test authentication login flow issuing valid JWT tokens and measure authentication response latency. | 28/07/2026 | 28/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Component testing of Amazon DynamoDB NoSQL database service.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Execute automated Read/Write performance benchmark script against the user profile table.<br>&emsp;+ Step 2: Measure query latency targeting Partition Key user identifier, recording an average response time of sub-6ms.<br>&emsp;+ Step 3: Test Point-in-time recovery (PITR) continuous backup activation and verify Encryption at Rest flags on AWS Console. | 29/07/2026 | 29/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Component testing of FastAPI Backend Framework and JWT Authentication Middleware.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Run automated `pytest` suite for backend API routers (authentication and profile management routes).<br>&emsp;+ Step 2: Issue HTTP requests with invalid JWT Access Tokens, expired tokens, or tampered RS256 signatures, verifying mandatory HTTP 401 Unauthorized error responses.<br>&emsp;+ Step 3: Benchmark JWKS key resolution middleware stability and verify trace logs on backend server. | 30/07/2026 | 30/07/2026 | |
| - End-to-End (E2E) System Integration Testing across the entire project.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Formulate end-to-end integration test scenarios connecting Web UI frontend to AWS cloud backend infrastructure.<br>&emsp;+ Step 2: Execute complete sequential user flow: Account Registration -> Email OTP -> Account Activation -> Login & JWT Acquisition -> Profile Viewing -> Profile Update -> Direct Avatar Upload to S3 via Presigned URL -> DynamoDB Persistence.<br>&emsp;+ Step 3: Record results: 100% E2E test scenarios passed successfully, demonstrating high system synchronization and reliability. | 31/07/2026 | 31/07/2026 | |
| - **Team Meeting:** Evaluate DynamoDB & overall project testing performance, summarize SmartDocAI project acceptance sign-off, and prepare for final presentation council.<br>- **Detailed agenda:**<br>&emsp;+ Summarize test results from individual technology component testing (S3, Cognito, DynamoDB, FastAPI) and E2E system testing.<br>&emsp;+ Audit response latency metrics, security isolation rules, and data recovery readiness.<br>&emsp;+ Align technical acceptance sign-off, ready for Week 7 video demo recording and completing remaining documentation sections. | 01/08/2026 | 01/08/2026 | |

### Results Achieved:
* Completed thorough component testing of core technologies (S3, Cognito, DynamoDB, FastAPI) meeting technical benchmarks.
* Achieved 100% pass rate in End-to-End System Testing across the entire project, confirming high stability and reliability.
* Team fully prepared for the final week to record the video demo and package report documentation.
