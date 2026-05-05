## Vocabulary Requirements

This section identifies the vocabulary and data model requirements that emerge from the use cases in this document. Standardized vocabularies are essential for interoperability, enabling credentials issued by different authorities and platforms to be understood consistently across jurisdictions and sectors.

### Core Organization and Identity Vocabularies

#### VOC-001 Legal Entity Identifier (LEI)

**Description:** Standard vocabulary for legal entity identification using the Global LEI System.

**Rationale:** Cross-border business identification requires a globally unique, authoritative identifier for legal persons that is resolvable and verifiable.

**Required fields:**
- LEI code (20-character alphanumeric)
- Legal name
- Jurisdiction of registration
- Registration date
- Entity status
- Parent/subsidiary relationships

**Standards:** ISO 17442, GLEIF data format

**Used in:** Know your business partner, Know your supplier, Know your customer, Trusted AI for agentic B2B commerce and treasury, Trusted AI for energy grid forecasting.

---

#### VOC-002 Business Registration Credentials

**Description:** Vocabulary for business registry data including registration number, legal form, registered address, and beneficial ownership.

**Rationale:** Each jurisdiction has its own business registration system. A common vocabulary enables cross-border recognition while preserving local identifiers.

**Required fields:**
- Registration number (jurisdiction-specific)
- Legal name (official and trading names)
- Legal form (GmbH, Ltd, S.A., etc.)
- Registered address
- Date of registration
- Registration authority
- Business registry URL
- NACE/ISIC sector codes
- Beneficial ownership data (where required)

**Standards:** BRIS (Business Registers Interconnection System), eIDAS trust services, ebXML Registry

**Used in:** Trusted data sharing, Company representative, Know your business partner, Know your supplier, Know your customer, Foreign tax declaration, e-Invoicing.

---

#### VOC-003 Tax and VAT Credentials

**Description:** Vocabulary for tax identification numbers, VAT registration, and tax compliance status.

**Rationale:** Cross-border transactions require verifiable tax status to ensure compliance with VAT, withholding tax, and treaty obligations.

**Required fields:**
- Tax Identification Number (TIN)
- VAT identification number
- Tax jurisdiction
- VAT registration status
- Tax residence status
- Treaty eligibility
- Tax compliance certificate status

**Standards:** OECD CRS, EU VAT Information Exchange System (VIES), ISO 3166 country codes

**Used in:** Know your supplier, Know your customer, Foreign tax declaration, e-Invoicing, EV charging and legal persons, Trusted AI for energy grid forecasting.

---

### Authorization and Delegation Vocabularies

#### VOC-004 Power of Representation (PoR)

**Description:** Vocabulary for natural person authorization to represent a legal entity.

**Rationale:** Company representatives need machine-verifiable proof of their authority to act on behalf of organizations.

**Required fields:**
- Representative identity (natural person)
- Represented entity (legal person)
- Scope of authority (general representation, specific transactions, domains)
- Authorized actions (signing, contracting, financial transactions)
- Validity period
- Constraints and limits
- Signatory role

**Standards:** eIDAS Qualified Certificates for Electronic Signatures and Seals, W3C Verifiable Credentials Data Model

**Used in:** Company representative, Know your customer, Foreign tax declaration, Authentication and access for transport.

---

#### VOC-005 Power of Attorney (PoA) and Agent PoA

**Description:** Vocabulary for delegated authority including both human-to-human and organization-to-agent delegation.

**Rationale:** Delegation relationships require precise scope definition, especially when delegating to AI agents or automated systems.

**Required fields:**
- Delegator identity
- Delegate identity (natural person, legal person, or AI agent)
- Delegation type (general PoA, limited PoA, Agent PoA)
- Authorized actions
- Scope constraints (geographic, temporal, financial limits, resource access)
- Transaction thresholds
- Human approval requirements
- Validity period
- Revocation conditions

**Standards:** W3C Verifiable Credentials Data Model, OAuth 2.0 scopes, XACML policy language

**Used in:** Trusted data sharing, Company representative, Foreign tax declaration, Autonomous driving and trusted software release, Trusted AI for agentic B2B commerce and treasury, Trusted Physical AI for robots in Japanese smart manufacturing, Trusted AI for energy grid forecasting.

---

