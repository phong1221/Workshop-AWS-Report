---
title: "Worklog Week 5: Cognito Authentication Integration with FastAPI Backend"
date: 2024-01-01
weight: 5
chapter: false
pre: " <b> 1.5. </b> "
---

### Objectives:
* Build API communication endpoints for User Registration, OTP Confirmation, and Login flows.
* Decode and verify validity of JWT tokens issued by Amazon Cognito.
* Implement security middleware protection preventing unauthorized API access to Backend services.

### Work Performed:

| Task | Start Date | End Date | Reference Documents |
| --- | --- | --- | --- |
| - Connect Backend processing application with Amazon Cognito identity service.<br>- Utilize official AWS SDK software development integration toolkits.<br>- Prepare authentication service configurations for Backend codebase. | 20/07/2026 | 20/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Develop Registration API endpoint processing incoming user payloads.<br>- Invoke Cognito service to initialize new user account record.<br>- Place new user account into unconfirmed state awaiting OTP verification. | 21/07/2026 | 21/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Develop OTP Confirmation API endpoint validating user-submitted Email verification codes.<br>- Verify Email OTP verification code against Cognito identity service.<br>- Transition account to confirmed status upon successful validation. | 22/07/2026 | 22/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Develop Login API endpoint processing Email and Password credentials.<br>- Authenticate login requests against Amazon Cognito identity pool.<br>- Retrieve and issue secure JWT Token sets to authorized client requests. | 23/07/2026 | 23/07/2026 | [Cognito Tokens Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/amazon-cognito-user-pools-using-tokens-verifying-a-jwt.html) |
| - Build security middleware mechanism decoding and validating JWT tokens.<br>- Verify token cryptographic signatures against Cognito public keys.<br>- Extract valid user identity claims to protect private backend APIs. | 24/07/2026 | 24/07/2026 | [Cognito Tokens Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/amazon-cognito-user-pools-using-tokens-verifying-a-jwt.html) |
| - Conduct comprehensive integration testing across authentication flows (Registration, OTP, Login JWT issuance).<br>- Team meeting: Evaluate overall system architecture, review codebase, and audit report documentation. | 25/07/2026 | 25/07/2026 | |

### Results Achieved:
* Successfully integrated authentication API suite connected directly to Amazon Cognito.
* Registration, OTP Verification, and Login business workflows functioning smoothly.
* Security middleware operating effectively to safeguard application API routes.
