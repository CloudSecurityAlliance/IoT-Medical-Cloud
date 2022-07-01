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

<h1> Patient-Centered Attack Flows </h1> 

**We want to protect the patient from harm, so we must guard against misconfigurations / firmware tampering, etc in the robotic device.**
<table>
<tr> <th width = "100"> Attack flow id  </th> <th> Description </th> </tr> 
<tr> <td> AF-001 </td> <td> Attack Flow: Authorized personnel unknowingly upload malicious firmware to robotic device. Device does not validate authentication and integrity of firmware upload.   

`this is a real-world example...  biomed firmware mfg rep coming in to service the device; infected copy of firmware used to restore device to service.` </td> </tr>
<tr> <td> AF-002 </td> <td> Attack Flow: Attacker modifies robotic device firmware through compromise of the vendor software update process (note: potential multi-patient effect). 

`automated software update on the device is not configured properly... `</td> </tr>
<tr> <td> AF-003 </td> <td> Attack Flow: Attacker modifies robotic device configuration file through compromise of a management system on the network... (differntiate from next one)... 

`most devices have mgmt console; any way to compromise the mgmt console will work/ phishing, etc...` </td> </tr>
<tr> <td> AF-004 </td> <td> Attack Flow: Attacker modifies device configuration settings through physical access to the device. 

` phyiscally in the room, with access to front panel of device...` </td> </tr>
<tr> <td> AF-005 </td> <td> Attack Flow: Attacker infects robotic device with virus/malicious code through cloned hard-drive, other means. 

` changing a part in the system, that has a software/firmware component, results in compromise... real-world; compromised medical supply chain... Chris to look up...` </td> </tr>
<tr> <th colspan="2"> We want to protect the patient from harm, so we must ensure the availabiity of the supporting cloud services. (e.g. can't perform radiation verification because csp was attacked). </th> </tr>

<tr> <td> AF-006 </td> <td> Attack Flow: Attacker performs a denial of service through a network flood.  

`device telemetry, biohealth data, target the egress circuit, or the cloud endpoints`</tr>
<tr> <td> AF-007 </td> <td> Attack Flow: Attacker encrypts critical file on the device through ransomware.

`file to boot device, configuration file, various files could be targeted...` </tr>
<tr> <td> AF-008 </td> <td> Attack Flow: Attacker performs attack on cloud service provider (CSP) that renders biohealth data unavailable. 

`attack on the collection of biohealth data in the cloud, or the analysis from that data back to system... `

`note: scope is restricted to device operations... add this to introduction...` </tr>
<tr> <td> AF-009 </td> <td> Attack Flow: Attacker performs attack on cloud provider resulting in a lack of AI capability (results in further delay to care). 

`note: scope is restricted to device operations... add this to introduction...` </tr>

<th colspan="2"> We want to protect the patient from harm, so we must ensure that a remote clinician has an accurate view of patient status.</th>

<tr> <td> AF-010 </td> <td> Attack Flow: Attacker modifies bio-sensor readings through tampering with biosensor data, or devices. 

`most surgeries have nurse to monitor vitals; if vitals change, change course of surgery by notifying doctor; halt surgery, take medical action, etc... `</td> </tr>
<tr> <td> AF-011 </td> <td> Attack Flow: Attacker modifies notification messages meant for the clinician through tampering with data. 

`hold on this one, get feedback first... `</td> </tr>


<th colspan = 2> We want to protect the patient from harm, so we must ensure that remote commands to the robotic device cannot be modified. </th>
<tr> <td> AF-012 </td> <td> Attack Flow: Attacker modifies commands sent to the device through tampering with the data. 

`need to get confirmation from vendors, is remote link active typically for manufacturing access, updates, etc... ` </td> </tr>

<th colspan = 2> We want to protect the patient from harm, so we must ensure the abailability of supporting communication infrastructure</th>
<tr> <td> AF-013 <td> Attack Flow: Attacker disables / disrupts network connectivity within the operating environment. 

`e.g., access to router, etc to turn off, change settings, etc... `

`clinical impact: no telemetry, typically all in room, ask manufacturer, are commands sent to robotic system going over HDO network or through seperate manufacturer connection (eg.. cellular) `
</tr> </td>
<th colspan = 2> We want to ensure that if something goes wrong in the system, that the root cause can be traced and identified</th>
<tr> <td> AF-014 </td> <td> Attack Flow: Attacker modifies log files within a device </td> </tr>
<tr> <td> AF-015 </td> <td> Attack Flow: Attacker modfies log files within a CSP </td> </tr>

<th colspan = 2> We want to ensure that patient privacy is protected</th>
<tr> <td> AF-016 </td> <td> Attack Flow: Attacker gains unauthorized access to PHI data stored locally on robotic device hard drive or other local device. 
`verify with manufacturer, maybe on the hard drive, etc... ` </tr> </td>


<th colspan = 2> We want to ensure that the environment of the operation is maintained</th>
<tr> <td> AF-017 </td> <td> Attack Flow: Attacker is able to disrupt power to the room.  </tr> </td>
<tr> <td> AF-018 </td> <td> Attack Flow: Attacker modifies the HVAC settings in the operating room, disrupting temperature  </tr> </td>
<tr> <td> AF-019 </td> <td> Attack Flow: Attacker disrupts the medical air settings used within the operating room.  </tr> </td>
<tr> <td> AF-020 </td> <td> Attack Flow: Attacker disrupts the humidity settings within the operating room.  </tr> </td>
<tr> <td> AF-021 </td> <td> Attack Flow: Attacker disables water flow to the operating room. </tr> </td>


<th colspan = 2> We want to ensure that the attacker cannot prepare effectively for an attack against the robotic platform</th>
<tr> <td> AF-022 </td> <td> Attack Flow: Attacker is able to scan the components on the network.  </tr> </td>
<tr> <td> AF-023 </td> <td> Attack Flow: Attacker is able to stage malicious files within the hospital network.  </tr> </td>
<tr> <td> AF-024 </td> <td> Attack Flow: Attacker is able to perform a successful phishing attack on hospital personnel.  </tr> </td>

</table>



<h1> Contributors </h1> 

