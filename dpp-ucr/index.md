# Introduction
A verifiable credential (VC) is a mechanism for issuing authenticated, revokable and portable data in a tamper-proof way to a "data holder" that also provides a privacy-preserving mechanism to verify this data by a third party (i.e., the “verifier” does not reveal anything about the "holder" when performing this verification). Thus, VCs are useful tools for encapsulating product-related claims: e.g. providing copyright proofs for merchandised products, ESG performance certifications, declarations of conformity, customs clearance proofs, etc., that might be accessed from a DPP. 

This note aims to investigate why, in some cases, it might be useful to issue a DPP as a VC, explain why a DPP task force has been created in the W3C VCWG and discuss compatibility of DPP standards with the VCDM VC format. 

# Digital product passports in international value chains
Digital product passports can be used to convey information about finished goods, components, intermediate products and materials. While sometimes they are given other names, e.g. "Material passports", "Circularity passport" etc., in this report, we assume that all of these are functionally equivalent. DPPs can therefore be defined at all stages of the supply-chain, from upstream raw material extraction to downstream Circular Economy materials recovery, as illustrated in the figure below:

<img width="886" height="429" alt="image" src="https://github.com/user-attachments/assets/f533b438-e0ed-45d2-b9c5-1c873c86587e" />

The use of VCs in the DPP context is closely related to the use of VCs for the transport of all types of machine-readable product-related claims: declarations of conformity, test reports by accredited laboratories and conformity assessment bodies, standards compliance certificates, purchase proofs, product life-cycle events, etc. By linking these digital documents from a product's DPP, data quality improves and greater trust can be achieved. 

# How are Verifiable Credentials used in DPP applications?
In general, because the DPP contains data about a product, when an economic operator decides to issue a DPP as a VC, the credential subject of the VC is the globally unique product identifier. There are many globally recognized standards for globally unique product identifiers: ISO/IEC 15459, IEC 61406-x, DIDs, etc. <mark> And also many globally recognized standards for generating a web link associated to the globally unique product identifier. But which one is the credential subject ? </mark>

There are many ways to share a DPP issued as a VC:
- The organisation issuing the DPP remains the holder of the VC, i.e. the issuer is also the holder. The DPP is thereforme made available in the issuer's wallet.
- A copy of the VC is made available by a third party, e.g. an online marketplace. The DPP is therefore made available through the online marketplace's wallet.
- The VC is made available in the product's wallet. The product wallet concept is a convenient approach for the collection of all related VCs about a product.  <mark> @Susanne, please correct/elaborate </mark>

We observe that, differently from the classic "identity" use case where holder binding between the credential subject and the holder's wallet is an important property, the need for holder binding is more complex in DPP use cases. Certain applications may not require any holder binding while others might require multiple holder bindings. Certain advanced applications where the product itself acts as an agent (i.e. a car requesting energy from an electric charging station) may require strong holder binding to ensure that the DPP provided is indeed authorized to make claims about the car.  <mark> @Ronald, please correct/elaborate </mark>

# Why are VCs useful for DPPs? 
The following list provides a number of use cases where VCs provide additional capabilities with respect to HTTPS.  <mark> This section must be improved to identify how VCs offer value beyond other digital signatures. </mark>

