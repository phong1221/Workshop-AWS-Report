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
| - Integrate automated profile initialization record creation in DynamoDB.<br>- Trigger profile insertion immediately upon Email OTP confirmation.<br>- Synchronize user account details between authentication and database layers. | 03/08/2026 | 03/08/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Develop API endpoint for viewing user profile details.<br>- Decode incoming JWT token claims to extract valid user identity.<br>- Query corresponding profile record from DynamoDB and return payload. | 04/08/2026 | 04/08/2026 | [DynamoDB Core Components](https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.CoreComponents.html) |
| - Develop API endpoint supporting personal info updates.<br>- Allow editing user attributes such as full name and phone number.<br>- Persist updated values to DynamoDB with timestamp modifications. | 05/08/2026 | 05/08/2026 | [Amazon DynamoDB Developer Guide](https://docs.aws.amazon.com/dynamodb/) |
| - Implement Avatar image upload feature via Backend S3 storage.<br>- Build API generating Presigned URLs for direct image upload to S3.<br>- Update and store resulting avatar asset link in DynamoDB profile record. | 06/08/2026 | 06/08/2026 | [Amazon S3 Presigned URLs Guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-presigned-url.html) |
| - Build automated test cases verifying correctness of profile APIs.<br>- Test data retrieval and item updating operations on DynamoDB.<br>- Handle unauthorized request conditions and edge case errors. | 07/08/2026 | 07/08/2026 | |
| - Conduct end-to-end integration testing across user profile management flows.<br>- Verify chain: Register -> OTP -> Login -> Profile View -> Avatar Upload.<br>- Confirm all connected components synchronize and operate smoothly. | 08/08/2026 | 08/08/2026 | |

### Results Achieved:
* Successfully integrated 100% of User Profile management APIs connecting Cognito, DynamoDB, and S3.
* User profile data initialized synchronously, managed consistently, and updated in real-time.
* Avatar upload feature via S3 Presigned URL operating reliably with accurate asset links stored in DynamoDB.
