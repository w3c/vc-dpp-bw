## Requirements

This section defines the normalized requirements derived from the use cases in this document.
Each requirement is assigned a stable identifier (`REQ-NNN`) and is specified with a description,
rationale, priority, and acceptance criteria. Priority levels follow [[RFC2119]]:
**MUST** denotes a mandatory requirement; **SHOULD** denotes a recommended requirement;
**MAY** denotes an optional requirement.

### Core Trust Primitives

The following requirements apply to every use case in this document and form the non-negotiable
foundation of the trust architecture.

#### REQ-001 Authentication / proof of control

**Priority:** MUST

**Description:** Every credential presentation MUST include a cryptographic proof that the presenting party controls the private key bound to the credential at the time of presentation.

**Rationale:** Without proof of control, credentials can be intercepted and replayed by unauthorized parties, making identity verification meaningless.

**Acceptance criteria:** A verifier can confirm that the presenter holds the private key bound to the credential using a challenge–response or equivalent protocol, without the presenter revealing that key.

**Used in:** All use cases.

---

#### REQ-002 Real-time credential status and revocation

**Priority:** MUST

**Description:** Every issued credential MUST carry a machine-queryable status endpoint that reflects the current validity state of the credential at the moment of verification. Verifiers MUST query the status endpoint before relying on any credential claim.

**Rationale:** Credentials may be revoked, suspended, or expired after issuance. Relying on a stale credential creates exploitable windows during which an invalidated credential is accepted.

**Acceptance criteria:** Within one verification cycle of a status change by the issuer, any verifier performing a fresh status check receives the updated status. Cached status older than the defined validity window is not accepted for high-assurance verifications.

**Used in:** All use cases.

---

#### REQ-003 Verifiable audit trail

**Priority:** MUST

**Description:** Every credential issuance, presentation, delegation, and revocation event MUST produce a tamper-evident audit record that authorized parties can query to reconstruct the event sequence.

**Rationale:** Accountability requires that all trust decisions can be traced to specific events, actors, and credentials. Audit trails enable compliance verification, dispute resolution, and forensic analysis.

**Acceptance criteria:** An auditor can reconstruct the complete chain of credential events for any transaction, including which credentials were presented, by whom, to whom, and when, from the audit log alone.

**Used in:** All use cases.

---

#### REQ-004 Cannot be administratively denied

**Priority:** MUST

**Description:** A holder's ability to present a validly issued, non-revoked credential MUST NOT depend on the continued cooperation of the issuer, the wallet provider, or any intermediary platform. Administrative blocking of credential presentation without revocation is not permitted.

**Rationale:** If an issuer, platform operator, or government can block credential presentation without revoking the credential itself, the credential system provides no meaningful autonomy to the holder.

**Acceptance criteria:** A credential holder can present their credential to a conformant verifier even if the original issuing platform is offline, the issuer has dissolved, or the holder's contractual relationship with a service provider has ended.

**Used in:** All use cases.

---

### Identity

#### REQ-005 Legal person identity

**Priority:** MUST

**Description:** A business wallet MUST be capable of holding and presenting a verifiable credential attesting the legal identity of the organisation it represents, issued by an authoritative business registry. The credential MUST include at minimum the legal name, registered identifier, and jurisdiction of registration.

**Rationale:** Machine-verifiable legal identity is the foundation of business-to-business trust. Without it, relying parties cannot confirm they are interacting with a legitimate registered entity.

**Acceptance criteria:** A verifier can resolve the credential issuer's identifier against an authoritative business register and confirm the credential's cryptographic signature without contacting the issuing organisation directly.

**Used in:** Trusted data sharing, Company representative, Know your business partner, Know your supplier, Know your customer, Foreign tax declaration, e-Invoicing.

---

#### REQ-006 Decentralized / self-issued credentials

**Priority:** MUST

**Description:** The credential ecosystem MUST support issuance by the credential subject or by any qualified issuer without requiring advance registration of each issuer with a central authority. Issuer verification MUST rely solely on cryptographic proof and resolvable identifiers.

