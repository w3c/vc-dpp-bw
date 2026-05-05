### Know your business partner — KYC / KYS / KYB due diligence

**Actors:**
- Lars — supplier qualification manager, Helix Pharma (verifier)
- CelluSyn — Czech API manufacturer (subject)
- Czech trade register, national UBO register, Czech SÚKL, accredited certification body, sanctions screening provider — credential issuers

**Preconditions:** CelluSyn holds a European Business Wallet with credentials from all relevant authoritative sources. Helix Pharma's compliance platform can resolve credential issuers against the European Business Register and accreditation registries.

**Trigger:** Helix Pharma's procurement team identifies CelluSyn as a candidate supplier and initiates a structured Know Your Business Partner due diligence process covering KYC, KYB, and KYS checks.

**Postconditions:** Helix Pharma holds a structured, machine-verifiable compliance record for CelluSyn. Future re-verifications are automated through credential status endpoints. CelluSyn's administrative effort for repeat due diligence with other customers is eliminated.

---

Lars is a supplier qualification manager at Helix Pharma, a German manufacturer of prescription medicines. Helix is legally required under EU pharmaceutical regulations to perform structured due diligence on every new supplier before a purchase order can be raised. For CelluSyn, a Czech producer of active pharmaceutical ingredients that Helix's procurement team wants to onboard, this means verifying the company's legal registration and ownership structure, confirming the identities of its ultimate beneficial owners, checking its ISO and GMP certifications, and establishing that it is not subject to any sanctions or insolvency proceedings. The process is known internally as Know Your Business Partner, spanning KYC, KYB, and KYS checks.

Lars sends CelluSyn a standard due diligence questionnaire. Over the following two weeks he receives a collection of PDFs: a Czech trade register extract dated four months ago, a hand-signed UBO declaration, scanned GMP certificates in Czech with informal translations attached, and a letter from CelluSyn's auditors confirming a clean balance sheet for the prior fiscal year. Lars's compliance team must now verify each document's authenticity individually — contacting the Czech trade register to confirm the extract, emailing the certification body to validate the GMP certificate number, and checking the UBO declaration against a sanctions screening service. Two of the documents are expired. One certification number returns no result from the issuing body's lookup tool. Onboarding stalls for six weeks.

This is not the first time CelluSyn has been through this process. Three other pharmaceutical customers conducted equivalent checks earlier in the same year, each requesting the same documents and each running independent validation routines. CelluSyn's administrative team spent over forty hours responding to overlapping requests for information it had already provided, in formats and languages dictated by each requester.

What Lars and CelluSyn both need is a mechanism by which CelluSyn assembles its compliance profile once — as a set of machine-verifiable credentials issued by the authoritative sources — and presents it to any counterparty without re-collecting, re-translating, or re-submitting the same underlying data.

CelluSyn loads its European Business Wallet with a set of credentials obtained directly from the relevant authorities: a legal-entity credential issued by the Czech trade register, a beneficial-ownership credential issued by the national UBO register, a GMP manufacturing authorisation issued by the Czech State Institute for Drug Control, an ISO 9001 certification credential issued by its accredited certification body, and a current sanctions-clearance credential issued by a regulated screening provider. Each credential is cryptographically signed by its issuer and carries a status endpoint that relying parties can query to confirm it has not been revoked or expired since issuance.

When Lars initiates a new supplier qualification for CelluSyn, CelluSyn's wallet generates a presentation containing only the credentials and claims that Helix's due diligence policy requires. The ownership structure is disclosed, but the detailed financial schedules — held in a separate credential — are not included in this presentation. CelluSyn's wallet logs the disclosure event with a record of which claims were shared, with whom, and when.

Lars's compliance platform receives the presentation, resolves each issuer's identifier against the European Business Register and the relevant accreditation registries, verifies every signature, and queries each credential's status endpoint in real time. The Czech-language trade register credential is accompanied by a machine-readable jurisdiction metadata claim; no human translation is required. The entire verification completes in under three minutes. Helix's audit log captures a structured record of the checks performed and their outcomes, satisfying the evidentiary requirements of Helix's internal compliance framework and any future regulatory inspection.

Six months later, CelluSyn's GMP authorisation is suspended by the Czech regulator pending an inspection. The regulator updates the credential's status at the source. The next time any of CelluSyn's customers — including Helix — performs a routine re-verification, the suspended status is returned automatically. No manual notification is needed; no customer continues to rely on a stale certificate.

**Requirements:** Authentication/proof of control, Decentralized/self-issued, Inter-jurisdictional, Mutual authentication, User-controlled selective disclosure, Credential portability across platforms, Verifiable audit trail, Real-time credential status and revocation, Cannot be administratively denied, Survives relationship with service provider

*Contributed by WeBuild Consortium*
