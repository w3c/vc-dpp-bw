### Authentication and access for transport

**Actors:**
- Tomasz — professional truck driver, BalticFreight GmbH (primary)
- BalticFreight GmbH — freight operator (mandate issuer)
- Port of Antwerp terminal gate — verifier
- Polish driving licence authority, Polish-certified training body — credential issuers
- German BFARM, EU ECMT scheme — BalticFreight credential issuers

**Preconditions:** Tomasz holds an EU Digital Identity Wallet with valid driving licence, CPC, and ADR credentials. BalticFreight holds a Business Wallet with GDP and ECMT credentials and has issued a trip-scoped delegation credential to Tomasz. The port authority's gate system supports real-time credential verification against EU transport authority registries.

**Trigger:** BalticFreight dispatches Tomasz to collect a pharmaceutical consignment from the Port of Antwerp under GDP regulations and ADR requirements.

**Postconditions:** Tomasz has been verified at the gate within seconds, collected the consignment under a matched eFTI freight record, and completed the eCMR chain of custody with qualified electronic signatures. All events are recorded as verifiable, timestamped credential presentations.

---

Tomasz is a professional truck driver employed by BalticFreight GmbH, a Hamburg-based freight operator that has been contracted to collect a consignment of temperature-sensitive pharmaceutical goods from the secure cargo terminal at the Port of Antwerp. The cargo is classified as high-value and subject to Good Distribution Practice regulations, meaning that every party in the chain — the driver, the vehicle, and the operating company — must be verified against specific certification requirements before the terminal gate will open.

BalticFreight's dispatcher has emailed the port authority a copy of the company's GDP transport licence, a PDF of Tomasz's ADR driver certificate permitting him to carry dangerous and sensitive goods, and a scanned version of his Certificate of Professional Competence. The port authority's gate office has printed these documents and placed them in a folder at the security booth. When Tomasz arrives after a twelve-hour drive from Hamburg, the security officer cannot reach the colleague who processed the email. The GDP licence PDF carries no issuer signature that can be verified on the spot. The ADR certificate was issued in Poland and its format is unfamiliar to the Belgian security officer, who is uncertain whether it is still valid. Tomasz waits at the gate for ninety minutes while phone calls are made across two countries. A second truck from a different operator, also waiting, turns out to be carrying forged documentation — a fraud the manual process failed to detect until a supervisor intervened.

Inside the terminal, the electronic freight transport information system — operating under the EU eFTI regulation — holds a digital freight record for the consignment. The record names BalticFreight as the authorised consignee and references the expected vehicle registration and driver identifier. But the gate system cannot automatically match the paper documents Tomasz has presented against the eFTI record. The connection between the freight data and the identity of the person standing at the gate exists only in the dispatcher's email thread.

What the port authority, BalticFreight, and Tomasz all need is a system in which every credential — the driver's licence, the professional competence certificate, the ADR authorisation, the company's GDP licence — is verifiable in seconds at the gate, bound to the freight record electronically, and trustworthy across the borders of every member state through which the cargo has passed.

Tomasz carries his EU Digital Identity Wallet on his phone. It holds three credentials issued by authoritative sources: his driving licence credential issued by the Polish driving licence authority, his Certificate of Professional Competence issued by a Polish-certified training body and registered with the national competent authority, and his ADR driver certificate issued by the same body and cross-registered with the European dangerous goods authority. Each credential is signed by its issuer and carries a real-time status endpoint.

BalticFreight's European Business Wallet holds the company's GDP transport licence, issued by the German Federal Institute for Drugs and Medical Devices, and its cross-border haulage authorisation, issued under the EU ECMT permit scheme. BalticFreight has issued a trip-scoped delegation credential to Tomasz for this specific consignment: it names him as the authorised driver, references the vehicle registration, the eFTI freight record identifier, and a validity window covering the collection date. The delegation credential is signed by BalticFreight and held in Tomasz's wallet alongside his personal credentials.

At the Antwerp terminal gate, Tomasz presents his wallet to the port authority's verification terminal. The system reads his driving licence, CPC, and ADR credentials, resolves each issuer against the European transport authority registry, and confirms their validity status in real time. It reads the BalticFreight delegation credential, verifies the company's GDP licence against the European medicines authority registry, and matches the eFTI freight record identifier in the delegation against the live eFTI system. The consignment, the authorised carrier, and the named driver are confirmed as a consistent, verified set within seconds of Tomasz arriving at the gate. The barrier opens.

At collection, Tomasz signs the electronic consignment note — the eCMR — using his wallet, producing a qualified electronic signature attributable to him as an identified natural person acting under BalticFreight's verified mandate. The eCMR is transmitted to the shipper, the consignee, and the eFTI platform simultaneously. No paper changes hands. When the consignment is delivered in Hamburg, Tomasz signs the delivery confirmation in the same way. The complete chain of custody — from terminal gate to warehouse door — is recorded as a sequence of verifiable, timestamped credential presentations and electronic signatures.

When Tomasz's ADR certificate expires three months later, the status endpoint returns a lapsed status. Any gate system performing a real-time check will decline to grant him access to sensitive cargo zones until a renewed credential is issued. No manual notification process is needed; no dispatcher has to remember to pull an expiry date from a spreadsheet.

**Requirements:** Authentication/proof of control, Decentralized/self-issued, Inter-jurisdictional, Mutual authentication, Credential delegation and scoped authorization, Machine-to-machine data exchange, Qualified electronic signature, Verifiable audit trail, Real-time credential status and revocation, Cannot be administratively denied, Human-centered interoperability

*Contributed by WeBuild Consortium*