**Rationale:** Centralized issuer registries create single points of failure and gatekeeping. Decentralized issuance allows any qualified authority to issue verifiable credentials discoverable through open protocols.

**Acceptance criteria:** A verifier can verify a credential from an issuer not previously registered with the verifier by resolving the issuer's decentralized identifier and confirming the cryptographic signature.

**Used in:** Trusted data sharing, Company representative, Know your business partner, Know your supplier, Know your customer, Foreign tax declaration, Issuing micro-credentials, Authentication and access for transport, e-Invoicing.

---

#### REQ-007 Inter-jurisdictional recognition

**Priority:** MUST

**Description:** Credentials issued by authorities in one jurisdiction MUST be verifiable by relying parties in other jurisdictions without re-issuance, notarisation, or manual translation. Issuer identifiers MUST be resolvable through shared or federated trust registries.

**Rationale:** Cross-border business activity is fundamental to the EU single market and international trade. Requiring re-issuance or notarisation for each jurisdiction creates prohibitive administrative overhead and delay.

**Acceptance criteria:** A verifier in jurisdiction B verifies a credential issued by an authority in jurisdiction A by resolving the issuer's identifier against an EU or bilateral trust registry, without a certified translation or apostille.

**Used in:** Trusted data sharing, Company representative, Know your business partner, Know your supplier, Know your customer, Foreign tax declaration, Issuing micro-credentials, Authentication and access for transport, e-Invoicing.

---

#### REQ-008 Employee and contact-person binding

**Priority:** SHOULD

**Description:** A business wallet MUST be capable of issuing a credential that verifiably binds a named natural person to a role or function within the organisation, signed by the organisation's wallet.

**Rationale:** Relying parties need to verify not only the organisation's identity but also the identity and role of the individual acting on its behalf, to satisfy AML, KYC, and operational requirements.

**Acceptance criteria:** A verifier confirms that a natural person presenting a credential is verifiably linked to the named organisation in a specified role, with the binding signed by the organisation's wallet.

**Used in:** Know your customer — KYC corporate onboarding.

---

#### REQ-009 Natural-person-to-legal-person binding

**Priority:** MUST

**Description:** The credential ecosystem MUST support credentials that bind a natural person's verified identity to a legal person, specifying the scope of authority the natural person holds on behalf of the legal person, the validity period, and any constraints.

**Rationale:** Representatives act on behalf of organisations in regulated contexts. Machine-verifiable binding enables automated verification of mandate scope without paper powers of attorney.

**Acceptance criteria:** A verifier confirms both the natural person's identity and their authority to act for the legal person, including scope and validity period, in a single credential presentation without paper or notarisation.

**Used in:** Company representative, Foreign tax declaration, Know your customer, Authentication and access for transport.

---

### Authorization and Delegation

#### REQ-010 Mutual authentication

**Priority:** MUST

**Description:** Before a credential presentation is requested, the relying party MUST present its own verified identity to the credential holder, enabling the holder to confirm they are interacting with a legitimate, identified party before disclosing any claims.

**Rationale:** One-sided authentication enables phishing attacks where fraudulent verifiers collect credentials. Mutual authentication ensures both parties are identified before any data is disclosed.

**Acceptance criteria:** A credential holder can verify the relying party's identity before disclosing any credential claims. An interaction with an unverified relying party is rejected by the holder's wallet.

**Used in:** Trusted data sharing, Company representative, Know your business partner, Know your supplier, Know your customer, Foreign tax declaration, Authentication and access for transport, e-Invoicing.

---

#### REQ-011 Credential delegation and scoped authorization

**Priority:** MUST

**Description:** A credential holder MUST be able to issue a derived credential that delegates a defined subset of their authority to another party, with explicit scope constraints on the permitted actions, the validity period, and the authorized recipient.

**Rationale:** Organisations frequently authorize representatives, agents, or automated systems to act on their behalf. Delegation MUST be scoped to prevent unauthorized actions beyond the granted authority.

