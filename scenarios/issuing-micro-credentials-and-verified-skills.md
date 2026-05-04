### Issuing micro-credentials and verified skills

**Actors:**
- Yusuf — student and job applicant (primary)
- University of Porto, CodeLabs (training provider), Yusuf's former employer — credential issuers
- TU Berlin admissions office — verifier (academic)
- Berlin-based recruiter — verifier (professional)

**Preconditions:** The University of Porto and CodeLabs are registered in the European Higher Education trust registry. Yusuf holds an EU Digital Identity Wallet. CodeLabs' micro-credentials are mapped to EQF levels and counter-attested by an accreditation body.

**Trigger:** Yusuf applies to a competitive master's programme at TU Berlin and is simultaneously approached by a recruiter, both requiring independent verification of his academic and professional qualifications.

**Postconditions:** TU Berlin's admissions platform and the recruiter have each independently verified the relevant credentials without paper, translation, or duplicate assessments. Yusuf's skill profile accumulates further micro-credentials from TU Berlin without invalidating prior credentials.

---

Yusuf is a twenty-four-year-old from Porto who has spent the last three years building a profile in data science through a combination of formal education, structured training, and professional practice. He holds a bachelor's degree in applied mathematics from the University of Porto, completed a sixteen-week data engineering bootcamp at CodeLabs — a certified vocational training provider — and spent eighteen months as a junior data analyst at a Lisbon-based logistics startup. He has now been accepted onto the application shortlist for a competitive master's programme in data science at the Technical University of Berlin, which requires him to demonstrate both his academic foundation and specific technical competences before a final admission decision is made.

The admissions office sends Yusuf a checklist. It requires an officially certified copy of his degree transcript, translated into German by a sworn translator. It requires proof that his bootcamp certificate meets the European Credit system for Vocational Education and Training standards. It requires a letter from his employer confirming his professional experience, on company letterhead, countersigned by a manager. And it requires all documents to arrive as physical originals or notarised copies within four weeks. Yusuf's degree transcript must be requested from the University of Porto's registrar, a process that takes up to ten working days. The certified translation adds another week and a fee of over a hundred euros. The bootcamp certificate does not state its alignment to any European framework — CodeLabs simply printed a PDF with his name and the course title. The startup he worked for has since been acquired; his former manager no longer works there and the company letterhead has changed.

Meanwhile, a recruiter at a Berlin-based mobility analytics firm has seen Yusuf's portfolio online and wants to verify his Python and machine learning skills before inviting him to interview. The recruiter has no means of verifying the bootcamp certificate independently and asks Yusuf to take a third-party skills assessment instead — duplicating work that CodeLabs already assessed and certified.

What Yusuf needs is a way to carry his qualifications as verifiable, portable, machine-readable credentials that any institution or employer can check against the issuing authority directly, without paper, without translation delays, and without asking him to prove the same competence twice.

The University of Porto issues Yusuf's degree credential into his EU Digital Identity Wallet, signed with the university's institutional identifier registered in the European Higher Education trust registry. The credential includes his transcript data structured against the Europass Learning Model, with field-level claims for each subject and grade. CodeLabs issues two micro-credentials into Yusuf's wallet: one for the data engineering programme mapped to EQF level 5, and one for a machine learning specialisation module mapped to EQF level 6. Each is signed by CodeLabs and counter-attested by the national accreditation body that audited the bootcamp's curriculum. His former employer — operating under its new parent company — issues a professional experience attestation signed with the parent company's legal-entity credential, with a verifiable link to the acquired entity's historical identifier confirming continuity of the employment record.

When Yusuf applies to TU Berlin, he presents a wallet-derived proof containing all four credentials in a single interaction. TU Berlin's admissions platform resolves the University of Porto's identifier against the European Higher Education trust registry, verifies the degree credential's signature, and reads the transcript claims directly without requiring a translation — the Europass Learning Model provides machine-readable field labels in all EU languages. It verifies the CodeLabs micro-credentials against the national accreditation body's registry, confirms EQF level alignment, and reads the professional attestation without needing a physical letter. The entire verification takes seconds. Yusuf is asked no follow-up questions about document authenticity.

When the Berlin recruiter contacts Yusuf, he generates a selective presentation from his wallet containing only the machine learning micro-credential and the professional experience attestation — not his degree transcript, which is irrelevant to the role and which Yusuf chooses not to share. The recruiter's platform verifies the micro-credential against the accreditation registry in real time. No third-party reassessment is requested.

Six months into his master's programme, Yusuf completes an advanced module in distributed data pipelines and receives a further micro-credential from TU Berlin into his wallet. His skill profile updates without any intervention from previous issuers. His Porto transcript and CodeLabs credentials remain valid and independently verifiable alongside the new addition.

**Requirements:** Authentication/proof of control, Decentralized/self-issued, Inter-jurisdictional, User-controlled selective disclosure, Credential portability across platforms, Human-centered interoperability, Verifiable audit trail, Survives issuing organisation changes, Cannot be administratively denied, Real-time credential status

*Contributed by WeBuild Consortium*
