# 📚 IT & Cloud Certification Cheat Sheets & Blueprint Traps

A curated, developer-grade collection of architecture cheat sheets, protocol comparison tables, port references, and root-cause exam trap breakdowns for professional Cloud, Cybersecurity, Networking, and Linux certifications.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Interactive Practice: BenchCert](https://img.shields.io/badge/Interactive%20Drills-BenchCert.app-6366f1.svg)](https://benchcert.app)
[![No Braindumps](https://img.shields.io/badge/100%25%20Original-No%20Braindumps-10b981.svg)](https://benchcert.app/terms)

> **Pro Tip**: Use these markdown sheets for rapid review. To test your knowledge under real exam conditions with sub-200ms keyboard navigation and in-question Socratic AI hints (`H` key), practice with the [BenchCert Active Recall Engine](https://benchcert.app). You can try a [5-Question Free Instant Drill](https://benchcert.app/try) with zero registration.

---

## 🧭 Certification Track Quick Navigation

| Exam Track | Code | Vendor | Focus Area | Cheat Sheet | Interactive Drills |
| :--- | :--- | :--- | :--- | :---: | :---: |
| **AWS Solutions Architect Associate** | `SAA-C03` | AWS | Distributed resilient architectures & storage | [View Sheet](cheatsheets/aws-saa-c03.md) | [Start SAA Drills](https://benchcert.app/cert/aws-saa-c03) |
| **CompTIA Security+** | `SY0-701` | CompTIA | Core protocols, enterprise threats & IAM | [View Sheet](cheatsheets/comptia-sec-701.md) | [Start Sec+ Drills](https://benchcert.app/cert/comptia-sec-701) |
| **CompTIA Network+** | `N10-009` | CompTIA | Subnetting, routing, OSI model & troubleshooting | [View Sheet](cheatsheets/comptia-net-009.md) | [Start Net+ Drills](https://benchcert.app/cert/comptia-net-009) |
| **Cisco CCNA** | `200-301` | Cisco | Switching, OSPF, VLANs & automation | [View Sheet](cheatsheets/cisco-ccna-200-301.md) | [Start CCNA Drills](https://benchcert.app/cert/cisco-ccna-200-301) |
| **Microsoft Azure Administrator** | `AZ-104` | Microsoft | Entra ID, VNets, storage & compute | [View Sheet](cheatsheets/azure-az-104.md) | [Start AZ-104 Drills](https://benchcert.app/cert/azure-az-104) |
| **Google Cloud Associate Cloud Engineer** | `ACE` | Google Cloud | GKE, Cloud Run, IAM & VPC architecture | [View Sheet](cheatsheets/gcp-ace.md) | [Start GCP Drills](https://benchcert.app/cert/gcp-ace) |
| **AWS Cloud Practitioner** | `CLF-C02` | AWS | Cloud concepts, billing & shared responsibility | [View Sheet](cheatsheets/aws-saa-c03.md) | [Start CLF Drills](https://benchcert.app/cert/aws-clf-c02) |
| **CompTIA CySA+** | `CS0-003` | CompTIA | Threat hunting, SIEM & incident response | [View Sheet](cheatsheets/comptia-sec-701.md) | [Start CySA+ Drills](https://benchcert.app/cert/comptia-cysa-003) |
| **CompTIA Linux+** | `XK0-005` | CompTIA | System administration, bash, storage & git | [View Sheet](cheatsheets/cisco-ccna-200-301.md) | [Start Linux+ Drills](https://benchcert.app/cert/comptia-linux-005) |
| **ISC2 CISSP** | `CISSP` | ISC2 | 8 Security domains & enterprise risk governance | [View Sheet](cheatsheets/comptia-sec-701.md) | [Start CISSP Drills](https://benchcert.app/cert/isc2-cissp) |

---

## ⚡ High-Yield Architecture Decision Matrices

### 1. AWS Inter-VPC & Hybrid Connectivity
| Requirement | Recommended Solution | Data Transfer Cost | Throughput / Scalability |
| :--- | :--- | :--- | :--- |
| **Connect 2 VPCs directly** | **VPC Peering** | Standard AZ/cross-region egress | Single-hop, no bottleneck, no transitive routing |
| **Connect 10+ VPCs with transitive routing** | **AWS Transit Gateway (TGW)** | Hourly attachment fee + $0.02/GB | Up to 50 Gbps per attachment |
| **Privately access a SaaS / internal service** | **AWS PrivateLink (Interface Endpoint)** | Hourly ENI fee + $0.01/GB | Network Load Balancer backed, no IP overlap issues |
| **Zero-cost S3 / DynamoDB private access** | **Gateway VPC Endpoint** | **$0.00 / GB** (Free) | Routed via VPC route table entries |
| **Dedicated private connection from on-prem** | **AWS Direct Connect (DX)** | Port hour + reduced data out | 1 Gbps, 10 Gbps, or 100 Gbps dedicated physical line |

---

### 2. Core Security & Authentication Protocols
| Protocol | Port(s) | Layer | Key Characteristics & Exam Traps |
| :--- | :---: | :---: | :--- |
| **LDAP / LDAPS** | `389` / `636` (TCP) | App | Plaintext vs. TLS encrypted directory queries. Exam trap: 636 is LDAPS. |
| **Kerberos** | `88` (TCP/UDP) | App | Ticket Granting Service (TGS) authentication. Symmetric key time-sensitive timestamps (max 5 min clock skew). |
| **RADIUS** | `1812` (Auth), `1813` (Acct) | UDP | Centralized AAA. Encrypts **only** the password field (not the whole packet). |
| **TACACS+** | `49` (TCP) | TCP | Cisco proprietary / open standard AAA. Encrypts the **entire** body of the packet and separates AAA components. |
| **Syslog / Syslog over TLS** | `514` (UDP) / `6514` (TCP) | App | Standard log forwarding. Exam trap: standard syslog is cleartext UDP 514; secure encrypted syslog is TCP 6514. |
| **SAML 2.0** | `443` (HTTPS) | App | XML-based federation protocol widely used in enterprise enterprise SSO (IDP $\rightarrow$ SP). |
| **OIDC / OAuth 2.0** | `443` (HTTPS) | App | JSON / REST-based federation. OAuth 2.0 handles **authorization** (scopes); OIDC adds the **identity/authentication** layer via JWT ID tokens. |

---

### 3. IPv4 Subnetting Quick Calculation Reference
| CIDR | Subnet Mask | Total IPs | Usable Hosts | Block Size (Magic Number) |
| :---: | :--- | :---: | :---: | :---: |
| `/24` | `255.255.255.0` | 256 | 254 | 1 (in 3rd octet) / 256 |
| `/25` | `255.255.255.128` | 128 | 126 | 128 |
| `/26` | `255.255.255.192` | 64 | 62 | 64 |
| `/27` | `255.255.255.224` | 32 | 30 | 32 |
| `/28` | `255.255.255.240` | 16 | 14 | 16 |
| `/29` | `255.255.255.248` | 8 | 6 | 8 |
| `/30` | `255.255.255.252` | 4 | 2 (P2P WAN Links) | 4 |

> **AWS VPC Rule**: In AWS subnets, **5 IP addresses** are reserved per subnet (Network `.0`, VPC Router `.1`, DNS `.2`, Future `.3`, and Broadcast `.255`). A `/28` subnet has $16 - 5 = 11$ usable IPs.

---

## 🛠️ Community & Interactive Study Resources
- **Active Recall Drills**: [BenchCert Practice Hub](https://benchcert.app/practice)
- **Certification Guides & Blueprints**: [BenchCert Cert Catalog](https://benchcert.app/catalog)
- **Comparison Against Legacy Question Banks**: [BenchCert vs. Tutorials Dojo](https://benchcert.app/vs/tutorials-dojo) • [BenchCert vs. Whizlabs](https://benchcert.app/vs/whizlabs) • [BenchCert vs. MeasureUp](https://benchcert.app/vs/measureup)
- **Instant 5-Question Free Trial**: [Try 5 Scenarios Free](https://benchcert.app/try)

## 📄 License
This collection is open source and available under the [MIT License](LICENSE).
