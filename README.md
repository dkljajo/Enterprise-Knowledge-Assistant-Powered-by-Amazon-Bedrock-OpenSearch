# 🧠 Enterprise Knowledge Assistant — Powered by Amazon Bedrock & OpenSearch

> *“Turning messy sales files into an intelligent, secure knowledge assistant.”*

---

## 🌟 Overview

This project showcases how to build an **Enterprise Knowledge Assistant** using **Amazon Bedrock**, **Titan Embeddings**, **Nova Micro FM**, **Amazon OpenSearch**, and **S3**, with an upgraded, **secure architecture** aligned to the **AWS Well-Architected Framework**.

It started as a simple proof-of-concept to let sales reps *ask natural language questions about their data*, and evolved into a **fully private, production-grade system** with encryption, IAM control, and automation.

---

## 🚀 Architecture Versions

### Phase 1 — Base Architecture

The original version focused on functionality and AI integration.

![Base Architecture](1.png)

**Flow:**
1. Sales representatives upload reports (PDF/CSV) to **Amazon S3**.
2. **Amazon Bedrock Knowledge Base** indexes them using **Titan Embeddings**.
3. **Nova Micro FM** enables Q&A in natural language.
4. **Amazon OpenSearch Service** supports structured search and analytics.

---

### 🔒 Phase 2 — Secure Architecture (Well-Architected Upgrade)

After learning from early tests, we hardened the design for enterprise deployment — ensuring compliance, encryption, and private networking.

![Secure Architecture](2.png)

**Security Additions:**
- ✅ **S3 SSE-KMS Encryption**
- ✅ **Private VPC Endpoints**
- ✅ **Fine-grained IAM Roles**
- ✅ **Amazon Macie** for sensitive data detection
- ✅ **Least Privilege Access**
- ✅ **OpenSearch inside VPC**

---

## 🧠 How It Works

| Step | Description |
|------|--------------|
| 1 | Sales reps upload sales reports to Amazon S3 |
| 2 | Bedrock Knowledge Base indexes new data via Titan Embeddings |
| 3 | Nova Micro FM handles natural-language Q&A |
| 4 | OpenSearch supports fast query, filtering, and reporting |
| 5 | Macie scans for sensitive data (PII/PHI) |
| 6 | CloudWatch and CloudTrail log and monitor all activity |

---

## ⚙️ Setup & Deployment

### Step 1 — Upload Sales Data to S3
```bash
aws s3 cp ./sales_reports s3://my-sales-knowledge-bucket/reports/ --recursive
aws s3 cp ./sales_details s3://my-sales-knowledge-bucket/details/ --recursive
