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
| - Analyze user profile storage attribute requirements for the system.<br>- Enumerate managed attributes (unique ID, email, name, phone, avatar link).<br>- Define creation and modification data timestamp fields. | 27/07/2026 | 27/07/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| - Design NoSQL data schema structure for user profile table.<br>- Select appropriate Partition Key attribute for efficient indexing.<br>- Ensure uniform data partition distribution across storage servers. | 28/07/2026 | 28/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Provision database table on Amazon DynamoDB service.<br>- Configure On-Demand (pay-per-request) capacity management mode.<br>- Optimize operational costs charging strictly per active request. | 29/07/2026 | 29/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Configure Encryption at Rest features on DynamoDB table.<br>- Apply secure encryption keys protecting stored database items.<br>- Guarantee absolute security for stored user profile records. | 30/07/2026 | 30/07/2026 | [DynamoDB Encryption at Rest](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/EncryptionAtRest.html) |
| - Implement database interaction module interfacing with Amazon DynamoDB.<br>- Build helper routines for profile insertion upon sign-up.<br>- Build querying and attribute update routines for user profile data. | 31/07/2026 | 31/07/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Execute test scripts inserting and querying sample data on DynamoDB.<br>- Monitor and verify database response latency performance metrics.<br>- Confirm rapid read/write data access with low latency. | 01/08/2026 | 01/08/2026 | |

### Results Achieved:
* Successfully provisioned Amazon DynamoDB database table matching encryption and cost optimization standards.
* Built base database interaction routines ready for Backend API consumption.
* Achieved rapid read/write database response performance with low latency.
