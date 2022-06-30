<h1> Introduction </h1>

This project defines a set of attack flows tailored to a cloud-enabled telesurgery system. 

<h1> Project Scope </h1>

This project is focused on threats, attacks and countermeasures that are patient-safety focused. This may include any threat that would result in the disruption of an operation. This includes threats to the availability of the robotic telesurgery system, threats to the integrity and availability of bio-health and telmetry data needed to effectively operate the machinery and evaluate the status of the patient, and threats to cloud services that support diagnostic and other patient-critical functions such as machine learning and data processing. 

<h1> Methodology </h1> 

Publicly-known attacks against hospital operations and medical devices have been documented and mapped to applicable attack flows. Since the technology in review is constantly evolving, theoretical attacks have also been included. When possible, the origin of the attack flow has been marked for each flow (e.g., realized vs theoretical). Design critiria for this project include: 

* Attack flows are patient-safety-focused. They should be designed from the perspective of protecting the patient. This will allow for easier buy-in from HDOs.

* Attack flows should be modular. Although many attack trees grow significantly, a modular approach makes it easier to manage the flows and supports mixing and matching to create multiple attack pathways. Modularity should be based on key decision points in an attack process (for example, once you've compromised a key, the attacker can move on to other attacks). Modularity is represented through the integration of multiple, modular files.

* A set of modular attack flow files represents an attack use case. The attack use case is the patient-focused artifact that is composed of many attack flows.

* This project integrates the MITRE ATT&CK techniques (https://attack.mitre.org/). This will allow HDOs to leverage ATT&CK technique mitigations in an enterprise security architecture.

* Attack flows will form the basis for a STRIDE-based threat model. Nodes in the attack flow will correspond to nodes in the STRIDE analysis.

<h1> System Description </h1>
A robotic telesurgery system is composed of two primary onsite components: (1) a surgeon console, and (2) a Robotic Platform. The system also includes a variety of biosensors and telemetry sensors, communication capabilities, cloud SaaS services, and Electronic Health Record (EHR) interfaces. A surgeon, surgeon assistant and patient all play a role in the surgical activity. Additional staff that may be present include representatives from the vendor, technicians and biomedical staff.

![image](https://user-images.githubusercontent.com/10893218/176735956-c2c6ab88-b57c-4aa3-89c0-d5f7bf76b634.png)


<h1> Contributors </h1> 