### AI Governance Vocabularies

#### VOC-006 AI Service Passport (AISP)

**Description:** Vocabulary for AI service metadata, validation status, operational parameters, and governance controls.

**Rationale:** AI agents and autonomous systems require standardized metadata to enable verification of their capabilities, limitations, and safety controls.

**Required fields:**
- AI service identifier
- Service operator
- Model family and version
- Software hash
- Training data classes and sources
- Operational Design Domain (ODD)
- Validation status
- TEVV (Test, Evaluation, Validation, and Verification) evidence
- Human oversight requirements
- Runtime monitoring configuration
- Incident history
- Update history
- Safety case reference
- Conformity assessments

**Standards:** EU AI Act requirements, NIST AI Risk Management Framework, ISO/IEC 42001, IEEE 7010, ISO/IEC 23894

**Used in:** C2PA and CAWG for trusted fashion imagery, Autonomous driving and trusted software release, Trusted AI for agentic B2B commerce and treasury, Trusted Physical AI for robots in Japanese smart manufacturing, Trusted AI for energy grid forecasting.

---

#### VOC-007 Model Metadata and Provenance

**Description:** Vocabulary for AI model identification, versioning, training data, and lineage.

**Rationale:** Model-specific identification enables targeted revocation and supports transparency requirements under AI regulations.

**Required fields:**
- Model identifier (unique, resolvable)
- Model version (semantic versioning)
- Model family
- Training data classes
- Training data sources and provenance
- Data licenses
- Model architecture
- Software dependencies (SBOM)
- Release date
- Deprecation status
- Known limitations
- Approved use cases
- Prohibited use cases

**Standards:** Model Cards (Google), System Cards (OpenAI), ML Model Metadata (Linux Foundation), SPDX for AI/ML

**Used in:** C2PA and CAWG for trusted fashion imagery, Autonomous driving and trusted software release, Trusted AI for agentic B2B commerce and treasury, Trusted Physical AI for robots in Japanese smart manufacturing, Trusted AI for energy grid forecasting.

---

#### VOC-008 TEVV and Validation Credentials

**Description:** Vocabulary for test results, validation evidence, conformity assessments, and certification status for AI systems.

**Rationale:** Independent validation requires standardized formats for test evidence and conformity declarations.

**Required fields:**
- Validation body identifier
- Validation scope
- Test methodology
- Test scenarios and results
- Performance metrics
- Safety metrics
- Bias and fairness metrics
- Robustness tests
- Validation date
- Validity period
- Conformity standards (EU AI Act, NIST AI RMF, ISO/IEC 42001)
- Limitations and exclusions

**Standards:** EU AI Act conformity assessment, NIST AI RMF, ISO/IEC 42001, ISO/IEC 23894, IEC 61508

**Used in:** Autonomous driving and trusted software release, Trusted AI for agentic B2B commerce and treasury, Trusted Physical AI for robots in Japanese smart manufacturing, Trusted AI for energy grid forecasting.

---

### Product and Supply Chain Vocabularies

#### VOC-009 Digital Product Passport (DPP)

**Description:** Vocabulary for product identity, lifecycle data, conformity status, and supply chain provenance.

**Rationale:** Regulatory requirements (EU Ecodesign, Battery Regulation, CBAM) mandate machine-readable product data throughout the lifecycle.

**Required fields:**
- Product identifier (GTIN, VIN, serial number)
- Manufacturer identity
- Manufacturing site
- Manufacturing date
- Model designation
- Technical specifications
- Conformity declarations
- Certifications
- Material composition
- Carbon footprint
- Recyclability data
- Repair and maintenance data
- End-of-life instructions
- Supply chain provenance

**Standards:** EU Digital Product Passport, GS1 Standards, ISO 22745, ECLASS, IEC 61406

**Used in:** Autonomous driving and trusted software release, Trusted Physical AI for robots in Japanese smart manufacturing, Automotive supply chain and battery passport, EV charging and legal persons.

---

#### VOC-010 Battery Passport

**Description:** Specialized DPP vocabulary for batteries including chemistry, capacity, state of health, due diligence, and recycling data.

**Rationale:** EU Battery Regulation requires specific data for battery identification, performance monitoring, and lifecycle management.

