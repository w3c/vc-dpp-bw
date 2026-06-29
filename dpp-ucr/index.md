# Introduction
A verifiable credential (VC) is a mechanism for issuing authenticated, revokable and portable data in a tamper-proof way to a "data holder" that also provides a privacy-preserving mechanism to verify this data by a third party (i.e., the “verifier” does not reveal anything about the "holder" when performing this verification). Thus, VCs are useful tools for encapsulating product-related claims: e.g. providing copyright proofs for merchandised products, ESG performance certifications, declarations of conformity, customs clearance proofs, etc., that might be accessed from a DPP. 

Different questions arise when considering issuing the DPP itself as a VC. In the normal case of VC use, a credential is issued by an “issuer” to another party, the “holder”, in recognition by the “issuer” of claims concerning the “holder”.   However, differently from most applications of VCs, where the “issuer” and “holder” are distinct parties and the “verifier” retrieves the data from the “holder” and only checks with the “issuer” that the credential is still valid, the default situation for a DPP (in particular for the European DPP) is that the “issuer” and “holder” are the same organisation, meaning that the DPP data is retrieved directly from the issuing organisation, a.k.a. the “economic operator”.  HTTPS provides the minimum requirements for authentication and integrity (assuming the link used to retrieve the data is trusted). 

This note aims to investigate why, in some cases, it might be useful to issue a DPP as a VC, explain why a DPP task force has been created in the W3C VCWG and discuss compatibility of DPP standards with the VCDM VC format. 

# Why are VCs useful for DPPs? 
The following list provides a number of use cases where VCs provide additional capabilities with respect to HTTPS.  
- **Identifying the issuer of the DPP**: In many trade and logistics supply-chains, the DPP data may be stored and used locally by different “holders”. Thus, the server hosting the DPP may provide no information on the actually issuer of the data.   
- **DPP revocation**: As economic operator are liable for the accuracy of the DPP data, DPP revocation is a useful feature in case an error has been detected and a new DPP must be issued. Revocation can also be useful for products with “use until” constraints. 
- **Proving data authenticity**: In a world where it is very easy to generate fake product data, an organisation making use of DPP data for their own commercial operations (e.g. a professional purchasing company) can limit their liability if they are able to provide proofs that they are indeed using authentic data. 
- **Timestamps**:  The timestamp inherent to the VC issuing helps improving the DPP data quality and supports liabilities related to claims. 
- **Integrity over time**: Differently from HTTPS which provides integrity during data transmission, the VC’s timestamps also supports DPP integrity, in the sense of absence of change, over time.  
- **Privacy**: The default HTTPS request provides no privacy for a party retrieving DPP data, e.g. a consumer. If the DPP is “held” by a third party, e.g. a retail store, the DPP copy held by the third party can be accessed and authenticated by the consumer instead of the version held by the issuing economic operator. This protects the privacy of the consumer. For example, if the DPP is for a medication, access to the DPP can reveal information about the user’s medical condition. 


# Why is there an international DPP Task Force in W3C Verifiable Credentials Working Group (VCWG)?
The following list of topics should be discussed:
- Current lack of international meeting place to work on linked data + VC-based DPPs. 
- Multiplicity of DPP vocabs and protocols (including standards), if linked data is used to enforce strong semantic interoperability for DPP.
- Importance of DPP data fusion for DPP. 
- Other VCWG Task forces working on closely related technology to DPP : VC Business Wallet Vocabularies, VC Recognized Entities, VC Barcodes and Data Integrity 
- Definition of international DPP “Use cases”:
    - Single-protocol “use cases”: Issuing an EU-compliant DPP ; Issuing an UNTP-compliant DPP ; Issuing an XYZ-compliant DPP
    - Multi-protocol “use cases”: Linking DPPs (possibly of different flavors) : a product with a DPP can have a component/material that has a DPP; Linking product-related claims using different protocols e.g. EU DPP containing a link to an UNTP claim. Linking product-related events using different DPP protocols ; Retrieving and combining data from DPPs from multiple standards. E.g. a Vehicle DPP references component DPPs that are built all over the world and according to different DPP standards/vocabularies. 

# Is DPP standard “X” compatible with VCDM ?
- Applicability of VCDM model to DPPs (EU/others) 
- question about credential subject and product identifier…
- A guidance document for creating VCDM-based DPPs. 
- A test-suite for DPPs based on VCDM ?
- A DPP-playground like environment
- An example of an EU-DPP implementation based on VCDM.


