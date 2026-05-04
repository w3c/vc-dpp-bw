### Company representative acting on behalf of a company

**Actors:**
- Sofia — legal affairs manager, VerdeTech (primary representative)
- VerdeTech — renewable energy company (principal)
- VerdeTech board of directors — mandate issuer
- Polish bank, Polish business register, municipal authority in Kraków — verifiers

**Preconditions:** VerdeTech holds a European Business Wallet with a legal-entity credential from the Dutch Chamber of Commerce. Sofia holds an EU Digital Identity Wallet with a personal identity credential. VerdeTech's board has issued a scoped Power of Representation credential into Sofia's wallet.

**Trigger:** VerdeTech wins a public procurement contract in Poland and appoints Sofia to complete cross-border legal and banking engagements within a two-week window.

**Postconditions:** Sofia has completed account opening, branch registration, and contract execution across three Polish institutions using a single wallet interaction each. VerdeTech can restrict or revoke Sofia's mandate at any time through its Business Wallet, with revocation visible to verifiers immediately.

---

Sofia is the legal affairs manager of VerdeTech, a mid-sized renewable energy company headquartered in Amsterdam. VerdeTech has won a public procurement contract to supply solar infrastructure to a municipal authority in Kraków, Poland. Before work can begin, VerdeTech must open a local corporate bank account, register a branch with the Polish business register, and sign the contract addendum with the municipal authority — all within a two-week window. Sofia has been appointed to handle all three on the company's behalf.

The moment Sofia lands in Kraków, the process stalls. The bank requires a notarised, apostilled power of attorney confirming that Sofia is authorised to open accounts on VerdeTech's behalf. The business register accepts digital submissions but only through its national identity portal, which does not recognise Sofia's Dutch eID. The municipal authority needs proof that Sofia's mandate covers contract execution specifically, not just general company representation. Each institution applies its own validation procedure, none of which recognise the others' outputs. Sofia spends the first week couriering certified paper documents between Amsterdam and Kraków and the second week chasing apostille stamps.

What Sofia and VerdeTech need is a machine-verifiable, digitally native mandate — one that proves Sofia's identity as a natural person, binds her unambiguously to VerdeTech as a legal person, specifies exactly which acts she is authorised to perform, and can be presented to any relying party in any member state without re-issuing or re-notarising.

VerdeTech's board of directors issues a Power of Representation credential through the company's European Business Wallet. The credential is signed with VerdeTech's legal-entity identifier — a credential itself issued by the Dutch Chamber of Commerce — and specifies Sofia as the named holder. The mandate is scoped: it authorises Sofia to open bank accounts, sign contracts valued up to €5 million, and submit filings to business registers, all on behalf of VerdeTech, valid for ninety days. The credential is pushed directly into Sofia's EU Digital Identity Wallet.

When Sofia presents herself at the Polish bank, she produces two credentials from her wallet in a single interaction: her personal identity credential — issued by the Dutch national identity authority — and the Power of Representation credential issued by VerdeTech. The bank's verification system resolves VerdeTech's legal-entity identifier against the European Business Register, confirms the credential's signature, checks the mandate scope, and confirms Sofia's identity matches the named holder. No paper is exchanged. No apostille is needed. The bank records a verifiable receipt of the presentation.

At the Polish business register, the same wallet presentation satisfies the national portal's identity requirements through cross-border recognition under the eIDAS 2.0 framework. The register does not need to issue Sofia a local credential; it relies on the credentials she already holds.

At the municipal authority, Sofia presents only the subset of her mandate relevant to contract execution. She does not disclose the banking authorisation or the financial ceiling of her mandate — details the municipality has no legitimate need to see. Selective disclosure ensures that each relying party receives exactly the claims it requires, no more.

Three days into her trip, Sofia completes all three engagements. When VerdeTech's board later restricts her mandate — removing the bank account authority after the account is opened — VerdeTech updates the credential status in its Business Wallet. The revocation is immediately visible to any party that attempts a fresh verification. Existing completed transactions are unaffected; only future presentations of the now-restricted credential will fail.

**Requirements:** Authentication/proof of control, Decentralized/self-issued, Inter-jurisdictional, Credential delegation and scoped authorization, User-controlled selective disclosure, Mutual authentication, Verifiable audit trail, Credential portability across platforms, Revocation without intermediary, Cannot be administratively denied

*Contributed by WeBuild Consortium*
