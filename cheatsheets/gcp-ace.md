# Google Cloud Certified Associate Cloud Engineer (GCP ACE) Cheat Sheet

Architecture reference for Google Cloud Platform IAM roles, Compute Engine, GKE, Cloud Run, and VPC configurations.

> **Interactive Practice**: Active recall drills and diagnostic breakdown on [BenchCert GCP ACE Hub](https://benchcert.app/cert/gcp-ace).

---

## 📊 Exam Blueprint & Domain Weights
- **Domain 1**: Setting up a cloud solution environment (**17.5%**)
- **Domain 2**: Planning and configuring a cloud solution (**17.5%**)
- **Domain 3**: Deploying and implementing a cloud solution (**25%**)
- **Domain 4**: Ensuring successful operation of a cloud solution (**20%**)
- **Domain 5**: Configuring access and security (**20%**)

**Passing Score**: 70%  
**Format**: 50–60 Questions | 120 Minutes

---

## ☁️ GCP Compute Services Selection Matrix
| Service | Abstraction | Scaling Behavior | Best Fit |
| :--- | :--- | :--- | :--- |
| **Compute Engine** | IaaS (VMs) | Managed Instance Groups (MIGs) | Legacy apps, custom OS kernels, persistent local storage |
| **Google Kubernetes Engine (GKE)** | Containers (K8s) | Cluster Autoscaler & HPA | Complex microservices, multi-container orchestration |
| **Cloud Run** | Serverless Containers | Scale-to-zero, instant concurrency | Web APIs, event-driven microservices, containerized workloads |
| **Cloud Functions** | FaaS (Serverless code) | Event-driven invocation | Lightweight webhooks, Cloud Storage triggers, Pub/Sub processing |

---

## 🔑 IAM Role Hierarchy & Rules
- **Resource Hierarchy**: Organization $\rightarrow$ Folder $\rightarrow$ Project $\rightarrow$ Resource.
- **Inheritance Rule**: Permissions are strictly **additive** down the hierarchy (an allow policy granted at a higher parent cannot be denied at a child level).
- **Role Types**:
  - *Primitive*: Owner, Editor, Viewer (Broad, not recommended for production).
  - *Predefined*: Granular per-service roles (e.g., `roles/compute.networkAdmin`, `roles/storage.objectViewer`).
  - *Custom*: User-defined collections of specific permissions.

---

### Resources
- [BenchCert Google Cloud ACE Hub](https://benchcert.app/cert/gcp-ace)
- [Official Google Cloud ACE Exam Guide](https://cloud.google.com/learn/certification/cloud-engineer)
