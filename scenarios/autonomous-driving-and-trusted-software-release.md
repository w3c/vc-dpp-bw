### Autonomous driving and trusted software release

**Actors:**
- Daniel — safety and homologation lead, UrbanFleet Mobility (operator)
- Japanese ADS software and robotics supplier — system supplier
- U.S. lidar sensor supplier — hardware supplier
- German remote supervision centre — certified control centre
- City mobility platforms (Rotterdam, Antwerp, Hamburg) — verifiers

**Preconditions:** UrbanFleet holds a Business Wallet with operator, insurance, and city operating permit credentials. Each vehicle holds an identity credential linked to its VIN and DPP. The Japanese ADS supplier holds an AISP for the automated driving stack and a software release credential for the current version.

**Trigger:** UrbanFleet prepares an autonomous shuttle for entry into service in Hamburg and presents a machine-readable proof to the city mobility platform for authorisation.

**Postconditions:** The city platform has verified the complete credential chain including operator identity, vehicle identity, software release, ODD, and remote supervision mandate. Any critical software vulnerability that triggers AISP revocation causes automatic blocking of affected vehicles across all city platforms until a patched release is verified.

---

Daniel is the safety and homologation lead at UrbanFleet Mobility, a Dutch operator of autonomous electric shuttle buses. UrbanFleet operates vehicles in Rotterdam, Antwerp, and Hamburg. The vehicles use an automated driving stack from a Japanese software and robotics supplier, lidar sensors from a U.S. supplier, and remote supervision services from a certified control centre in Germany.

Each city authority requires proof that the vehicles are approved for their operational design domain. They also require proof that the current software version is authorised, that cybersecurity controls are valid, that the remote supervision centre is allowed to act, and that the operator has insurance and operating approval.

Today, UrbanFleet submits type-approval documents, safety case documents, software release notes, cybersecurity certificates, sensor calibration reports, and operator licences through separate local portals. When a software update is released, UrbanFleet must prove again that the release belongs to the approved branch and does not exceed the approved operational design domain. This is slow and hard to audit.

What UrbanFleet needs is a verifiable trust chain between the legal persons, the vehicle, the autonomous driving system, the software release, the operational design domain, the remote operator, and the public authority. Each role must be clear. Each software release must be traceable. Each authorisation must be revocable.

UrbanFleet loads its Business Wallet with a legal person identity credential, fleet operator credentials, insurance credentials, and city operating permits. The Japanese automated driving supplier loads its Business Wallet with a legal person identity credential, software supplier credential, cybersecurity credential, and AI Service Passport (AISP) for the automated driving stack. The vehicle receives a vehicle identity credential linked to its VIN and its Digital Product Passport. The software release receives a credential that identifies the exact model version, software hash, safety case, approved operational design domain, and release authority.

Before a shuttle enters service in Hamburg, the vehicle presents a machine-readable proof to the city mobility platform. The proof contains UrbanFleet’s operator credential, the vehicle identity credential, the software release credential, the operational design domain credential, and the remote supervision mandate. The city platform verifies all credentials and checks their status.

During operation, the vehicle can present the same proof to roadside infrastructure, an inspection authority, or an incident investigation system. It does not disclose unrelated fleet data or commercial contracts. It discloses only the claims needed to prove lawful and safe operation.

Later, a critical vulnerability is found in one software release. The supplier updates the status of the affected software release credential and the related AISP. Vehicles using that release fail the next verification check. City platforms and fleet systems can block autonomous operation until a patched and validated release is issued.

**Requirements:** Authentication/proof of control, legal person identity, vehicle identity, software release identity, AI Service Passport, operational design domain credential, remote supervision mandate, credential delegation and scoped authorization, mutual authentication, machine-to-machine data exchange, cybersecurity status, safety-case linkage, real-time credential status and revocation, verifiable audit trail, human oversight, cannot be administratively denied.

*Contributed by Spherity GmbH*