**Required fields:**
- Battery identifier
- Battery category (EV, industrial, portable)
- Chemistry (NMC, LFP, etc.)
- Nominal capacity
- State of Health (SoH)
- Cycle count
- Manufacturing date and location
- Cell supplier and batch
- Due diligence evidence (responsible sourcing)
- Carbon footprint
- Recycled content
- Hazardous substances
- Dismantling instructions
- Collection and recycling information

**Standards:** EU Battery Regulation (EU) 2023/1542, GBA Battery Passport, IEC 62619

**Used in:** Automotive supply chain and battery passport.

---

#### VOC-011 Conformity and Certification

**Description:** Vocabulary for conformity declarations, test reports, and certification credentials.

**Rationale:** Supply chain verification requires machine-readable conformity evidence from accredited bodies.

**Required fields:**
- Certificate identifier
- Certification body
- Accreditation status
- Certification standard (ISO 9001, IATF 16949, ISO 14001, etc.)
- Scope of certification
- Certified entity
- Certified sites
- Issue date
- Expiry date
- Surveillance status
- Non-conformities

**Standards:** ISO/IEC 17065, ISO/IEC 17025, European Accreditation (EA), International Accreditation Forum (IAF)

**Used in:** Know your supplier, Automotive supply chain and battery passport, Trusted Physical AI for robots in Japanese smart manufacturing.

---

### Transport and Mobility Vocabularies

#### VOC-012 Vehicle Identity and Credentials

**Description:** Vocabulary for vehicle identification, technical specifications, type approval, and operational authorization.

**Rationale:** Autonomous and connected vehicles require machine-verifiable identity and authorization for road use and infrastructure access.

**Required fields:**
- Vehicle Identification Number (VIN)
- Registration number
- Manufacturer
- Model and variant
- Type approval number
- Homologation status
- Mass and dimensions
- Propulsion type
- Autonomous capability level (SAE J3016)
- Insurance status
- Operator identity
- Operating permits

**Standards:** ISO 3779 (VIN), ISO 4030, UN Regulation on Automated Driving Systems, SAE J3016

**Used in:** Autonomous driving and trusted software release, EV charging and legal persons.

---

#### VOC-013 EVSE and Charging Session

**Description:** Vocabulary for Electric Vehicle Supply Equipment (EVSE) identity, capabilities, charging sessions, and billing data.

**Rationale:** EV charging roaming requires standardized session records and billing data across multiple operators and platforms.

**Required fields:**
- EVSE identifier
- Charge Point Operator (CPO) identity
- E-Mobility Service Provider (eMSP) identity
- Location (coordinates, address)
- Connector types and power levels
- Availability status
- Session identifier
- Vehicle identifier
- Start/end timestamp
- Energy delivered (kWh)
- Metering data (signed)
- Tariff reference
- Cost
- Payment account
- Renewable energy claim

**Standards:** OCPI (Open Charge Point Interface), OCPP (Open Charge Point Protocol), ISO 15118, EMIR (European Metering Instrument Regulation)

**Used in:** EV charging and legal persons.

---

#### VOC-014 Operational Design Domain (ODD)

**Description:** Vocabulary for defining the operating conditions under which an autonomous system is designed to function.

**Rationale:** Autonomous vehicles and robots require precise definition of approved operational parameters.

**Required fields:**
- Geographic boundaries
- Road types (highway, urban, private)
- Speed limits
- Weather conditions
- Lighting conditions
- Traffic density
- Operational hours
- Infrastructure dependencies
- Hazard exclusions

**Standards:** SAE J3016, ISO/PAS 21448 (SOTIF), UL 4600

**Used in:** Autonomous driving and trusted software release, Trusted Physical AI for robots in Japanese smart manufacturing.

---

### Energy and Grid Vocabularies

#### VOC-015 Energy Market Roles

**Description:** Vocabulary for energy market participant roles, authorizations, and operational responsibilities.

**Rationale:** Automated grid operations require machine-verifiable market role credentials.

**Required fields:**
- Market participant identifier (EIC code)
- Market role (DSO, TSO, BRP, supplier, aggregator, flexibility operator)
- Jurisdiction
- Licensed service territory
- Grid area codes
- Authorized activities
- Regulatory authority
- License number and status

