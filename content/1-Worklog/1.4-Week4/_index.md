---
title: "Worklog Week 4: Amazon Cognito User Pool Research & Configuration"
date: 2024-01-01
weight: 4
chapter: false
pre: " <b> 1.4. </b> "
---

### Objectives:
* Provision and configure Amazon Cognito User Pool as centralized identity management service.
* Implement Registration and Email OTP verification flows (focusing strictly on Email OTP, without Google OAuth).
* Create App Client and establish user credential password policies.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - Study User object storage schema within Amazon Cognito User Pools.<br>- Select Email address as primary sign-in attribute.<br>- Declare supplementary user attributes including full name and phone. | 13/07/2026 | 13/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Provision Amazon Cognito User Pool service on AWS management console.<br>- Establish central user identity repository and authentication directory.<br>- Configure operating parameters for identity services. | 14/07/2026 | 14/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Setup secure user password credential policies.<br>- Configure automated 6-digit Email OTP verification code dispatch.<br>- Ensure automated account verification workflow upon sign-up. | 15/07/2026 | 15/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Create App Client integration entry within Cognito User Pool.<br>- Configure secure authentication flows for client applications.<br>- Enable safe credential parameter exchange with Cognito. | 16/07/2026 | 16/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Perform test user registration workflow on the system.<br>- Verify automatic delivery of 6-digit Email OTP verification code.<br>- Confirm account activation status transitions to confirmed. | 17/07/2026 | 17/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Audit overall security configuration of Cognito User Pool.<br>- Ensure strict Email OTP authentication enforcement (excluding Google OAuth).<br>- Record integration connection parameters for Backend code wiring. | 18/07/2026 | 18/07/2026 | |

### Results Achieved:
* Successfully provisioned and configured Amazon Cognito User Pool for user authentication.
* Email OTP verification code dispatch operating reliably and accurately.
* Prepared integration parameters for Backend application connection in Week 5.
