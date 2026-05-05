### Trusted data sharing in a data space

**Actors:**
- Marco — grain farmer and CEADS member (primary)
- CEADS portal — data space operator
- AgriConsult — advisory service (data consumer)
- EUAgriLab — research consortium (data consumer)
- Ministry of Agriculture — regulatory authority (data consumer)
- Italian Chamber of Commerce, regional cadastral office, equipment manufacturer — credential issuers

**Preconditions:** Marco holds a European Business Wallet with valid credentials from the Italian Chamber of Commerce, the regional cadastral office, and his equipment manufacturer. Each CEADS participant has a verifiable identifier registered in the EU trust registry.

**Trigger:** Marco joins CEADS and attempts to onboard multiple data consumers simultaneously, each requiring independent identity verification and data access grants.

**Postconditions:** Marco has onboarded to CEADS once and issued scoped delegation credentials to each data consumer. Each consumer can access only the agreed data attributes for the agreed period. A verifiable audit record exists of every disclosure event. Marco can revoke any delegation at any time without platform intermediation.

---

Marco is a grain farmer in northern Italy whose cooperative recently invested in a network of smart sensors measuring soil moisture, crop health, and fertilizer consumption across his fields. His cooperative has signed up to the Common European Agricultural Data Space (CEADS), which promises him access to precision-farming advisory services, collaboration with university research institutes, and streamlined regulatory reporting to the national agricultural authority — all through a single platform membership.

The promise, however, has not yet matched the reality. Each service within CEADS operates its own onboarding portal. The advisory platform wants Marco to upload a copy of his business registration certificate and a proof of land ownership. The research institute needs him to create a separate account and re-verify his identity from scratch. The public authority requires an additional qualified electronic signature on every data submission. Marco has spent more time filling in forms than consulting agronomists.

What Marco needs is a way to establish his identity and the provenance of his sensor data once, and then reuse that proof across every participant in the data space — without surrendering control over which fields, which seasons, and which chemical inputs each recipient can actually see.

Marco obtains a European Business Wallet issued by his national accreditation authority and loads it with a set of verifiable credentials: his business identity credential (issued by the Italian Chamber of Commerce), a land-use credential (issued by the regional cadastral office), and a sensor-calibration attestation (issued by the equipment manufacturer). Each credential carries a globally resolvable identifier for the issuing authority so that any relying party can independently verify it without calling back to the issuer at query time.

When Marco connects to the CEADS portal for the first time, he presents a single composite proof derived from his wallet. The portal verifies each credential against its issuer's public identifier, confirms that Marco holds the private key bound to the business identity credential, and records a pseudonymous audit token rather than a copy of the raw documents. Marco is onboarded once.

Marco then authorizes AgriConsult, an advisory service, to receive weekly soil-moisture readings for field parcels A3 and A7 only — not the fertilizer logs, which are commercially sensitive. He grants EUAgriLab, a research consortium, access to anonymized, aggregated crop-health statistics for the current season. He grants the Ministry of Agriculture access to the full fertilizer ledger for regulatory compliance, but only for the date range covered by the current subsidy application. Each grant is encoded as a signed delegation credential in his wallet, scoped to the recipient's identifier and the agreed data attributes. No grant is possible without Marco's explicit, wallet-mediated consent.

When Marco later suspects that a sub-processor of AgriConsult has accessed data beyond the agreed scope, the audit log — anchored to the identifiers of Marco, AgriConsult, and the sub-processor — provides a verifiable record of every disclosure event. Marco can revoke the delegation credential for AgriConsult at any time; revocation propagates immediately through the trust framework without requiring CEADS to act as an intermediary.

When AgriConsult is acquired by a competitor and its original organizational identifier is retired, Marco's verifiable credentials remain valid: they are bound to the issuing authority's long-lived identifier, not to any particular platform session or service-provider account.

**Requirements:** Authentication/proof of control, Decentralized/self-issued, Inter-jurisdictional, User-controlled selective disclosure, Mutual authentication, Credential delegation and scoped authorization, Verifiable audit trail, Credential portability across platforms, Survives issuing organization changes, Cannot be administratively denied

*Contributed by WeBuild Consortium*
