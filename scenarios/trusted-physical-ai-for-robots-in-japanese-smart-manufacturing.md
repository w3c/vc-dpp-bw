### Trusted Physical AI for robots in Japanese smart manufacturing

**Actors:**
- Akira — production lead, Sakura Robotics Works (site operator)
- Robotics vendor — robot manufacturer and AI supplier
- System integrator — safety integration specialist
- Validation bodies — robot skill certification authorities
- Factory access control system — verifier (zone enforcement)

**Preconditions:** Sakura Robotics Works holds a Business Wallet with site operator, occupational safety, and production-site authorisation credentials. Each robot holds an identity credential bound to its serial number, a DPP, and an AISP for its Physical AI control stack. Task-specific Agent PoAs are issued by Sakura's Business Wallet per work zone and time window.

**Trigger:** A robot is assigned to enter a restricted work zone at the Nagoya manufacturing facility to perform a defined inspection task under a task-specific Agent PoA.

**Postconditions:** The robot has completed the task within the authorised zone, time window, and speed/force limits. All operational events are signed at the edge and linked to the AISP version and task-specific PoA in the plant audit trail. A perception model defect flagged by the vendor updates the AISP status, blocking autonomous operation in affected zones immediately.

---

Akira is the production lead at Sakura Robotics Works, a Japanese industrial robotics operator running a smart manufacturing site in Nagoya. The site uses humanoid robots and mobile manipulation robots for inspection, material handling, surface preparation, welding support, and maintenance in areas that are hard, repetitive, or unsafe for people.

The robots use cameras, depth sensors, force sensors, path planning, robot foundation models, and edge safety controllers. Some robot skills are trained in simulation before they are used on the factory floor. Some skills are supplied by a Japanese robotics vendor. Other modules come from European and U.S. software providers. The system must work near humans, machines, moving parts, and safety zones.

Today, the plant can test a robot in a lab, but the production system cannot always verify which AI model version is running on the robot, which skill was validated, which safety limits apply, whether the robot may enter a zone, and whether the remote supervisor has the right mandate. The same robot can move between sites, tools, tasks, and software versions. Paper approvals cannot control this in real time.

What Akira and Sakura Robotics Works need is a verifiable trust chain for Physical AI. The system must prove the identity of the robot, the legal identity of the operator, the status of the robot system, the validation state of the AI service, the task authorisation, and the human oversight mandate. It must also allow immediate revocation if a model, tool, safety function, or operator mandate is no longer valid.

Sakura Robotics Works loads its Business Wallet with a legal person identity credential, site operator credential, occupational safety credentials, and production-site authorisations. The robotics vendor loads its Business Wallet with a legal person identity credential, manufacturer credential, quality credential, cybersecurity credential, and robot conformity credentials. The system integrator holds legal person identity and safety integration credentials.

Each robot receives a robot identity credential bound to its serial number, hardware configuration, secure element, firmware baseline, and approved tool interfaces. Each robot also receives a Digital Product Passport credential for lifecycle data, including manufacturer, model, critical components, maintenance status, battery health, tool modules, safety sensors, and software bill of materials.

The robot’s Physical AI control stack receives an AI Service Passport. The AISP records the AI service operator, model family, model version, software hash, training data classes, simulation environment, tested scenarios, known limits, guardrails, human-in-the-loop rules, runtime monitoring, fallback behaviour, incident history, update history, and TEVV evidence. Validation bodies issue robot skill validation credentials for tasks such as inspection, surface scanning, and welding support.

Before a robot enters a restricted work zone, the access system performs machine-to-machine verification. The robot presents its robot identity credential, DPP credential, AISP, active skill credential, maintenance status credential, and a task-specific Agent PoA issued by Sakura’s Business Wallet. The PoA states that the robot may enter a defined zone, during a defined time window, for a defined task, under defined speed and force limits.

During operation, the robot signs operational events at the edge. The events include task start, task completion, detected anomaly, human override, emergency stop, model version, sensor configuration, and operator intervention. The events are linked to the AISP and to the task-specific PoA. The plant receives an audit trail showing what the robot did, under which authority, with which AI model, in which zone, and under whose supervision.

Later, the robotics vendor finds that one perception model has reduced performance under strong backlight. The vendor updates the status of the affected AISP. Sakura’s fleet management system detects the change. Robots using that AISP version are blocked from autonomous inspection in affected zones until a patched and revalidated AISP is issued.

**Requirements:** Authentication/proof of control, legal person identity, robot identity, robot Digital Product Passport, AI Service Passport, task-specific Agent PoA, site access credential, operator credential, robot skill validation credential, safety integration credential, TEVV evidence, simulation evidence, ISO/IEC 42001 operator credential, NIST AI RMF operator credential, real-time credential status and revocation, machine-to-machine verification, policy-based access control, human-in-the-loop and human override, edge audit trail, safety-zone enforcement, non-repudiation, incident traceability, model-version control, tool authorisation, maintenance status verification, cannot be administratively denied.

Contributed by Spherity GmbH
