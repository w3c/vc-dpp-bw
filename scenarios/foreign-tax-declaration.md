### Foreign tax declaration

**Actors:**
- Astrid — finance director, NordBuild AB (principal)
- RoTax Advisors — tax intermediary (authorised representative)
- ANAF — Romanian national tax authority (verifier)
- Swedish Companies Registration Office, Swedish Tax Agency — credential issuers

**Preconditions:** NordBuild holds a European Business Wallet with legal-entity, VAT, and tax-residence credentials from Swedish authorities. RoTax holds a Business Wallet capable of receiving delegation credentials. ANAF's portal can resolve EU trust registry identifiers.

**Trigger:** NordBuild's sustained construction activity in Romania triggers a local VAT registration obligation and a recurring quarterly filing requirement under the Sweden–Romania double taxation treaty.

**Postconditions:** RoTax has submitted NordBuild's VAT return to ANAF via machine-to-machine interface under a verifiable delegation. Both wallets hold a tamper-evident QUERDS delivery receipt. Astrid revokes RoTax's mandate on project completion; the revocation takes effect immediately.

---

Astrid is the finance director of NordBuild AB, a Swedish construction company that has been delivering a renewable energy installation project in Romania for the past eight months. Under EU VAT rules, NordBuild's sustained activity in Romania has triggered a local VAT registration obligation. Astrid must now file quarterly VAT returns with ANAF, the Romanian national tax authority, and submit a certificate of tax residence to support a withholding tax reduction claim under the Sweden-Romania double taxation treaty. Because NordBuild has no Romanian-speaking staff, Astrid has engaged RoTax Advisors, a Bucharest-based tax intermediary, to prepare and submit the filings on the company's behalf.

Before RoTax can file anything, ANAF requires proof that NordBuild is a legally registered entity, that it holds a valid Swedish VAT number, that it is tax-resident in Sweden, and that RoTax has been formally authorised to act as its representative. ANAF's portal does not accept Swedish eID credentials. NordBuild must submit a notarised and apostilled power of attorney naming RoTax as its authorised agent, accompanied by a certified extract from the Swedish Companies Registration Office and a tax residence certificate issued by the Swedish Tax Agency — all translated into Romanian by a certified translator. The Swedish Tax Agency issues residence certificates by post, with a processing time of up to three weeks. The notary and apostille process adds a further ten days and a fee of several hundred euros.

By the time the paper chain is complete, NordBuild has missed the deadline for its first quarterly filing and incurred a late-submission penalty. RoTax cannot begin work until the originals arrive by courier. The same process will repeat every quarter for as long as the project runs, and again when NordBuild eventually applies for a VAT deregistration.

What Astrid and RoTax both need is a mechanism that establishes NordBuild's legal identity and tax status once, grants RoTax a verifiable, scoped mandate to act on NordBuild's behalf, and allows ANAF to verify both without requiring paper originals or human translation.

NordBuild loads its European Business Wallet with three credentials obtained directly from the Swedish authorities: a legal-entity credential issued by the Swedish Companies Registration Office, a VAT registration credential issued by the Swedish Tax Agency, and a tax-residence credential also issued by the Swedish Tax Agency. Each credential is signed with the issuing authority's long-lived identifier and carries a machine-readable validity period and status endpoint.

Astrid uses NordBuild's Business Wallet to issue a delegation credential to RoTax Advisors. The mandate is scoped precisely: it authorises RoTax to submit VAT returns and tax treaty applications to Romanian tax authorities on NordBuild's behalf, for the duration of the Romanian project. It does not grant authority over NordBuild's Swedish filings, its banking relationships, or any other jurisdiction. The delegation credential is signed by NordBuild and delivered directly into RoTax's wallet.

When RoTax connects to the ANAF filing portal, it presents a composite proof: NordBuild's legal-entity and tax-residence credentials, together with the delegation credential naming RoTax as the authorised intermediary. ANAF's verification system resolves each issuer's identifier — the Swedish Companies Registration Office and the Swedish Tax Agency — against the European Business Register and the EU trusted-authority registry. Every signature is verified. The mandate scope is confirmed. No paper is exchanged, no translation is required, and the entire verification completes before the session times out.

RoTax prepares the VAT return and submits it through a machine-to-machine interface, attaching a qualified electronic seal derived from NordBuild's Business Wallet. ANAF receives a filing that is cryptographically attributable to NordBuild and verifiably submitted by its authorised agent. A structured delivery receipt is returned to both RoTax's wallet and NordBuild's wallet via a Qualified Electronic Registered Delivery Service, giving Astrid a tamper-evident record of what was filed, when, and by whom.

When the project concludes and NordBuild applies for VAT deregistration, Astrid revokes the delegation credential in NordBuild's wallet. RoTax's authority to represent NordBuild before ANAF terminates immediately, without any further administrative action from either party.

**Requirements:** Authentication/proof of control, Decentralized/self-issued, Inter-jurisdictional, Credential delegation and scoped authorization, Mutual authentication, Machine-to-machine data exchange, Qualified electronic signature and seal, Verifiable audit trail, Real-time credential status and revocation, Cannot be administratively denied, Survives relationship with service provider

*Contributed by WeBuild Consortium*
