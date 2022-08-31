Introduction
This project defines a set of attack flows tailored to a cloud-enabled telesurgery system.

Project Scope
This project is focused on threats, attacks and countermeasures that are patient-safety focused. This may include any threat that would result in the disruption of an operation. This includes threats to the availability of the robotic telesurgery system, threats to the integrity and availability of bio-health and telmetry data needed to effectively operate the machinery and evaluate the status of the patient, and threats to cloud services that support diagnostic and other patient-critical functions such as machine learning and data processing.

Methodology
Publicly-known attacks against hospital operations and medical devices have been documented and mapped to applicable attack flows. Since the technology in review is constantly evolving, theoretical attacks have also been included. When possible, the origin of the attack flow has been marked for each flow (e.g., realized vs theoretical). Design critiria for this project include:

Attack flows are patient-safety-focused. They should be designed from the perspective of protecting the patient. This will allow for easier buy-in from HDOs.

Attack flows should be modular. Although many attack trees grow significantly, a modular approach makes it easier to manage the flows and supports mixing and matching to create multiple attack pathways. Modularity should be based on key decision points in an attack process (for example, once you've compromised a key, the attacker can move on to other attacks). Modularity is represented through the integration of multiple, modular files.

A set of modular attack flow files represents an attack use case. The attack use case is the patient-focused artifact that is composed of many attack flows.

This project integrates the MITRE ATT&CK techniques (https://attack.mitre.org/). This will allow HDOs to leverage ATT&CK technique mitigations in an enterprise security architecture.

Attack flows will form the basis for a STRIDE-based threat model. Nodes in the attack flow will correspond to nodes in the STRIDE analysis.

System Description
A robotic telesurgery system is composed of two primary onsite components: (1) a surgeon console, and (2) a Robotic Platform. The system also includes a variety of biosensors and telemetry sensors, communication capabilities, cloud SaaS services, and Electronic Health Record (EHR) interfaces. A surgeon, surgeon assistant and patient all play a role in the surgical activity. Additional staff that may be present include representatives from the vendor, technicians and biomedical staff.
image

Patient-Centered Attack Flows
We want to protect the patient from harm, so we must guard against misconfigurations / firmware tampering, etc in the robotic device.

Attack flow id	Description
AF-001	Attack Flow: Authorized personnel unknowingly upload malicious firmware to robotic device. Device does not validate authentication and integrity of firmware upload.
this is a real-world example... biomed firmware mfg rep coming in to service the device; infected copy of firmware used to restore device to service.

AF-002	Attack Flow: Attacker modifies robotic device firmware through compromise of the vendor software update process (note: potential multi-patient effect).
automated software update on the device is not configured properly...

AF-003	Attack Flow: Attacker modifies robotic device configuration file through compromise of a management system on the network... (differntiate from next one)...
most devices have mgmt console; any way to compromise the mgmt console will work/ phishing, etc...

AF-004	Attack Flow: Attacker modifies device configuration settings through physical access to the device.
phyiscally in the room, with access to front panel of device...

AF-005	Attack Flow: Attacker infects robotic device with virus/malicious code through cloned hard-drive, other means.
changing a part in the system, that has a software/firmware component, results in compromise... real-world; compromised medical supply chain... Chris to look up...

We want to protect the patient from harm, so we must ensure the availabiity of the supporting cloud services. (e.g. can't perform radiation verification because csp was attacked).
AF-006	Attack Flow: Attacker performs a denial of service through a network flood.
device telemetry, biohealth data, target the egress circuit, or the cloud endpoints

AF-007	Attack Flow: Attacker encrypts critical file on the device through ransomware.
file to boot device, configuration file, various files could be targeted...

AF-008	Attack Flow: Attacker performs attack on cloud service provider (CSP) that renders biohealth data unavailable.
attack on the collection of biohealth data in the cloud, or the analysis from that data back to system...

note: scope is restricted to device operations... add this to introduction...

AF-009	Attack Flow: Attacker performs attack on cloud provider resulting in a lack of AI capability (results in further delay to care).
note: scope is restricted to device operations... add this to introduction...

We want to protect the patient from harm, so we must ensure that a remote clinician has an accurate view of patient status.
AF-010	Attack Flow: Attacker modifies bio-sensor readings through tampering with biosensor data, or devices.
most surgeries have nurse to monitor vitals; if vitals change, change course of surgery by notifying doctor; halt surgery, take medical action, etc...

AF-011	Attack Flow: Attacker modifies notification messages meant for the clinician through tampering with data.
hold on this one, get feedback first...

We want to protect the patient from harm, so we must ensure that remote commands to the robotic device cannot be modified.
AF-012	Attack Flow: Attacker modifies commands sent to the device through tampering with the data.
need to get confirmation from vendors, is remote link active typically for manufacturing access, updates, etc...

We want to protect the patient from harm, so we must ensure the abailability of supporting communication infrastructure
AF-013	Attack Flow: Attacker disables / disrupts network connectivity within the operating environment.
e.g., access to router, etc to turn off, change settings, etc...

clinical impact: no telemetry, typically all in room, ask manufacturer, are commands sent to robotic system going over HDO network or through seperate manufacturer connection (eg.. cellular)

We want to ensure that if something goes wrong in the system, that the root cause can be traced and identified
AF-014	Attack Flow: Attacker modifies log files within a device
AF-015	Attack Flow: Attacker modfies log files within a CSP
We want to ensure that patient privacy is protected
AF-016	Attack Flow: Attacker gains unauthorized access to PHI data stored locally on robotic device hard drive or other local device.
verify with manufacturer, maybe on the hard drive, etc...

We want to ensure that the environment of the operation is maintained
AF-017	Attack Flow: Attacker is able to disrupt power to the room.
AF-018	Attack Flow: Attacker modifies the HVAC settings in the operating room, disrupting temperature
AF-018	Attack Flow: Attacker disrupts the medical air settings used within the operating room.
AF-018	Attack Flow: Attacker disrupts the humidity settings within the operating room.
AF-018	Attack Flow: Attacker disables water flow to the operating room.
We want to ensure that the attacker cannot prepare effectively for an attack against the robotic platform
AF-019	Attack Flow: Attacker is able to scan the components on the network.
AF-020	Attack Flow: Attacker is able to stage malicious files within the hospital network.
AF-021	Attack Flow: Attacker is able to perform a successful phishing attack on hospital personnel.
Contributors