- **Authenticity of the DPP**. The electronic signature of the economic operator that signs the DPP makes it "authentec". That means, it is possible to identify the actor that issued the DPP;
- **Non-Repudiation of the DPP-Issuer**. The economic operator that signed the DPP cannot deny having issued product information, also called non-repudiation. (Should we add information about a trust anchor here?)
- **Detect modifications of a DPP**. The electronic signature makes it possible to determine if the DPP has been modified / tampered with after issuance. This is also called verifying the "integrity" of a DPP and can be detected if the validation of the electronic signature fails.
- **Increase trust in the DPP data**. The fact that the authenticity, non-repudiation, and integrity of a DPP becomes verifiable its trustworthyness.
- **Data sovereignty + business confidentiality**. Because economic operators stores its signed DPPs decentrally, they also has the possibility to control access to them. The economic operator can thus ensure that competitors do not gain access to any company secrets, but that only people with legitimate interest (e.g. an auditor, a customer, a recycler or a market surveillance authority) can view the data relevant to them.
- **Real-time DPP updates**. (To be discussed) If product information changes or must be added (e.g. State of Health (SoH)), a Digital Identity Wallet allows to receive all Verifiable Credentials for a given subject ID in real time of a credential store. That means, by issuing VCs to a product wallet, DPP updates can become visible for all authorized actors in real-time.
- **Identifying the issuer of the DPP**: (Review) In many trade and logistics supply-chains, the DPP data may be stored and used locally by different “holders”. Thus, the server hosting the DPP may provide no information on the actually issuer of the data.   
- **DPP revocation**: As the economic operator is responsible for the accuracy of the DPP data, DPP revocation is a useful feature in case an error has been detected and a new DPP must be issued. Revocation can also be useful for products with “use until” constraints. 
- **Proving data authenticity**: (Review - maybe merge with non-repudiation)In a world where it is very easy to generate fake product data, an organisation making use of DPP data for their own commercial operations (e.g. a professional purchasing company) can limit their liability if they are able to provide proofs that they are indeed using authentic data.
- **Timestamps**:  The timestamp inherent to the VC issuing helps improving the DPP data quality and supports liabilities related to claims.
- **Integrity over time**: Differently from HTTPS which provides integrity during data transmission, the VC’s timestamps also supports DPP integrity, in the sense of absence of change, over time.  
- **Privacy**: The default HTTPS request provides no privacy for a party retrieving DPP data, e.g. a consumer. If the DPP is “held” by a third party, e.g. a retail store, the DPP copy held by the third party can be accessed and authenticated by the consumer instead of the version held by the issuing economic operator. This protects the privacy of the consumer. For example, if the DPP is for a medication, access to the DPP can reveal information about the user’s medical condition.
- **Business confidentiality**: This is provided through several mechanisms. For the DPP provider, through selective disclosure of DPP content. For the DPP requestor, if the DPP is “held” by a third party.
- **Legal evidence**: <mark> Rigo to elaborate. How do VCs go beyond normal digitally signed documents? </mark>
- **Quantum resistance**: The VCWG task force on Confidence Methods will define a mechanism that can be used with the Verifiable Credentials Data Model v2.0 to increase a verifier's confidence about a particular subject identified in a verifiable credential. <mark> The REC mentions that the goal is to "increase a verifier's confidence that a presenter of a verifiable credential is, in fact, appropriately related for its use." So this approach is only used for VPs? </mark>

# Why are VPs useful for DPPs? 
- Are Verifiable Presentations useful in DPP use cases? Yes : A VP is ephemeral. It can transport several VCs packaged together, while retaining the signature of each plus the signature of the VP (i.e. the signature of the VC holder) so you know who assembled the package. Alternatively, the signature of each VC can be removed and then only the signature of the VP issuer remains. For example, in the education sector, VCs containing the grades of each individual course are collected into a VP of the diploma.
- The packaging of credentials together is relevant both for any credentials related to claims contained in the DPP and for credentials related to proving the issuer is a recognized entity of a trustworthy third-party (e.g. a business registrar.)
- <mark> Are there arguments against the use of VPs ? (Steve) </mark>
- VPs can be used for selective disclore of claims contained in a DPP. This is a useful feature for disclosing selected data sets to parties on a need-to-know basis. 

# Why is Linked Data useful for DPPs? 
<mark> Elaboration needed. Thank you </mark>
- Provides explicit context and semantic interoperability
- Elimintates semantic conflicts in data ingestion
- Offers combinability properties for data. 
- Improves AI-based data exploitation. 

# Why is there an international DPP Task Force in W3C Verifiable Credentials Working Group (VCWG)?
The following list of topics should be discussed:
- Current lack of international meeting place to work on linked data + VC-based DPPs. 
- Multiplicity of DPP vocabs and protocols (including standards), if linked data is used to enforce strong semantic interoperability for DPP.
- Importance of DPP data fusion for DPP. 
- Other VCWG Task forces working on closely related technology to DPP : VC Business Wallet Vocabularies, VC Recognized Entities, VC Barcodes and Data Integrity.  The VCWG may need to consider how to present linked VCs in a VP.
- How can one know if the VC/DPP issuer is a valid issuer? This topic is related to the recognized entity work by the VCWG.
- Definition of international DPP “Use cases”:
    - Single-protocol “use cases”: Issuing an EU-compliant DPP ; Issuing an UNTP-compliant DPP ; Issuing an XYZ-compliant DPP
    - Multi-protocol “use cases”: Linking DPPs (possibly of different flavors) : a product with a DPP can have a component/material that has a DPP; Linking product-related claims using different protocols e.g. EU DPP containing a link to an UNTP claim. Linking product-related events using different DPP protocols ; Retrieving and combining data from DPPs from multiple standards. E.g. a Vehicle DPP references component DPPs that are built all over the world and according to different DPP standards/vocabularies. 