**Standards:** ENTSO-E EIC codes, EBIX/EFET market role model, EU Network Codes

**Used in:** Trusted AI for energy grid forecasting and automated flexibility activation.

---

#### VOC-016 Flexibility and Grid Services

**Description:** Vocabulary for flexibility assets, activation requests, and grid service delivery.

**Rationale:** AI-driven flexibility activation requires standardized request and response formats.

**Required fields:**
- Asset identifier
- Asset type (battery, heat pump, industrial load, EV fleet)
- Flexibility capacity (MW)
- Response time
- Duration
- Grid area
- Activation request identifier
- Requester identity (DSO/TSO)
- Time window
- Technical constraints
- Price/compensation
- Activation confirmation
- Metered delivery

**Standards:** OpenADR, IEC 61850, IEEE 2030.5, USEF flexibility framework

**Used in:** Trusted AI for energy grid forecasting and automated flexibility activation.

---

### Content Authenticity Vocabularies

#### VOC-017 C2PA Content Credentials

**Description:** Vocabulary for content provenance manifests including creation, editing, and validation history.

**Rationale:** Content authenticity requires binding metadata to digital assets in a tamper-evident format.

**Required fields:**
- Asset identifier
- Content type (image, video, audio, document)
- Creation timestamp
- Creator identity (person, organization, AI service)
- Editing history
- AI generation flag
- AI service used
- Validation status
- Signature chains
- CAWG identity assertions

**Standards:** C2PA Specification v2.4, CAWG Identity Assertion Framework

**Used in:** C2PA and CAWG for trusted fashion imagery.

---

#### VOC-018 Rights and Approvals

**Description:** Vocabulary for intellectual property rights, usage permissions, brand authorization, and content approval.

**Rationale:** Content publication requires proof of rights clearance and approval chain.

**Required fields:**
- Rights holder identity
- License type
- Usage scope
- Geographic restrictions
- Temporal restrictions
- Brand authorization
- Product authorization
- Approval authority
- Approval date

**Standards:** IPTC Photo Metadata, PLUS (Picture Licensing Universal System), Creative Commons licenses

**Used in:** C2PA and CAWG for trusted fashion imagery.

---

### Cryptography and Security Vocabularies

#### VOC-019 Cryptographic Profiles and Algorithms

**Description:** Vocabulary for cryptographic algorithm identifiers, key parameters, and security profiles.

**Rationale:** Crypto-agility and PQC transition require explicit algorithm metadata in credentials and encrypted data.

**Required fields:**
- Algorithm identifier (NIST approved, custom)
- Algorithm type (signature, encryption, KEM)
- Key size
- Security level (bits)
- Hybrid mode flag
- Classical component
- PQC component
- Profile version
- Deprecation status

**Standards:** NIST FIPS publications, RFC cryptographic algorithm registries, COSE (RFC 9052), JOSE (RFC 7515-7518)

**Used in:** PQC-resilient U.S.-German digital data sharing corridor.

---

#### VOC-020 eIDAS Qualified Signatures and Seals

**Description:** Vocabulary for qualified electronic signatures (QES) and qualified electronic seals (QeSeal) metadata.

**Rationale:** Legal recognition of electronic signatures and seals requires conformance to eIDAS 2.0 requirements.

**Required fields:**
- Signature/seal type (QES, QeSeal, AdES)
- Signer/sealer identity
- Qualified certificate reference
- Trust service provider
- Timestamp
- Signature algorithm
- Hash algorithm
- Certificate chain
- Revocation information (OCSP, CRL)

**Standards:** eIDAS Regulation (EU) 910/2014 and eIDAS 2.0, ETSI EN 319 series (AdES formats)

**Used in:** Foreign tax declaration, Authentication and access for transport, e-Invoicing, Trusted AI for agentic B2B commerce and treasury, EV charging and legal persons.

---

### Compliance and Regulatory Vocabularies

#### VOC-021 KYC/KYB Data

**Description:** Vocabulary for customer and business due diligence data including identity verification, sanctions screening, and risk assessment.

**Rationale:** Regulated financial services require standardized KYC/KYB data formats.

**Required fields:**
- Customer identifier
- Identity verification level
- Verification method
- Verification date
- Document types verified
- Ultimate Beneficial Owner (UBO) data
- Sanctions screening status
- PEP (Politically Exposed Person) status
- Risk rating
- Source of funds
- Purpose of relationship

