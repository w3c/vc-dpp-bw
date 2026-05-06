### EV charging and legal persons

**Actors:**
- Liang — fleet operations manager, SinoMove Europe GmbH (fleet operator)
- SinoMove delivery vans — fleet vehicles (delegated subjects)
- Charge point operators (CPOs) — charging infrastructure operators
- E-mobility service providers (eMSPs) — roaming intermediaries
- Charging stations (EVSEs) — technical endpoints

**Preconditions:** SinoMove holds a Business Wallet with legal person, VAT, fleet operator, and payment account credentials. Each vehicle holds a vehicle identity credential and a fleet delegation credential scoped to country, tariff class, and validity period. Each CPO and eMSP holds a Business Wallet with legal person, VAT, and market role credentials.

**Trigger:** A SinoMove delivery van connects to a charging station in Germany to recharge, initiating a mutual authentication and billing session.

**Postconditions:** The charging session is recorded as a signed session record binding vehicle, EVSE, metered energy, cost, and renewable energy claim. SinoMove's ERP receives a tamper-evident billing record. Vehicle removal from the fleet immediately revokes the delegation credential, preventing further charges to SinoMove's account.

---

Liang is the fleet operations manager at SinoMove Europe GmbH, the European subsidiary of a Chinese EV manufacturer. SinoMove operates electric delivery vans across Germany, the Netherlands, Belgium, and France. The vans charge through several charge point operators, roaming platforms, and e-mobility service providers. Drivers use plug-and-charge, mobile apps, and fleet contracts.

At the end of each month, SinoMove receives invoices from many providers. The invoices contain different tariff structures, VAT treatment, charging session records, and renewable energy claims. Some sessions are assigned to the wrong vehicle. Some are billed to the wrong cost centre. In one case, a charging location was changed in the roaming chain before the invoice reached the ERP system.

What Liang needs is a trust framework in which the fleet operator, the vehicle, the charge point operator, the e-mobility service provider, the charging station, and the payment account can be verified as legal or technical subjects. The system must support cross-border charging, correct billing, verified VAT handling, scoped delegation from the company to the vehicle or driver, and audit evidence for every session.

SinoMove Europe loads its Business Wallet with a legal person identity credential, VAT credential, fleet operator credential, and payment account credential. Each vehicle receives a vehicle identity credential and a fleet delegation credential. The delegation states that the vehicle is authorised to charge on SinoMove’s account within defined countries, tariff classes, contract IDs, and validity periods.

Each charge point operator and e-mobility service provider holds a Business Wallet with legal person identity, VAT status, market role, and endpoint credentials. Each charging station holds a technical credential proving its EVSE identity, location, operator, metering calibration status, and certification status.

When a SinoMove van connects to a charging station in Germany, the vehicle and charge point perform mutual authentication. The vehicle presents its vehicle credential and fleet delegation credential. The charge point presents its EVSE credential, operator credential, and routing credential. The roaming platform verifies that the vehicle may charge for SinoMove and that the charge point is operated by a verified legal person.

At the end of the session, the charging station creates a signed charging session record. The record includes the EVSE identifier, vehicle identifier, contract identifier, metered energy, timestamp, tariff reference, location, CPO identifier, eMSP identifier, and renewable energy claim where applicable. The charge point operator seals the record and sends it to SinoMove’s ERP. Any change to the metered energy, bank account, VAT number, or location breaks the integrity check.

When one van leaves the fleet, SinoMove revokes the vehicle’s delegation credential. From that moment, the vehicle can no longer charge on SinoMove’s account, even if an old card or cached contract reference still exists.

**Requirements:** Authentication/proof of control, legal person identity, vehicle identity, EVSE identity, charge point operator credential, e-mobility service provider credential, market-role credentials, credential delegation and scoped authorization, mutual authentication, machine-to-machine data exchange, qualified electronic seal where required, verifiable audit trail, real-time credential status and revocation, verified billing data, verified VAT and payment data, credential portability across roaming platforms, survives service-provider changes, cannot be administratively denied.

*Contributed by Spherity GmbH*
