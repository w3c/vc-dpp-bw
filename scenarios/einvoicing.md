### eInvoicing

**Actors:**
- Kaisa — accounts payable manager, MeridianTech SpA (buyer)
- Margus — finance director, SilverComponent OÜ (supplier)
- Peppol network — transmission infrastructure
- Sistema di Interscambio (SDI) — Italian clearance system
- Estonian Business Register, Estonian Tax and Customs Board, Italian Business Register, Agenzia delle Entrate — credential issuers

**Preconditions:** Both MeridianTech and SilverComponent hold European Business Wallets with legal-entity and VAT credentials. SilverComponent's invoicing system can apply qualified electronic seals covering all invoice fields. MeridianTech's ERP can automatically verify seals before any invoice enters the approval workflow.

**Trigger:** SilverComponent generates an invoice for a delivery of printed circuit board assemblies to MeridianTech and transmits it via the Peppol network.

**Postconditions:** MeridianTech's ERP has automatically verified the invoice's integrity, provenance, and payment account binding before processing. Any tampered invoice is automatically rejected before reaching the payment queue. The SDI clearance receipt is stored in both companies' audit logs.

---

Kaisa is the accounts payable manager at MeridianTech SpA, an Italian electronics manufacturer based in Milan. MeridianTech sources printed circuit board assemblies from SilverComponent OÜ, an Estonian component supplier with whom it has traded for two years. The two companies exchange several dozen invoices a month, routed through the Peppol network and submitted to Italy's mandatory electronic invoicing clearance system, the Sistema di Interscambio, before MeridianTech's ERP can process a payment.

Three months ago, MeridianTech's finance team received what appeared to be a routine invoice from SilverComponent for a delivery of components. The invoice carried SilverComponent's correct company name, Estonian VAT number, and order reference. The only change was a single field: the bank account number for payment settlement. By the time the discrepancy was identified, MeridianTech had transferred eighty-seven thousand euros to an account controlled by a third party who had intercepted the invoice in transit and altered it. The PDF format of the original invoice carried no cryptographic signature. There was no mechanism for MeridianTech's ERP to verify that the invoice it received was identical to the one SilverComponent had issued, nor to confirm that the bank account number was one legitimately associated with SilverComponent as a verified legal entity.

SilverComponent, for its part, had no reliable way to confirm MeridianTech's VAT registration status before extending sixty-day payment terms on a large order. It queried the EU VIES system manually for each new order cycle, but VIES returns only a binary valid or invalid result and carries no cryptographic assurance. A fraudulent buyer could present a cloned VAT number and SilverComponent would have no means to detect it at the point of invoice issuance.

Both companies now conduct additional manual verification calls before processing any invoice above ten thousand euros — a control that slows the payment cycle, introduces human error, and still provides no tamper-evidence for the document itself.

What Kaisa and SilverComponent's finance director Margus both need is a trust framework in which every invoice is issued by a cryptographically verified legal entity, every payment-relevant data field is bound to that entity's verified identity, and every receiving system can confirm the invoice's integrity and provenance without a phone call or a manual database lookup.

SilverComponent loads its European Business Wallet with two credentials: a legal-entity credential issued by the Estonian Business Register and a VAT registration credential issued by the Estonian Tax and Customs Board. Each credential is signed with the issuing authority's long-lived identifier and carries a status endpoint. MeridianTech similarly loads its Business Wallet with a legal-entity credential from the Italian Business Register and a VAT registration credential from the Agenzia delle Entrate.

When SilverComponent's invoicing system generates an invoice for MeridianTech, it embeds SilverComponent's verified legal-entity identifier in the invoice header and applies a qualified electronic seal derived from SilverComponent's Business Wallet. The seal covers every field of the structured invoice document, including the payment bank account number. The invoice is transmitted via Peppol with both parties' business wallet identifiers included as verified endpoint references.

When MeridianTech's ERP receives the invoice, it resolves SilverComponent's identifier against the European Business Register, verifies the qualified seal, and confirms that the bank account number in the payment field is bound to SilverComponent's verified identity. The verification completes automatically before the invoice enters the approval workflow. Any alteration of the document in transit — including a substituted bank account number — breaks the seal and triggers an automatic rejection with a detailed audit entry. No invoice that fails verification reaches the payment queue.

Before issuing the invoice, SilverComponent's system performs the reciprocal check: it resolves MeridianTech's business wallet identifier, verifies the Italian legal-entity and VAT credentials, and confirms that MeridianTech is a currently registered, VAT-compliant entity in good standing. The credit terms are extended on the basis of a verified counterparty, not a name and a VAT number that could have been spoofed.

The verified invoice is forwarded to the Sistema di Interscambio carrying the qualified seal intact. The SDI receives a document that is cryptographically attributable to a verified Estonian legal entity transacting with a verified Italian legal entity, satisfying Italian mandatory eInvoicing requirements without any additional manual submission step. The clearance receipt returned by the SDI is stored in both companies' audit logs alongside the original verified presentation.

When SilverComponent later migrates from one Peppol access point provider to another, its business wallet identifier and verifiable credentials remain unchanged. MeridianTech's ERP continues to verify incoming invoices against the same issuer identifiers without any reconfiguration. The trust relationship survives the change of service provider on both sides.

**Requirements:** Authentication/proof of control, Decentralized/self-issued, Inter-jurisdictional, Mutual authentication, Qualified electronic seal, Machine-to-machine data exchange, Verifiable audit trail, Real-time credential status and revocation, Cannot be administratively denied, Survives relationship with service provider

*Contributed by WeBuild Consortium*
