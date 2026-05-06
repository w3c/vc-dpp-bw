### Automotive supply chain and battery passport

**Actors:**
- Marta — supplier quality manager, RheinMotor AG (verifier / OEM)
- HanBattery Energy — South Korean cell supplier
- Polish Tier 1 module supplier
- Italian power electronics supplier
- Accredited test labs, certification bodies — credential issuers

**Preconditions:** Each supplier holds a Business Wallet with legal person identity, site identity, certification, and product credentials. HanBattery has issued battery cell DPP credentials for cell batches. RheinMotor's quality system can initiate automated composite proof verification and resolve issuers against accreditation registries.

**Trigger:** RheinMotor begins the PPAP release process for a new electric vehicle platform, requiring multi-tier supplier qualification across legal identity, material compliance, battery due diligence, and safety certification.

**Postconditions:** RheinMotor holds a machine-verifiable, audit-ready PPAP record for each supplier and batch. Ongoing certification status is monitored automatically. A test credential withdrawal by an accredited lab triggers automatic identification and blocking of the affected vehicle lots.

---

Marta is a supplier quality manager at RheinMotor AG, a German vehicle manufacturer preparing a new electric vehicle platform. The platform uses battery cells from HanBattery Energy, a South Korean cell manufacturer, battery modules assembled by a Polish Tier 1 supplier, power electronics from Italy, and semiconductors from a European distributor. Before series production can start, RheinMotor must complete supplier qualification, PPAP release, material compliance checks, product carbon footprint review, battery due diligence, and conformity checks for safety-relevant parts.

Today, the evidence arrives as PDFs, spreadsheets, audit reports, portal exports, and scanned certificates. RheinMotor receives IATF 16949 certificates, ISO 14001 certificates, REACH and RoHS declarations, battery material reports, test reports, and PPAP records. Some files are signed. Others are copies. Several claims are issued by bodies in other jurisdictions. The quality team must verify them manually. This delays release and makes the audit trail weak.

What Marta and RheinMotor need is a way to verify each legal person, plant, part, batch, certificate, and product claim in one structured process. RheinMotor must know who issued each claim, whether the issuer is trusted, whether the claim is still valid, and whether it relates to the right part, batch, and production site.

Each supplier loads its Business Wallet with a legal person identity credential, site credentials, certification credentials, and product credentials. HanBattery issues battery cell Digital Product Passport credentials for cell batches. The Polish module supplier issues module DPP credentials that link to the Korean cell credentials. Accredited test labs issue verifiable test credentials. Certification bodies issue verifiable certification credentials. Each credential is signed by the issuer and carries a status endpoint.

When RheinMotor starts the PPAP release process, the Tier 1 supplier presents a composite proof. It contains its legal identity, site identity, certification status, PPAP release evidence, selected upstream provenance, and battery module DPP data. Sensitive commercial data, such as prices and unrelated customer contracts, is not disclosed. The proof is scoped to the product, batch, plant, and release process.

RheinMotor’s quality system verifies the proof automatically. It resolves legal person identifiers, checks certification bodies against accreditation registries, verifies signatures, and checks credential status. The system records which credentials were checked, which issuers were trusted, which batches were covered, and which policy requirements were satisfied.

Six months later, an accredited lab withdraws a test credential for one power electronics batch because a test procedure was wrong. The credential status changes at the source. RheinMotor detects the change during routine monitoring, identifies the affected vehicle lots, and blocks further use of the batch until a new valid attestation is issued.

**Requirements:** Authentication/proof of control, legal person identity, manufacturing-site identity, product identity, battery DPP credentials, batch credentials, conformity credentials, supplier provenance, selective disclosure, mutual authentication, real-time credential status and revocation, verifiable audit trail, machine-to-machine verification, credential portability across platforms, survives relationship with service provider, cannot be administratively denied.

*Contributed by Spherity GmbH*
