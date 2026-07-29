---
title: "Worklog Week 6: Amazon DynamoDB Database Research & Deployment"
date: 2024-01-01
weight: 6
chapter: false
pre: " <b> 1.6. </b> "
---

### Objectives:
* Analyze user data storage requirements and design NoSQL data models for the database layer.
* Provision data table on Amazon DynamoDB service optimizing cost and security posture.
* Configure data encryption at rest and build base database interaction routines.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - Research theoretical concepts: User profile storage attribute requirements for application.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Draft Blog 3 (*5 Classic Mistakes When Deploying Serverless*) content.<br>&emsp;+ Step 2: Publish Blog 3 on AWS Study Group VN community forum.<br>&emsp;+ Step 3: Design detailed user profile data entity schema. | 27/07/2026 | 27/07/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) & Blog 3 |
| - Research theoretical concepts: NoSQL data modeling for user profile table and selecting Partition Keys.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Define NoSQL data persistence schema on Amazon DynamoDB.<br>&emsp;+ Step 2: Select user identity attribute as primary Partition Key for uniform distribution.<br>&emsp;+ Step 3: Map satellite profile attributes (Full Name, Phone, Avatar Path). | 28/07/2026 | 28/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Research theoretical concepts: On-Demand capacity management mode on Amazon DynamoDB.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Provision user profile database storage area on AWS Management Console.<br>&emsp;+ Step 2: Configure On-Demand capacity mode for dynamic auto-scaling per traffic.<br>&emsp;+ Step 3: Optimize operational costs charging strictly per active read/write request. | 29/07/2026 | 29/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Research theoretical concepts: Encryption at Rest security features protecting database tables.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Access security configuration tab on DynamoDB Management Console.<br>&emsp;+ Step 2: Enable Encryption at Rest security feature protecting stored database items.<br>&emsp;+ Step 3: Confirm encryption status protecting user profile records at rest. | 30/07/2026 | 30/07/2026 | [DynamoDB Encryption at Rest](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/EncryptionAtRest.html) |
| - Research theoretical concepts: Data Layer module implementation interfacing Backend with Amazon DynamoDB.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Program data interaction module connecting Backend app with DynamoDB.<br>&emsp;+ Step 2: Build processing flows for profile initialization, data retrieval, and attribute updates.<br>&emsp;+ Step 3: Add exception handling mechanisms for connectivity or query failures. | 31/07/2026 | 31/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Team meeting: Evaluate DynamoDB performance, finalize SmartDocAI project acceptance, and prepare for final presentation. | 01/08/2026 | 01/08/2026 | |

### Results Achieved:
* Successfully provisioned Amazon DynamoDB database table matching encryption and cost optimization standards.
* Built base database interaction routines ready for Backend API consumption.
* Achieved rapid read/write database response performance with low latency.
