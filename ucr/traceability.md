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

### Group A — Core Trust Primitives

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-001 Authentication / proof of control | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-002 Real-time credential status and revocation | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-003 Verifiable audit trail | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-004 Cannot be administratively denied | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

### Group B — Identity

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-005 Legal person identity | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | | | ✓ |
| REQ-006 Decentralized / self-issued | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-007 Inter-jurisdictional recognition | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| REQ-008 Employee and contact-person binding | | | | | ✓ | | | | |
| REQ-009 Natural-person-to-legal-person binding | | ✓ | | | ✓ | ✓ | | ✓ | |

### Group C — Authorization and Delegation

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-010 Mutual authentication | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | | ✓ | ✓ |
| REQ-011 Credential delegation and scoped authorization | ✓ | ✓ | | | ✓ | ✓ | | ✓ | |
| REQ-012 User-controlled selective disclosure | ✓ | ✓ | ✓ | ✓ | ✓ | | ✓ | | |
| REQ-013 Policy-driven attestation requests | | | | ✓ | ✓ | | | | |
| REQ-014 Revocation without intermediary | | ✓ | | | | | | | |

### Group D — Interoperability and Portability

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-015 Credential portability across platforms | ✓ | ✓ | ✓ | ✓ | | | ✓ | | |
| REQ-016 Survives issuing organisation changes | ✓ | ✓ | | ✓ | ✓ | | ✓ | | |
| REQ-017 Survives relationship with service provider | | | ✓ | | | ✓ | | | ✓ |
| REQ-018 Machine-to-machine data exchange | | | | | | ✓ | | ✓ | ✓ |
| REQ-019 Human-centred interoperability | | | | | | | ✓ | ✓ | |
| REQ-020 IBAN binding to verified legal identity | | | | ✓ | | | | | |

### Group E — Cryptography and Integrity

| Requirement | DS | CR | KYB | KYS | KYC | TAX | EDU | TRP | INV |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| REQ-021 Qualified electronic signature | | | | | | ✓ | | ✓ | |
| REQ-022 Qualified electronic seal | | | | | | ✓ | | | ✓ |
