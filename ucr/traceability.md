## Requirements Traceability Matrix

This section maps each requirement to the use cases that depend on it.
Column abbreviations correspond to the use cases in the preceding section:

| Code | Use Case |
|------|----------|
| DS | Trusted data sharing in a data space |
| CR | Company representative acting on behalf of a company |
| KYB | Know your business partner — KYB/KYS/KYC due diligence |
| KYS | Know your supplier — KYS supplier onboarding |
| KYC | Know your customer — KYC corporate onboarding |
| TAX | Foreign tax declaration |
| EDU | Issuing micro-credentials and verified skills |
| TRP | Authentication and access for transport |
| INV | eInvoicing |
| ADS | Autonomous driving and trusted software release |
| AITRS | Trusted AI for agentic B2B commerce and treasury |
| PHYAI | Trusted Physical AI for robots in Japanese smart manufacturing |
| PQC | PQC-resilient U.S.-German digital data sharing corridor |
| AUTO | Automotive supply chain and battery passport |
| EVC | EV charging and legal persons |
| AIGRID | Trusted AI for energy grid forecasting and automated flexibility activation |
| DCP | Digital Copyright Passport for IP creators and licensors |

### Group A — Core Trust Primitives

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-001 Authentication / proof of control | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-002 Real-time credential status and revocation | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-003 Verifiable audit trail | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-004 Cannot be administratively denied | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

### Group B — Identity

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-005 Legal person identity | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | | | ✓ | ✓ | ✓ | ✓ | | ✓ | ✓ | ✓ | ✓ |
| REQ-006 Decentralized / self-issued | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-007 Inter-jurisdictional recognition | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | | ✓ | | | ✓ | ✓ |
| REQ-008 Employee and contact-person binding | | | | | ✓ | | | | | | | | | | | | |
| REQ-009 Natural-person-to-legal-person binding | | ✓ | | | ✓ | ✓ | | ✓ | | | | | | | | | |

### Group C — Authorization and Delegation

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-010 Mutual authentication | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-011 Credential delegation and scoped authorization | ✓ | ✓ | | | ✓ | ✓ | | ✓ | | ✓ | | | | | ✓ | | |
| REQ-012 User-controlled selective disclosure | ✓ | ✓ | ✓ | ✓ | ✓ | | ✓ | | | | | | ✓ | ✓ | | ✓ | ✓ |
| REQ-013 Policy-driven attestation requests | | | | ✓ | ✓ | | | | | | | | | | | | |
| REQ-014 Revocation without intermediary | | ✓ | | | | | | | | | | | | | | | ✓ |

### Group D — Interoperability and Portability

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-015 Credential portability across platforms | ✓ | ✓ | ✓ | ✓ | | | ✓ | | | | | | | | ✓ | | ✓ |
| REQ-016 Survives issuing organisation changes | ✓ | ✓ | | ✓ | ✓ | | ✓ | | | | | | | | | | |
| REQ-017 Survives relationship with service provider | | | ✓ | | | ✓ | | | ✓ | | | | | | ✓ | | ✓ |
| REQ-018 Machine-to-machine data exchange | | | | | | ✓ | | ✓ | ✓ | ✓ | ✓ | ✓ | | ✓ | ✓ | ✓ | |
| REQ-019 Human-centred interoperability | | | | | | | ✓ | ✓ | | | | | | | | | |
| REQ-020 IBAN binding to verified legal identity | | | | ✓ | | | | | | | | | | | | | |

### Group E — Cryptography and Integrity

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-021 Qualified electronic signature | | | | | | ✓ | | ✓ | | | | | | | | | |
| REQ-022 Qualified electronic seal | | | | | | ✓ | | | ✓ | | ✓ | | | | ✓ | | |

### Group F — AI Governance and Autonomous Systems

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-023 AI Service Passport | | | | | | | | | | ✓ | ✓ | ✓ | | | | ✓ | |
| REQ-024 Agent Power of Attorney | | | | | | | | | | ✓ | ✓ | ✓ | | | | ✓ | |
| REQ-025 Agent validation credential | | | | | | | | | | ✓ | ✓ | ✓ | | | | ✓ | |
| REQ-026 Human oversight and control | | | | | | | | | | ✓ | ✓ | ✓ | | | | ✓ | |
| REQ-027 Model version control and runtime monitoring | | | | | | | | | | ✓ | ✓ | ✓ | | | | ✓ | |

### Group G — Product and Asset Identity

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-028 Digital Product Passport | | | | | | | | | | ✓ | | ✓ | | ✓ | ✓ | | |
| REQ-029 Vehicle, robot, and device identity | | | | | | | | | | ✓ | | ✓ | | ✓ | ✓ | | |
| REQ-030 Manufacturing site identity | | | | | | | | | | | | ✓ | | ✓ | | | |

### Group H — Content Authenticity and Provenance

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-032 Tamper-evident content provenance | | | | | | | | | | | | | | | | | ✓ |

### Group I — Post-Quantum Cryptography

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-033 Post-quantum cryptographic primitives | | | | | | | | | | | | | ✓ | | | | |
| REQ-034 Hybrid signatures and encryption | | | | | | | | | | | | | ✓ | | | | |
| REQ-035 Crypto-agility and algorithm metadata | | | | | | | | | | | | | ✓ | | | | |

### Group J — Market Role and Regulated Operations

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-036 Market role credentials for regulated sectors | | | | | | | | | | | ✓ | | | | ✓ | ✓ | |
| REQ-037 Public authority identity credentials | | | | | | | | | | | | | ✓ | | | | ✓ |
| REQ-038 Policy-based access control | | | | | | | | | | | ✓ | ✓ | ✓ | | | ✓ | |

### Group K — Intellectual Property and Rights Management

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV | ADS | AITRS | PHYAI | PQC | AUTO | EVC | AIGRID | DCP |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-039 Natural person creator identity | | | | | | | | | | | | | | | | | ✓ |
| REQ-040 Creator membership and IP registry credential | | | | | | | | | | | | | | | | | ✓ |
| REQ-041 Content identification and verifiable authorship credential | | | | | | | | | | | | | | | | | ✓ |
| REQ-042 Digital Copyright Passport credential | | | | | | | | | | | | | | | | | ✓ |
| REQ-043 Rights expression and machine-enforceable licence credential | | | | | | | | | | | | | | | | | ✓ |
