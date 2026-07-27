---
title: "Blog 1: Multi-Tenant Authorization for RAG"
date: 2024-01-01
weight: 1
chapter: false
pre: " <b> 3.1. </b> "
---

![Secure Multi-Tenant RAG Architecture Diagram with Amazon Bedrock and Verified Permissions](https://d2908q01vomqb2.cloudfront.net/fc074d501302eb2b93e2554793fcaf50b3bf7291/2026/07/09/secure-rag-featured-image.png)

### 1. System Purpose & Deployment Challenge
In real-world enterprise environments, data access requirements are complex: standard employees should only access their department's internal documents, while management or executives require cross-departmental access to consolidate business insights.

Retrieval-Augmented Generation (RAG) offers an ideal solution balancing document analysis performance and cost. However, constructing separate Knowledge Bases for each department leads to infrastructure duplication, skyrocketing storage costs, and heavy operational maintenance overhead. The challenge is building a single shared enterprise Knowledge Base while maintaining strict, granular access controls.

---

### 2. Solution: Logical Data Isolation
Instead of physical separation, this system applies logical data isolation using metadata filters at retrieval time.
* The underlying vector database remains a shared resource across departments.
* Based on user identity, the system dynamically restricts document search scopes. This is ideal for intra-organizational access control.

> ⚠️ **Technical Note:** Logical isolation does not replace physical infrastructure isolation via IAM policies (which remains mandatory for SaaS multi-tenant models serving independent client organizations).

---

### 3. Two-Layer Defense-in-Depth Authorization Architecture
The system features two independent authorization boundaries following a strict default-deny model:

* **Layer 1: Perimeter Security (API Gateway)**
  When a query request hits API Gateway, a Lambda Authorizer intercepts and decodes the JWT token issued by Amazon Cognito. The authorizer invokes Amazon Verified Permissions to evaluate Cedar policies, determining if the user has permissions to invoke the API route. If unverified, the request is blocked with HTTP 403 Forbidden.

* **Layer 2: Granular Retrieval Control (Middleware Lambda)**
  Upon passing Layer 1, the request routes to a Middleware Lambda executing a second evaluation: *Which department documents is this user role authorized to read?* Evaluated Cedar policy results compile into a structured metadata filter (e.g., `department = dept-a`). This filter is injected into the payload of the Amazon Bedrock `RetrieveAndGenerate` API call, filtering out unauthorized document vectors **before** context reaches the Large Language Model (LLM).

---

### 4. Automated Data Ingestion & Safe Metadata Tagging
To ensure Layer 2 metadata filtering operates reliably, all ingested documents must be accurately tagged via a two-phase automated workflow:
* **Phase 1 (Event-Driven Processing):** When new documents land in S3 department folders, EventBridge triggers SQS and invokes a Lambda function. This function creates a corresponding `.metadata.json` configuration file containing department access policies beside the source document.
* **Phase 2 (Scheduled Ingestion):** Every 5 minutes, EventBridge Scheduler triggers a Lambda function invoking Amazon Bedrock `StartIngestionJob` to vectorize documents with metadata. **Safety Mechanism:** The ingestion function skips any document missing a `.metadata.json` file, preventing untagged documents from entering the knowledge base.

---

### 5. Response Safeguards with Amazon Bedrock Guardrails
Beyond protecting input data, the architecture secures output responses via Amazon Bedrock Guardrails:
* **Contextual Grounding:** Guardrails validate AI responses against retrieved reference context, preventing hallucinations.
* **Content Filtering:** Automatically redacts or blocks harmful content, maintaining corporate compliance standards.

---

### Reference Documentation
* **Original Article on AWS Architecture Blog:** [Secure multi-tenant RAG with Amazon Bedrock and Verified Permissions](https://aws.amazon.com/vi/blogs/architecture/secure-multi-tenant-rag-with-amazon-bedrock-and-verified-permissions/)