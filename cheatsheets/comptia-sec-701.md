# CompTIA Security+ (SY0-701) Cheat Sheet

Comprehensive revision guide for CompTIA Security+ covering cryptographic fundamentals, identity and access management, security operations, and essential port numbers.

> **Interactive Practice**: Test your readiness with validated scenario drills on [BenchCert CompTIA Security+ Guide](https://benchcert.app/cert/comptia-sec-701).

---

## 📊 Exam Blueprint & Domain Weights
- **Domain 1**: General Security Concepts (**12%**)
- **Domain 2**: Threats, Vulnerabilities, and Mitigations (**22%**)
- **Domain 3**: Security Architecture (**18%**)
- **Domain 4**: Security Operations (**28%**)
- **Domain 5**: Security Program Management and Oversight (**20%**)

**Passing Score**: 750 / 900  
**Format**: 65–90 Questions | 90 Minutes

---

## 🔒 Port Numbers You Must Memorize
| Port | Protocol | Usage / Context |
| :---: | :--- | :--- |
| **20/21** | FTP | Cleartext file transfer (21 Control, 20 Data) |
| **22** | SSH / SFTP | Secure shell, secure file transfer |
| **23** | Telnet | Unencrypted remote console (Flag as vulnerability!) |
| **25** | SMTP | Mail relay (Cleartext) |
| **53** | DNS | Domain name queries (UDP) / Zone transfers (TCP) |
| **67/68** | DHCP | IP allocation (67 Server, 68 Client) |
| **69** | TFTP | Trivial FTP (UDP, unauthenticated bootstrap) |
| **80** | HTTP | Plaintext web traffic |
| **88** | Kerberos | Active Directory ticket authentication |
| **123** | NTP | Network time synchronization (Crucial for Kerberos) |
| **143** | IMAP | Email retrieval |
| **161/162** | SNMP | Network monitoring (161 Query, 162 Trap; use v3 for auth/priv) |
| **389** | LDAP | Lightweight Directory Access (Plaintext) |
| **443** | HTTPS | Encrypted TLS web traffic |
| **445** | SMB | Windows file sharing |
| **636** | LDAPS | Secure LDAP over TLS |
| **993** | IMAPS | Secure IMAP over TLS |
| **1812/1813** | RADIUS | AAA (1812 Authentication, 1813 Accounting) |
| **3389** | RDP | Windows Remote Desktop |
| **6514** | Syslog over TLS | Encrypted system event logging |

---

## 🛡️ Authentication & Federation
- **SAML 2.0**: XML-based web SSO between Identity Provider (IdP) and Service Provider (SP).
- **OAuth 2.0**: Token-based authorization framework (grants access via scopes/access tokens; does NOT authenticate identity).
- **OIDC (OpenID Connect)**: Identity layer built on top of OAuth 2.0, providing JWT ID tokens to authenticate users.
- **MFA (Multifactor Authentication)**: Requires 2 or more distinct factor types:
  1. *Something you know* (Password, PIN)
  2. *Something you have* (Smartcard, Hardware token, Authenticator app TOTP)
  3. *Something you are* (Fingerprint, Retina, Facial biometric)
  4. *Somewhere you are* (GPS / Geolocation)
  5. *Something you do* (Typing cadence, gait analysis)

---

### Resources
- [BenchCert CompTIA Security+ Hub](https://benchcert.app/cert/comptia-sec-701)
- [Official CompTIA SY0-701 Exam Blueprint](https://www.comptia.org/certifications/security)
