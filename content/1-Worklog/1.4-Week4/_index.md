---
title: "Worklog Week 4: Amazon Cognito User Pool Research & Configuration"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Objectives:
* Provision and configure Amazon Cognito User Pool as a centralized user identity authentication directory.
* Implement user registration and automated Email OTP verification workflows.
* Create App Client integration entries and establish user password security rules.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - Analyze identity management requirements: User profile schema design within Amazon Cognito User Pools.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Design user attribute schema: Email (primary identifier), Full Name, Phone Number, Avatar URL, and User Role.<br>&emsp;+ Step 2: Classify required attributes versus optional metadata fields.<br>&emsp;+ Step 3: Standardize profile data encoding and privacy protection standards. | 13/07/2026 | 13/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Provision and configure Amazon Cognito User Pool identity directory.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Navigate to AWS Cognito Console, create new Cognito User Pool instance for the project.<br>&emsp;+ Step 2: Configure primary sign-in options allowing users to log in using Email address.<br>&emsp;+ Step 3: Set Multi-Factor Authentication (MFA) to Optional and configure Email account recovery options. | 14/07/2026 | 14/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Configure password security policies & automated Email OTP verification delivery flows.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Define Password Policy requiring minimum 8 characters, uppercase, lowercase, numbers, and special symbols.<br>&emsp;+ Step 2: Enable automated 6-digit verification OTP code issuance upon account sign-up via Email.<br>&emsp;+ Step 3: Customize HTML Email template with SmartDocAI branding and 10-minute OTP expiration lifetime. | 15/07/2026 | 15/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Provision App Client within Cognito User Pool to support Web Application interface.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Create App Client entry within Cognito User Pool.<br>&emsp;+ Step 2: Disable Client Secret generation (Generate client secret = False) as Single Page Web Apps cannot securely store secrets.<br>&emsp;+ Step 3: Enable allowed secure authentication flows to support the web interface. | 16/07/2026 | 16/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Test end-to-end Account Registration & Real-time Email OTP Verification flow.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Trigger user registration API call supplying test user email and password credentials.<br>&emsp;+ Step 2: Inspect recipient email inbox for incoming 6-digit OTP verification code.<br>&emsp;+ Step 3: Trigger OTP confirmation API call with received OTP code to successfully transition account status to fully verified. | 17/07/2026 | 17/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Audit Cognito User Pool security settings and extract integration configurations.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Review security configurations on AWS Console, disabling unused authentication flows to minimize attack surfaces.<br>&emsp;+ Step 2: Extract essential configuration parameters: User Pool ID, App Client ID, and AWS Region.<br>&emsp;+ Step 3: Save configuration parameters into local `.env` environment file ready for FastAPI Backend integration in Week 5. | 18/07/2026 | 18/07/2026 | |

### Results Achieved:
* Successfully provisioned and configured Amazon Cognito User Pool for centralized user identity authentication.
* Automated Email OTP verification code delivery flows operated reliably and accurately.
* Complete set of integration credentials fully extracted for Backend integration in Week 5.
