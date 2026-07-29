---
title: "Worklog Week 7: DynamoDB Data Layer & Profile Management Integration"
date: 2024-01-01
weight: 7
chapter: false
pre: " <b> 1.7. </b> "
---

### Objectives:
* Build User Profile management APIs interfacing data across Backend services, Cognito, DynamoDB, and S3.
* Automate profile record initialization in DynamoDB upon successful account confirmation.
* Implement profile updating and Avatar upload pipeline integrating S3 Presigned URLs with DynamoDB storage.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - Research theoretical concepts: Automated profile initialization syncing authentication service and database.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Integrate logic creating initial profile record on DynamoDB upon successful OTP confirmation.<br>&emsp;+ Step 2: Store initial attributes including user ID, Email, and creation timestamp.<br>&emsp;+ Step 3: Verify initial profile record persists accurately in DynamoDB storage. | 03/08/2026 | 03/08/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Research theoretical concepts: Business logic for retrieving logged-in user profile details.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Build personal profile retrieval processing flow on Backend.<br>&emsp;+ Step 2: Automatically decode JWT Token in HTTP Header to extract user identity.<br>&emsp;+ Step 3: Query profile details from DynamoDB and return JSON payload to client UI. | 04/08/2026 | 04/08/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| - Research theoretical concepts: Business logic for updating user profile fields.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Build profile update payload processing flow (Name, Phone) on Backend.<br>&emsp;+ Step 2: Validate payload input data format and constraints on Backend.<br>&emsp;+ Step 3: Save updated profile attributes to DynamoDB alongside updated timestamp. | 05/08/2026 | 05/08/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Research theoretical concepts: S3 Presigned URL integration with DynamoDB for Avatar photo updates.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Build Presigned URL generation flow dedicated to user avatar image files.<br>&emsp;+ Step 2: Allow client UI to upload Avatar image directly from workstation to S3 Bucket.<br>&emsp;+ Step 3: Save corresponding Avatar image S3 path to user profile record in DynamoDB. | 06/08/2026 | 06/08/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Research theoretical concepts: Automated testing methods verifying profile management feature correctness.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Build automated test scenarios verifying profile read and update operations.<br>&emsp;+ Step 2: Test missing JWT Token scenarios verifying unauthorized access blocks.<br>&emsp;+ Step 3: Confirm all automated test cases pass successfully. | 07/08/2026 | 07/08/2026 | |
| - Research overview: Evaluating end-to-end user data flow synchronization.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Execute end-to-end integration test from client UI: Sign Up -> OTP -> Login.<br>&emsp;+ Step 2: Test personal profile viewing, editing Name/Phone, and updating Avatar photo.<br>&emsp;+ Step 3: Confirm user profile data displays synchronously in real time on web application. | 08/08/2026 | 08/08/2026 | |

### Results Achieved:
* Successfully integrated 100% of User Profile management APIs connecting Cognito, DynamoDB, and S3.
* User profile data initialized synchronously, managed consistently, and updated in real-time.
* Avatar upload feature via S3 Presigned URL operating reliably with accurate asset links stored in DynamoDB.