# Is DPP standard “X” compatible with VCDM ?
In this section, we must explain that there is not a single "DPP standard" but rather a multiplicity of DPP standards. 

## The product as credential subject

A digital product passport attests facts **about a product** — its composition, origin, conformity status, repairability, environmental performance, and so on. In the [Verifiable Credentials Data Model (VCDM) 2.0](https://www.w3.org/TR/vc-data-model-2.0/), claims are always made about a **subject**. For a DPP expressed as a verifiable credential, the natural subject is therefore the **product** itself, not the issuing economic operator, the data holder, or any other party involved in the supply chain.

Concretely, the `credentialSubject` property of a DPP VC carries the product-related claims, and `credentialSubject.id` identifies **which product** those claims describe. All DPP standards — whether EU Battery Regulation, ESPR, UNTP, or sector-specific frameworks — ultimately need a stable, globally interoperable way to identify the product that the passport describes. VCDM provides the mechanism; the choice of identifier determines interoperability across standards and value chains.

## VCDM allows URLs as credential subject identifiers

Section 4.4 ("Identifiers") of [VCDM 2.0](https://www.w3.org/TR/vc-data-model-2.0/#identifiers) defines an optional `id` property for objects within a verifiable credential, including the credential subject. When present, the value of `id` **must be a single URL**, which may be dereferenceable. The specification explicitly lists HTTP URLs alongside UUIDs and Decentralized Identifiers (DIDs) as valid examples:

> Example `id` values include UUIDs (`urn:uuid:…`), HTTP URLs (`https://id.example/things#123`), and DIDs (`did:example:1234abcd`).

Importantly, DIDs are **not required**. The specification states that "verifiable credentials do not depend on DIDs and DIDs do not depend on verifiable credentials." For products identified through supply-chain standards rather than through cryptographic key pairs, a resolvable HTTP(S) URL is a first-class, fully conformant choice for `credentialSubject.id`. The specification further recommends that, where the URL is dereferenceable, it should resolve to machine-readable information about the identified thing — a property that well-designed product identifier URIs can satisfy through linked-data resolvers.

## GS1 Digital Link as credentialSubject.id for DPP VCs

The [GS1 Digital Link](https://www.gs1.org/standards/gs1-digital-link) standard defines a Web URI syntax for GS1 identification keys — the same keys that appear in barcodes, RFID tags, and product catalogues worldwide. A GS1 Digital Link URI (DLURI) encodes Application Identifiers as path and query elements, making it both a valid Web address and a precise GS1 identifier. This dual nature makes DLURIs an excellent fit for `credentialSubject.id` in DPP verifiable credentials.

### Identifying a product with a GTIN Digital Link URI

The Global Trade Item Number (GTIN, Application Identifier `01`) identifies a trade item — a product or product class. Its canonical Digital Link form is:

```
https://id.gs1.org/01/{gtin}
```

For example, `https://id.gs1.org/01/09520123456788` identifies GTIN 95201234567888 and is informationally equivalent to the barcode element string `(01)09520123456788`. Key qualifiers can refine the identifier to match the granularity required by a given DPP:

| Granularity | Qualifier (AI) | Example URI |
|-------------|----------------|-------------|
| Product class (trade item) | — | `https://id.gs1.org/01/09520123456788` |
| Consumer product variant | CPV (`22`) | `https://id.gs1.org/01/09520123456788/22/2A` |
| Batch / lot (LGTIN) | Batch/lot (`10`) | `https://id.gs1.org/01/09520123456788/10/ABC123` |
| Serialized instance (SGTIN) | Serial (`21`) | `https://id.gs1.org/01/09520123456788/21/12345` |

Using a GTIN-based DLURI as `credentialSubject.id` means that the same identifier appears on the product's barcode/QR code, in the manufacturer's product catalogue, in logistics systems, and in the DPP verifiable credential — enabling seamless linking of product-related claims across the entire value chain without identifier translation.

The [GS1 Verifiable Credentials Data Model](https://ref.gs1.org/gs1/vc/data-model/1.0.1/) already mandates that the `credentialSubject.id` of a GS1 Data Credential must be a GS1 Digital Link URI, and uses GTIN DLURIs in its Product Data Credential profile. This establishes a concrete, standards-based pattern that DPP implementers can adopt directly.



## Remaining topics

- Applicability of VCDM model to DPPs (EU/others) 
- A guidance document for creating VCDM-based DPPs. 
- A test-suite for DPPs based on VCDM ?
- A DPP-playground like environment
- An example of an EU-DPP implementation based on VCDM.

# Glossary