**Acceptance criteria:** A delegated credential specifies the authorized acts, the authorized party, the validity period, and any additional constraints. A verifier confirms that a presented action falls within the delegated scope and that the delegation is current.

**Used in:** Trusted data sharing, Company representative, Foreign tax declaration, Authentication and access for transport, Know your customer.

---

#### REQ-012 User-controlled selective disclosure

**Priority:** MUST

**Description:** A credential holder MUST be able to present only a specified subset of the claims in a credential to a relying party, without revealing claims not needed for the verification purpose and without the verifier being able to infer undisclosed claims.

**Rationale:** Minimizing disclosed data reduces privacy risk and complies with the data minimization principle of GDPR. Relying parties should receive only what they have a legitimate need to verify.

**Acceptance criteria:** A credential holder generates a presentation including specific claims while provably not disclosing others. The verifier receives only the disclosed claims and cannot infer values of undisclosed claims from the presentation.

**Used in:** Trusted data sharing, Company representative, Know your business partner, Know your supplier, Know your customer, Issuing micro-credentials.

---

#### REQ-013 Policy-driven attestation requests

**Priority:** SHOULD

**Description:** A verifier MUST be able to express a structured, machine-readable credential request specifying which credential types, claims, and issuers it requires. The holder's wallet MUST evaluate the request and present the result to the holder for review before any disclosure.

**Rationale:** Static credential presentation bundles are inefficient and over-disclose. Policy-driven requests enable relying parties to ask for exactly what they need and holders to respond with the minimum required set.

**Acceptance criteria:** A relying party sends a structured presentation request. The holder's wallet evaluates the request, shows the holder what will be disclosed including the stated purpose, and requires explicit consent before responding.

**Used in:** Know your supplier, Know your customer.

---

#### REQ-014 Revocation without intermediary

**Priority:** MUST

**Description:** A credential issuer MUST be able to revoke a credential such that the revocation is detectable by any verifier performing a fresh status check, without requiring a central intermediary to propagate or approve the revocation.

**Rationale:** Revocation that depends on a platform operator or intermediary gives that party veto power over the issuer's control. Direct revocation preserves issuer authority and is more resilient to platform failures.

**Acceptance criteria:** An issuer updates a credential's status endpoint directly. Any verifier querying that endpoint within one verification cycle receives the revoked status without requiring notification from any intermediary.

**Used in:** Company representative acting on behalf of a company.

---

### Interoperability and Portability

#### REQ-015 Credential portability across platforms

**Priority:** MUST

**Description:** Credentials issued by one platform or wallet provider MUST be presentable to verifiers using different platforms and wallet implementations, without migration, re-issuance, or proprietary format conversion.

**Rationale:** Vendor lock-in undermines the value of verifiable credentials. Holders must be able to change wallet providers and present credentials to verifiers on any conformant platform.

**Acceptance criteria:** A credential issued by system A is accepted by a verifier on system B with no prior bilateral arrangement beyond conformance to the shared credential format and trust registry.

**Used in:** Trusted data sharing, Company representative, Know your business partner, Know your supplier, Issuing micro-credentials.

---

#### REQ-016 Survives issuing organisation changes

**Priority:** MUST

**Description:** Credentials MUST remain verifiable even if the issuing organisation changes its name, merges with another entity, is acquired, or has its original identifier retired, provided a published identifier transition record is maintained.

**Rationale:** Business continuity requires that credential validity is not contingent on the continued existence of the issuer's original legal entity or platform instance.

**Acceptance criteria:** A verifier verifies a credential whose issuer has undergone organisational changes by following a published identifier transition record that links the old identifier to the successor. No re-issuance is required.

**Used in:** Trusted data sharing, Company representative, Know your supplier, Know your customer, Issuing micro-credentials.

---

#### REQ-017 Survives relationship with service provider

**Priority:** MUST

