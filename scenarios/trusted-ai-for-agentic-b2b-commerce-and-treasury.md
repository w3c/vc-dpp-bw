### Trusted AI for agentic B2B commerce and treasury

**Actors:**
- Clara — treasurer, AlpinChem AG (principal)
- AlpinChem AI treasury agent — authorised AI agent (primary acting party)
- NorthBridge Markets Inc. — financial service provider (counterparty)
- NorthBridge AI pricing agent — counterparty AI agent

**Preconditions:** AlpinChem holds a Business Wallet with LEI, VAT, and treasury policy credentials. Clara holds a PoR and has issued a scoped Agent PoA to the treasury agent. NorthBridge holds a Business Wallet with regulated financial service provider credentials and an AISP for its pricing agent. Both AI agents are running approved, validated software versions.

**Trigger:** AlpinChem's AI treasury agent identifies a liquidity need and initiates a request for an FX forward quote from NorthBridge's AI pricing agent.

**Postconditions:** The FX transaction has been verified, approved (with dual human sign-off for amounts above threshold), sealed with a qualified electronic seal, and logged. Both parties hold a verifiable, non-repudiable record of the transaction and the AI service versions used. A model-risk issue in the pricing agent propagates immediately to block new requests.

---

Clara is the treasurer of AlpinChem AG, a German specialty chemicals company with subsidiaries in France, Italy, and Poland. Her team manages daily liquidity, short-term deposits, FX hedging, working-capital financing, and payments to critical suppliers. AlpinChem uses a U.S.-based financial service provider, NorthBridge Markets Inc., to access liquidity products, FX execution, and short-term credit facilities.

AlpinChem has started using an AI treasury agent. The agent monitors cash positions, forecasts liquidity, compares offers, and prepares execution recommendations. NorthBridge also uses an AI service agent to respond to treasury requests, price products, and check whether the client has passed KYB, sanctions, LEI, and mandate checks.

Today, these interactions still rely on static APIs, manual onboarding, PDF mandates, and internal email approvals. NorthBridge cannot automatically verify whether AlpinChem’s AI agent is real, whether it has authority to request a quote, whether it may prepare an execution file, and whether the request is inside AlpinChem’s treasury policy. AlpinChem has the reverse problem. It cannot automatically verify whether the responding AI agent belongs to NorthBridge and whether the AI service is validated.

What Clara and NorthBridge need is a verifiable trust chain for agentic B2B commerce. The system must prove the identity of each legal person, the authority of each AI agent, the regulated role of the financial service provider, the scope of the treasury mandate, and the validation status of the AI services used in the transaction.

AlpinChem loads its Business Wallet with a legal person identity credential, LEI credential, VAT credential, and treasury policy credential. The board issues Clara a Power of Representation credential for treasury operations. Clara then uses AlpinChem’s Business Wallet to issue a scoped Agent PoA to the AI treasury agent. The PoA allows the agent to request quotes, compare offers, and prepare recommendations for FX forwards and short-term deposits within defined limits. It does not allow final execution above the threshold without human approval.

NorthBridge loads its Business Wallet with its legal person identity credential, regulated financial service provider credentials, KYB status credentials, and payment account credentials. NorthBridge also issues an AI Service Passport for its pricing agent. The AISP contains the model version, service operator, release approval, TEVV evidence, runtime controls, human oversight model, incident history, and validation credentials. NorthBridge also holds operator credentials for NIST AI RMF alignment and ISO/IEC 42001 management controls.

When AlpinChem’s treasury agent requests an FX quote, it presents AlpinChem’s legal person credential, the Agent PoA, selected treasury policy claims, and its agent validation credential. NorthBridge verifies the credentials, checks the mandate scope, checks revocation status, and applies policy controls. The request is accepted only if it is within the authorised currency pair, volume, time window, and purpose.

NorthBridge’s AI agent responds with a signed quote. It presents NorthBridge’s legal person credential, regulated service provider credential, AISP, and validation credentials. AlpinChem verifies that the quote comes from an authorised counterparty and from a validated AI service. For a high-value transaction, the policy engine blocks autonomous execution and requires dual human approval. The final instruction is sealed and logged.

Three months later, NorthBridge finds a model-risk issue in one pricing agent release. It updates the AISP status. AlpinChem detects the change during routine monitoring. All new requests to that AI service version are blocked until NorthBridge issues a new validated AISP.

**Requirements:** Authentication/proof of control, legal person identity, LEI credential, regulated financial service provider credential, KYB/KYC credentials, Agent PoA, treasury policy credential, AI Service Passport, agent validation credential, NIST AI RMF operator credential, ISO/IEC 42001 operator credential, A2A mutual authentication, machine-to-machine verification, transaction limits, human approval thresholds, real-time credential status and revocation, third-party risk management, verifiable audit trail, non-repudiation, qualified electronic seal where required, cannot be administratively denied.

*Contributed by Spherity GmbH*
