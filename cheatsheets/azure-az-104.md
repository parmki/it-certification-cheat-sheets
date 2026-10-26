# Microsoft Certified: Azure Administrator Associate (AZ-104) Cheat Sheet

Core architecture reference for Azure governance, Entra ID (Azure AD), storage redundancy, virtual networking, and compute administration.

> **Interactive Practice**: Active recall drills and diagnostic breakdown on [BenchCert Azure AZ-104 Hub](https://benchcert.app/cert/azure-az-104).

---

## 📊 Exam Blueprint & Domain Weights
- **Domain 1**: Manage Azure Identities and Governance (**22%**)
- **Domain 2**: Implement and Manage Storage (**18%**)
- **Domain 3**: Deploy and Manage Azure Compute Resources (**22%**)
- **Domain 4**: Configure and Manage Virtual Networking (**26%**)
- **Domain 5**: Monitor and Maintain Azure Resources (**16%**)

**Passing Score**: 700 / 1000  
**Format**: 40–60 Questions | 100 Minutes

---

## 💾 Storage Redundancy Matrix
| Replication Option | Scope | Failure Tolerance | Target SLA |
| :--- | :--- | :--- | :--- |
| **LRS (Locally Redundant)** | Single data center in primary region | 3 copies across separate racks in 1 facility | 11 9's ($99.999999999\%$) |
| **ZRS (Zone Redundant)** | 3 availability zones in primary region | 3 copies across 3 distinct zones in 1 region | 12 9's ($99.9999999999\%$) |
| **GRS (Geo-Redundant)** | Primary region + paired secondary region | LRS in primary + LRS asynchronously replicated to secondary | 16 9's |
| **GZRS (Geo-Zone-Redundant)** | Primary zones + secondary region | ZRS in primary + LRS in paired secondary region | 16 9's |

---

## 🌐 Virtual Networking & Routing
- **VNet Peering**: Low latency, private Microsoft backbone routing. Non-transitive by default (VNet A peered to B, and B to C does NOT connect A to C without an NVA / route tables).
- **Network Security Groups (NSGs)**:
  - Processed in order of **Priority** (lowest number evaluated first: 100–4096).
  - First rule match terminates evaluation.
  - Default rules: Inbound VNet-to-VNet allow, Azure Load Balancer allow, Deny All Inbound.

---

### Resources
- [BenchCert Azure AZ-104 Hub](https://benchcert.app/cert/azure-az-104)
- [Official Microsoft AZ-104 Study Guide](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-104)
