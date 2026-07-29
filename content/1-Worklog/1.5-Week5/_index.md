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
| - Research theoretical concepts: Connection methods between Backend application and Amazon Cognito.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Declare Cognito identity parameters in Backend environment configuration file.<br>&emsp;+ Step 2: Initialize Cognito authentication service connector module in Backend codebase.<br>&emsp;+ Step 3: Test network connectivity between Backend server and Cognito identity service. | 20/07/2026 | 20/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Research theoretical concepts: Registration API business logic from frontend interface.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Build user registration processing flow (Email, Password, Name) on Backend.<br>&emsp;+ Step 2: Forward account sign-up payload to Cognito identity directory.<br>&emsp;+ Step 3: Return unconfirmed OTP state response back to client interface. | 21/07/2026 | 21/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Research theoretical concepts: OTP Confirmation API business logic for account activation.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Build user OTP confirmation payload processing flow on Backend.<br>&emsp;+ Step 2: Forward user OTP code to Cognito for validation against email record.<br>&emsp;+ Step 3: Activate user account and return success notification to client. | 22/07/2026 | 22/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Research theoretical concepts: Login API business logic and JWT Token security token structures.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Build user login processing flow (Email, Password) on Backend.<br>&emsp;+ Step 2: Authenticate user credentials against Cognito identity pool.<br>&emsp;+ Step 3: Retrieve JWT Token set from Cognito and issue Bearer Tokens to client. | 23/07/2026 | 23/07/2026 | [Cognito Tokens Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/amazon-cognito-user-pools-using-tokens-verifying-a-jwt.html) |
| - Research theoretical concepts: JWT Token decoding and cryptographic signature verification mechanisms.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Build security Middleware intercepting and inspecting JWT Tokens in HTTP Headers.<br>&emsp;+ Step 2: Verify RSA token cryptographic signatures against Cognito public JWKS endpoint.<br>&emsp;+ Step 3: Extract user identity claims to protect private backend endpoints. | 24/07/2026 | 24/07/2026 | [Cognito Tokens Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/amazon-cognito-user-pools-using-tokens-verifying-a-jwt.html) |
| - Team meeting: Evaluate overall system architecture, review codebase, and audit report documentation. | 25/07/2026 | 25/07/2026 | |

### Results Achieved:
* Successfully integrated authentication API suite connected directly to Amazon Cognito.
* Registration, OTP Verification, and Login business workflows functioning smoothly.
* Security middleware operating effectively to safeguard application API routes.
