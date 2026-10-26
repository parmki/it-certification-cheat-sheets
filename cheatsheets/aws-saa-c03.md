# AWS Certified Solutions Architect – Associate (SAA-C03) Cheat Sheet

A comprehensive, high-yield blueprint guide covering core AWS architectural design principles, domain weights, service decision matrices, and common distractor traps.

> **Interactive Practice**: Test these concepts in real scenario drills on [BenchCert AWS SAA-C03 Guide](https://benchcert.app/cert/aws-saa-c03) or try the [5-Question Free Instant Trial](https://benchcert.app/try).

---

## 📊 Exam Blueprint & Domain Weights
- **Domain 1**: Design Secure Architectures (**30%**)
- **Domain 2**: Design Resilient Architectures (**26%**)
- **Domain 3**: Design High-Performing Architectures (**24%**)
- **Domain 4**: Design Cost-Optimized Architectures (**20%**)

**Passing Score**: 720 / 1000  
**Format**: 65 Questions | 130 Minutes

---

## 🏗️ Storage Decision Matrix

| Storage Service | Storage Type | Protocol | Primary Use Case | Performance Benchmark |
| :--- | :--- | :--- | :--- | :--- |
| **Amazon S3** | Object | REST HTTP/S | Unstructured files, static websites, data lakes | Up to 3,500 PUT and 5,500 GET req/sec per prefix |
| **Amazon EBS** | Block | Raw Block | OS boot volumes, transactional databases (single EC2) | gp3 (up to 16,000 IOPS), io2 Block Express (up to 256,000 IOPS) |
| **Amazon EFS** | File (Shared) | NFSv4 | Linux multi-AZ shared file system (thousands of EC2s) | Elastic throughput mode, sub-ms read latencies |
| **Amazon FSx for Windows** | File (Shared) | SMB | Native Windows workloads, Active Directory integration | Sub-millisecond latency, multi-AZ failover |
| **Amazon FSx for Lustre** | High Performance | Lustre | HPC, machine learning, financial modeling | Hundreds of GB/s throughput, millions of IOPS |

---

## 🔄 Decoupling & Messaging
- **Amazon SQS (Standard)**: Unlimited throughput, at-least-once delivery, best-effort ordering.
- **Amazon SQS (FIFO)**: Guaranteed exactly-once processing, strict ordering, 300 msgs/sec (or 3,000 msgs/sec with batching).
- **Amazon SNS**: Fanout pub/sub model (one publisher $\rightarrow$ multiple subscribers: SQS, Lambda, Email, SMS).
- **Amazon EventBridge**: Serverless event bus routing JSON events between SaaS apps, AWS services, and custom microservices with declarative content filtering rules.

---

## ⚡ High-Yield Exam Traps & Anti-Patterns
1. **Disaster Recovery RTO / RPO Spectrum**:
   - *Backup & Restore*: Hours to days (lowest cost).
   - *Pilot Light*: Core data kept replicated; compute launched via AMIs on disaster (RTO tens of minutes).
   - *Warm Standby*: Scaled-down minimum production footprint always running (RTO minutes).
   - *Multi-Region Active-Active*: Zero downtime, instant traffic routing (highest cost).
2. **Gateway Endpoints vs Interface Endpoints**:
   - Gateway Endpoints support **only S3 and DynamoDB** and cost **$0.00/GB**.
   - Interface Endpoints (PrivateLink) support all other services, require an Elastic Network Interface (ENI), and incur hourly ENI and per-GB transfer fees.
3. **Route 53 Routing Controls (Route 53 ARC)**:
   - For region failover during catastrophic control-plane impairments, use Route 53 Application Recovery Controller (Route 53 ARC) cluster data-plane endpoints, not `ChangeResourceRecordSets` control plane APIs.

---

### Resources
- [BenchCert AWS SAA-C03 Hub](https://benchcert.app/cert/aws-saa-c03)
- [Official AWS SAA-C03 Exam Guide](https://d1.awsstatic.com/training-and-certification/docs-sa-assoc/AWS-Certified-Solutions-Architect-Associate_Exam-Guide.pdf)