**Standards:** FATF Recommendations, JMLSG Guidance, SWIFT KYC Registry data model, LEI beneficial ownership data

**Used in:** Know your business partner, Know your supplier, Know your customer, Trusted AI for agentic B2B commerce and treasury.

---

#### VOC-022 Professional Qualifications and Skills

**Description:** Vocabulary for educational credentials, professional qualifications, and verified skills.

**Rationale:** Cross-border recognition of qualifications requires standardized credential formats.

**Required fields:**
- Credential type (degree, diploma, certificate, microcredential)
- Issuing institution
- Qualification level (EQF, NQF levels)
- Field of study (ISCED codes)
- Learning outcomes
- Credits (ECTS)
- Issue date
- Skills and competencies
- Recognition status

**Standards:** Europass, European Qualifications Framework (EQF), ELMO (European Learner Mobility), W3C Open Badges, IMS Global Comprehensive Learner Record

**Used in:** Issuing micro-credentials and verified skills.

---

### Cross-Cutting Vocabularies

#### VOC-023 Status and Revocation

**Description:** Vocabulary for credential status, revocation reasons, suspension, and validity state.

**Rationale:** Real-time status checking requires standardized status values and revocation semantics.

**Required fields:**
- Status type (valid, revoked, suspended, expired)
- Status reason
- Status effective date
- Status authority
- Next update time

**Standards:** W3C Verifiable Credentials Status List, OCSP (RFC 6960), CRL (RFC 5280)

**Used in:** All use cases (REQ-002).

---

#### VOC-024 Audit and Provenance

**Description:** Vocabulary for audit trails, event logs, and provenance chains.

**Rationale:** Accountability requires standardized audit event formats.

**Required fields:**
- Event identifier
- Event type (issuance, presentation, revocation, delegation)
- Event timestamp
- Actor identifier
- Action performed
- Resource affected
- Credential references
- Context data
- Signature

**Standards:** W3C PROV-O, ISO/IEC 27037 (digital evidence), OASIS XACML, CloudEvents

**Used in:** All use cases (REQ-003).

---

#### VOC-025 Policy Expression

**Description:** Vocabulary for authorization policies, presentation requests, and access control rules.

**Rationale:** Policy-driven credential exchange requires machine-readable policy languages.

**Required fields:**
- Policy identifier
- Required credential types
- Required claims
- Trusted issuer list
- Minimum assurance level
- Purpose of collection
- Retention period
- Permitted use

**Standards:** W3C DIF Presentation Exchange, XACML, Rego (Open Policy Agent), JSON Schema

**Used in:** Know your supplier, Know your customer, Trusted data sharing, PQC-resilient U.S.-German digital data sharing corridor.

---

### Vocabulary Governance Requirements

#### VOC-REQ-001 Multilingual Support

**Priority:** SHOULD

**Description:** Vocabularies SHOULD support multilingual labels and descriptions using language tags (BCP 47) to enable human-readable presentation in multiple languages while maintaining machine-processable identifiers.

**Used in:** All use cases with cross-border operations.

---

#### VOC-REQ-002 Versioning and Extension

**Priority:** MUST

**Description:** Vocabularies MUST include version identifiers and support backward-compatible extension mechanisms to enable evolution without breaking existing implementations.

**Used in:** All use cases.

---

#### VOC-REQ-003 Resolvable Identifiers

**Priority:** MUST

**Description:** Vocabulary terms MUST be identified by resolvable URIs that return machine-readable definitions and human-readable documentation.

**Used in:** All use cases.

---

#### VOC-REQ-004 Alignment with Existing Standards

**Priority:** SHOULD

**Description:** New vocabularies SHOULD reuse existing standard identifiers (NACE codes, GTIN, VIN, LEI, etc.) and align with established domain vocabularies (schema.org, FOAF, Dublin Core) where applicable.

**Used in:** All use cases.

---

#### VOC-REQ-005 Linked Data Compatibility

**Priority:** SHOULD

**Description:** Vocabularies SHOULD be expressed as RDF/JSON-LD compatible schemas to enable semantic interoperability and linked data applications.

**Used in:** All use cases.