**Description:** A holder's credentials and their verifiability MUST NOT depend on the continued operation of any specific service provider, access point, wallet host, or intermediary platform. Trust MUST be anchored to the issuer's cryptographic identifier, not the platform.

**Rationale:** Service providers change, merge, and cease operations. Credential trust anchored to a platform rather than the issuer is lost when the platform changes.

**Acceptance criteria:** When a holder migrates from one service provider to another, existing credentials remain valid and presentable without re-issuance. Verifiers continue to accept the credentials using the same issuer identifiers.

**Used in:** Know your business partner, Foreign tax declaration, e-Invoicing.

---

#### REQ-018 Machine-to-machine data exchange

**Priority:** MUST

**Description:** The credential ecosystem MUST support automated, non-interactive credential presentation and verification between systems without requiring human intervention for each individual exchange.

**Rationale:** High-volume B2B processes such as invoicing, tax filings, and gate access control require automated verification at scale. Human-in-the-loop for every credential check is not operationally viable.

**Acceptance criteria:** A sending system presents credentials to a receiving system, which verifies them and takes an automated action, without human intervention, at a throughput consistent with the operational context.

**Used in:** Foreign tax declaration, Authentication and access for transport, e-Invoicing.

---

#### REQ-019 Human-centred interoperability

**Priority:** SHOULD

**Description:** Credential presentation flows MUST be usable by non-technical users without requiring understanding of cryptographic protocols, trust registries, or credential formats. The wallet interface MUST abstract technical complexity.

**Rationale:** Verifiable credentials achieve adoption only if end users can use them as intuitively as presenting a physical document. Technical barriers prevent uptake by the intended user population.

**Acceptance criteria:** A holder with no technical background locates, selects, and presents the correct credential(s) to a verifier using a standard wallet interface within a time comparable to presenting a physical document.

**Used in:** Issuing micro-credentials, Authentication and access for transport.

---

#### REQ-020 IBAN binding to verified legal identity

**Priority:** MUST

**Description:** A payment account credential MUST cryptographically bind the IBAN or other payment account identifier to the verified legal identity of the account holder, such that any substitution of the account number is detectable.

**Rationale:** Invoice fraud and business email compromise attacks frequently succeed by substituting a payment account number in transit. Cryptographic binding enables tamper detection at the point of invoice processing.

**Acceptance criteria:** A verifier confirms that the IBAN presented in a payment credential is cryptographically bound to the same legal entity as the invoicing credential. Substitution of the account number breaks the binding and triggers automatic rejection.

**Used in:** Know your supplier — KYS supplier onboarding.

---

### Cryptography and Integrity

#### REQ-021 Qualified electronic signature

**Priority:** MUST

**Description:** The credential ecosystem MUST support the production and verification of qualified electronic signatures (QES) as defined under eIDAS 2.0, enabling natural persons to sign documents with cross-border legal equivalence to handwritten signatures.

**Rationale:** Many regulated processes — tax filings, customs declarations, contract execution — require legally binding electronic signatures. QES ensures cross-border legal recognition under EU law without notarisation.

**Acceptance criteria:** A document signed with a QES derived from a wallet is accepted by an EU public authority or private verifier as legally equivalent to a handwritten signature, without a separate notarisation step.

**Used in:** Foreign tax declaration, Authentication and access for transport.

---

#### REQ-022 Qualified electronic seal

**Priority:** MUST

**Description:** The credential ecosystem MUST support the production and verification of qualified electronic seals (QeSeal) as defined under eIDAS 2.0, enabling legal persons to seal documents with machine-verifiable evidence of organisational origin and content integrity.

**Rationale:** Legal persons cannot sign in the way natural persons do. Qualified seals provide equivalent assurance for organisational documents such as invoices and regulatory submissions.

**Acceptance criteria:** A document sealed with a QeSeal from a business wallet is accepted by an EU authority or private verifier as evidence of organisational origin and integrity, without requiring a separate authentication step.

**Used in:** Foreign tax declaration, e-Invoicing.
