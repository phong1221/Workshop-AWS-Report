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
| - Research theoretical concepts: User object schema design in Amazon Cognito User Pools.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Design user attribute schema blueprint (Email, Full Name, Phone, Avatar).<br>&emsp;+ Step 2: Categorize mandatory primary identity attributes and optional profile fields.<br>&emsp;+ Step 3: Standardize user credential encryption formatting. | 13/07/2026 | 13/07/2026 | [Amazon Cognito User Pools Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/cognito-user-identity-pools.html) |
| - Research theoretical concepts: Provisioning and managing centralized user identity directory via Cognito.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Log into AWS Console and provision new Amazon Cognito User Pool.<br>&emsp;+ Step 2: Select Email Address as primary sign-in method.<br>&emsp;+ Step 3: Setup operational security parameters for identity directory. | 14/07/2026 | 14/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Research theoretical concepts: User password credential complexity standards & automated Email OTP verification.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Configure minimum 8-character password complexity rules.<br>&emsp;+ Step 2: Enable automated 6-digit OTP delivery mechanism upon sign-up.<br>&emsp;+ Step 3: Customize Email notification template for OTP code delivery. | 15/07/2026 | 15/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Research theoretical concepts: App Client authorization entries and credential encryption in Cognito.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Provision new App Client entry within Cognito User Pool.<br>&emsp;+ Step 2: Configure client secret-free security mode for SPA Web Frontend compatibility.<br>&emsp;+ Step 3: Grant secure user authentication flow permissions for frontend UI. | 16/07/2026 | 16/07/2026 | [Amazon Cognito Developer Guide](https://docs.aws.amazon.com/cognito/) |
| - Research overview: User sign-up workflow and real-time Email OTP code delivery.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Perform test user registration workflow on application system.<br>&emsp;+ Step 2: Retrieve and input 6-digit OTP code received via email.<br>&emsp;+ Step 3: Confirm user account status transitions to confirmed state. | 17/07/2026 | 17/07/2026 | [Cognito Verification Guide](https://docs.aws.amazon.com/cognito/latest/developerguide/user-pool-settings-email-phone-verification.html) |
| - Research overview: Security policy compliance and audit metrics for Cognito User Pool.<br>- **Hands-on practice:**<br>&emsp;+ Step 1: Audit all security settings on Cognito Management Console.<br>&emsp;+ Step 2: Disable unused authentication flows to minimize attack surfaces.<br>&emsp;+ Step 3: Export User Pool ID and App Client ID configuration parameters for Backend. | 18/07/2026 | 18/07/2026 | |

### Results Achieved:
* Successfully provisioned and configured Amazon Cognito User Pool for user authentication.
* Email OTP verification code dispatch operating reliably and accurately.
* Prepared integration parameters for Backend application connection in Week 5.
