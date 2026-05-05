### C2PA and CAWG for trusted fashion imagery

**Actors:**
- Mariana — head of digital content, ModaSul Brasil S.A. (responsible publisher)
- AI image provider — content creator service
- Verification body — output validator (trusted industry association)
- Customers, marketplaces, auditors, regulators — verifiers

**Preconditions:** ModaSul holds a Business Wallet with legal person identity, brand ownership, and product credentials. The AI image provider holds a Business Wallet with an AI Service Passport (AISP). A verification body holds a legal person credential and is authorised to issue output validation credentials.

**Trigger:** ModaSul commissions AI-generated fashion imagery to replace part of its human model photography, requiring verifiable provenance for publication on its webshop and partner marketplaces.

**Postconditions:** Each published image carries a C2PA manifest with CAWG identity assertions linking ModaSul, the AI provider, and the verification body. Any customer, auditor, or regulator can verify the full provenance chain. A defective model version triggers automatic flagging and removal of affected images.

---

Mariana is the head of digital content at **ModaSul Brasil S.A.**, a Brazilian online fashion retailer selling apparel in Brazil, the EU, and the United States. ModaSul wants to replace part of its human model photography with generative AI. The goal is to reduce photo-shoot costs, create more product variants, localise visuals for different markets, and show products on different virtual body types.

Today, the process is hard to trust. The webshop shows AI-generated fashion images, but buyers, marketplaces, auditors, brands, and regulators cannot easily verify who created the image, which legal person approved it, which AI model was used, whether the image is linked to the correct product, whether rights were cleared, and whether the output was validated before publication.

What Mariana and ModaSul need is a verifiable provenance chain for AI-generated fashion visuals. The image must show not only that it has a valid C2PA manifest. It must also show which legal persons stand behind the image, which AI service created it, which product is shown, which rights and approvals apply, and which verification body validated the output.

C2PA is used to bind provenance metadata to the image. The C2PA manifest records the asset origin, edits, claim signature, and assertions about the content history. C2PA Content Credentials are designed to establish the origin and edits of digital content and to bind assertions, claims, and signatures into a verifiable manifest. ([c2pa.org](https://c2pa.org/))

But C2PA signing alone is not enough. A PKI certificate can prove that a signing key was used by a claim generator. It does not automatically prove that the responsible actor is the correct legal entity, that the actor has authority inside a corporate group, that rights were cleared, or that the AI service was validated. The C2PA trust model itself is based on the signer identity associated with the cryptographic signing key, and signers may be services, devices, or other non-human actors. ([spec.c2pa.org](https://spec.c2pa.org/specifications/specifications/2.4/specs/C2PA_Specification.html))

ModaSul therefore combines C2PA with CAWG identity assertions and Legal Person Credentials. CAWG identity assertions are used to bind named actors to a C2PA asset and to document their relationship to that asset. CAWG positions identity assertions as the “who” layer in the content authenticity ecosystem. ([cawg.io](https://cawg.io/about/identity-framework/))

ModaSul loads its Business Wallet with a legal person identity credential, VAT or tax credentials, brand ownership credentials, and product catalogue credentials. The AI image provider loads its Business Wallet with a legal person identity credential, AI service operator credential, model provenance credential, and AI Service Passport. The AISP records the model family, model version, training data classes, guardrails, output policy, TEVV results, human review rules, incident history, and validation status. A verification body, such as a trusted industry association or copyright verification body, holds its own legal person credential and issues output validation credentials.

When ModaSul generates a new fashion image, the AI image provider creates the image and attaches a C2PA manifest. The manifest records that generative AI was used, which tool created the image, which product image or product data was used as input, which edits were made, and which output file was published. The CAWG identity assertion links the image to ModaSul as the responsible retailer, the AI provider as the creator service, and the verification body as the validator.

Before publication, ModaSul’s content system verifies the full chain. It checks ModaSul’s legal person credential, the AI provider’s legal person credential, the AISP, the model provenance credential, the rights-clearance credential, the product credential, and the output validation credential. The system also verifies the C2PA manifest and confirms that the image has not been changed after validation.

The webshop shows the image with a visible verification label or QR code. A customer, marketplace, auditor, or regulator can scan it and verify: who created the image, which legal person approved it, which AI model was used, which product is shown, whether rights were cleared, whether the output was validated, and whether the image was changed after approval.

Later, the AI provider discovers that one model version produced visual artefacts that misrepresented garment fit for certain sizes or added inappropriate tattoos to AI-generated human model photography. The provider updates the AISP status. ModaSul’s content system detects the status change. All images created with that model version are flagged for review. Images that fail the policy check are removed or replaced until a new validated output credential is issued.

Requirements: Authentication/proof of control, legal person identity, CAWG identity assertion, C2PA manifest, AI Service Passport, model provenance credential, output validation credential, rights-clearance credential, product credential, brand ownership credential, marketplace publication credential, human review credential where required, real-time credential status and revocation, selective disclosure, verifiable audit trail, machine-to-machine verification, tamper-evident content provenance, post-publication status monitoring, cannot be administratively denied.

*Contributed by Spherity GmbH*
