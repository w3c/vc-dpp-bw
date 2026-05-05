### PQC-resilient U.S.-German digital data sharing corridor

**Actors:**
- Anna — senior risk officer, German customs authority (responding party)
- U.S. customs analyst — requesting party
- German and U.S. corridor endpoints — automated systems
- Both authorities — credential holders and policy enforcers

**Preconditions:** Both authorities hold public authority identity, agency role, and mandate credentials under their respective trust frameworks. Both corridor endpoints implement hybrid cryptography combining classical and post-quantum key establishment (ML-KEM) and digital signatures (ML-DSA or SLH-DSA). A bilateral trust framework mapping has been agreed and both sides' credentials are resolvable across frameworks.

**Trigger:** A U.S. customs analyst requests product-compliance evidence for a high-risk shipment of industrial battery modules exported from the U.S. to Germany, signing the request with a hybrid signature linked to their mandate credential.

**Postconditions:** The German corridor endpoint has delivered a selective, hybrid-encrypted data package containing only the authorised fields, with a verifiable audit envelope recording the request, approving authority, credentials verified, policy applied, algorithms used, and timestamp. Archived packages remain verifiable across cryptographic profile migrations.

---

Anna is a senior risk officer at a German customs authority. She works with a counterpart at a U.S. customs and border authority on high-risk shipments moving between the United States and Germany. The joint process covers customs declarations, product safety evidence, Digital Product Passport data, sanctions screening results, exporter and importer identity data, inspection results, and fraud-risk indicators.

Today, the data is exchanged through separate portals, bilateral API links, email attachments, and case-by-case requests. Some data has long-term confidentiality value. This includes trade-flow intelligence, enforcement patterns, supplier networks, dual-use indicators, sensitive company data, and critical infrastructure components. If encrypted traffic is collected today, it may become exposed later when quantum-capable attacks become practical. This creates a harvest-now, decrypt-later risk.

What Anna and her U.S. counterpart need is a PQC-resilient digital data sharing corridor. The corridor must protect data in transit and at rest. It must also verify the legal and administrative identity of each authority, the mandate of each officer or system, the purpose of each data request, and the integrity of every data package.

The German authority holds a public authority identity credential, agency role credentials, and mandate credentials for authorised systems and officers. The U.S. authority holds equivalent public authority, role, and mandate credentials under its trust framework. The corridor maps these credentials through a bilateral trust framework. Only authorised roles can request protected data.

Before data is exchanged, both sides perform mutual authentication. The corridor verifies the German authority credential, the U.S. authority credential, the agency role credentials, the mandate credentials, and the current status of each credential. The request is accepted only if the policy engine confirms that the requester is authorised for the data category, product class, case type, and legal basis.

The cryptographic channel uses hybrid cryptography. Key establishment combines a classical algorithm with a post-quantum key establishment algorithm such as ML-KEM. Digital signatures combine classical signatures with post-quantum signatures such as ML-DSA or SLH-DSA. The corridor records the cryptographic profile used for each exchange so that future migration and audit are possible.

A U.S. customs analyst requests product-compliance evidence for a shipment of industrial battery modules exported to Germany. The request includes the shipment identifier, exporter identity, importer identity, HS code, product category, legal basis, purpose limitation, and requested data fields. The request is signed with a hybrid signature and linked to the analyst’s mandate credential.

The German corridor endpoint verifies the request. It checks the U.S. agency credential, role credential, mandate credential, hybrid signature, credential status, and data access policy. It then creates a selective data package. The package contains only the authorised fields: product identity, DPP identifier, conformity declaration, battery passport reference, inspection status, sanctions screening result, and relevant risk indicators. It does not disclose unrelated commercial data or internal enforcement logic.

The response is encrypted using the hybrid channel and signed with a hybrid signature. The data package contains a verifiable audit envelope. The envelope records who requested the data, which authority approved it, which credentials were verified, which policy was applied, which algorithms were used, and when the package was sent.

Three years later, one cryptographic profile is deprecated. The corridor marks it as no longer valid for new exchanges. Archived packages remain verifiable because they contain algorithm metadata, timestamps, trust-chain evidence, and migration status. New exchanges are automatically upgraded to the approved hybrid profile without renegotiating the bilateral data-sharing agreement.

**Requirements:** Public authority identity credential, agency role credential, mandate credential, legal basis credential, purpose limitation, mutual authentication, PQC-resilient hybrid encryption, hybrid digital signatures, ML-KEM-based key establishment, post-quantum signature support, crypto-agility, algorithm metadata, verifiable audit trail, selective disclosure, policy-based access control, real-time credential status and revocation, tamper-evident data package, long-term archive protection, cross-border trust framework mapping, cannot be administratively denied.

*Contributed by Spherity GmbH*
