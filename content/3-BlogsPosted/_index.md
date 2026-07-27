---
title: "Posted Technical Blogs"
date: 2024-01-01
weight: 3
chapter: false
pre: " <b> 3. </b> "
---

Below is the summary of 3 technical blog posts on cloud infrastructure and serverless architecture published in the [AWS Study Group](https://www.facebook.com/groups/awsstudygroupfcj) community:

---

### [Blog 1 - Secure Multi-Tenant RAG System with Amazon Bedrock and Verified Permissions](3.1-Blog1/)

![Secure Multi-Tenant RAG Architecture Diagram with Amazon Bedrock](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2026/07/09/secure-rag-featured-image.png)

This post introduces a solution for building a shared enterprise RAG (Retrieval-Augmented Generation) system using Amazon Bedrock and Amazon Verified Permissions. The architecture enforces logical data isolation through metadata filters and a defense-in-depth authorization pattern at API Gateway and Middleware Lambda layers.

---

### [Blog 2 - Amazon Bedrock Baseline Architecture in an AWS Landing Zone](3.2-Blog2/)

![Amazon Bedrock Baseline Architecture Diagram in AWS Landing Zone](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2025/06/18/ARCHBLOG-1133-image-1-960x630.png)

This blog outlines the baseline architecture for deploying Amazon Bedrock within an AWS Landing Zone (AWS Control Tower). It covers multi-account isolation, private network connectivity via AWS PrivateLink, identity management with IAM Identity Center, and centralized governance via SCPs and CloudWatch/CloudTrail logging.

---

### [Blog 3 - 5 Common Pitfalls to Avoid in Serverless Architecture with AWS Lambda](3.3-Blog3/)

![Monolith vs Serverless Microservices Comparison Architecture Diagram](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2021/05/27/Example-1-Monolitic-VS-Microservice-approach-1260x554.png)

This blog analyzes 5 classic mistakes developers make when transitioning from traditional servers (EC2/VPS) to Event-Driven Serverless architecture on AWS Lambda, providing remedies using Amazon SQS, RDS Proxy, AWS Lambda Power Tuning, and AWS Step Functions.