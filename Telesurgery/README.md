<h1> Introduction </h1>
Medical devices are becoming reliant on cloud services for machine learning, data storage, Electronic Health Record (EHR) integration, messaging, digital twins, and various other capabilities. Medical Device Manufacturers (MDMs) must design secure architectures and implement secure configurations of these cloud services in order to assure the confidentiality, integrity, and availability of patient data and the safety of patients. Failure to do so may result in degradation of service availability, tampering or manipulation of patient diagnosis or treatment plans, or compromise of protected health information (PHI).

There are many types of medical devices. Devices may be simple and purpose-built, or may be complex. One type of complex medical device is known as a Robotic Assisted Surgery (RAS) system. RAS (aka telesurgery) systems are increasingly becoming a preferred option for surgeons due to their ability to support tremor filtration, a higher degree of movement, and precise dissection ( Schreuder, 2009).  These systems allow local onsite or remotely located surgeons to perform their duties using precise robotic controls. Some RAS systems such as the hinotori RAS  are now being designed with cloud backends that provide various real-time services, including machine-learning, digital twins, analytics, and simulations (Medicaroid, 2020). 

This work provides recommendations to securely develop, deploy and operate cloud-connected RAS systems. Included are a repository of attack flows and associated recommendations for mitigation and detection of each attack. The end-result are recommendations that can be tailored to the unique implementation details of each HDO. 


The GitHub repository for this information can be found at: https://github.com/cloudsecurityalliance/IoT-Medical-Cloud

<h1> Scope </h1>
This document defines attack flows that may be used to compromise a cloud-connected RAS system. Due to the limited real-world data associated with compromise of RAS systems, these flows are assembled using both real-world and theoretical techniques. 


<h1> Methodology </h1>
Publicly-known attacks against hospital operations and medical devices have been documented and mapped to applicable attack flows. Since the technology in review is constantly evolving, theoretical attacks have also been included. When possible, the origin of the attack flow has been marked for each flow (e.g., realized vs theoretical). 

For purposes of this document realized is defined as an attack flow that is documented as being used by a threat actor in an attack against an HDO.  A theoretical attack flow is an attack flow that has not yet been documented as being used in an attack on an HDO, even if proof of concept exploits exist to support the flow. Design criteria for this project include:
Attack flows are focused not only on data protection and system availability, but also on patient-safety. Flows are modeled from the perspective of protecting the patient, assuring the confidentiality and integrity of patient data and maintaining hospital operations. 
 
Attack flows have been designed to be modular. Although many attack trees grow significantly, a modular approach makes it easier to manage the flows and supports mixing and matching to create multiple attack pathways. Modularity in this context is based on key decision points in an attack process (for example, once you've compromised a key, the attacker can move on to other attacks). Modularity is represented through the integration of multiple, modular files.

A set of modular attack flow files represents an attack use case. The attack use case is the higher level scenario that each associated attack flow may be run against. 
 
This project leverages the MITRE ATT&CK techniques (https://attack.mitre.org/) for Enterprise, Mobile and Industrial Control Systems (ICS). These attack techniques provide a basis for identification of the associated prevention and detection controls that are specified in this document. 
 
A set of prevention or detection controls can be combined to guard against a particular scenario, which comprises multiple attack flows. In this sense, these controls can be leveraged to develop an enterprise architecture that mitigates risks associated with RAS operations. 

<h1> System Description </h1>
A RAS / telesurgery is composed of two primary components: (1) a surgeon console, and (2) a Robotic Platform. These components may be co-located or may be geographically distributed. Sensors transmit telemetry data across the system. Telemetry data is used by the Surgeon, the robotic system, and by various others involved in the process to make clinical decisions and augment RAS command and control (C2). 

<h2> Surgeon Console </h2> 
The surgeon console requires reliable network communication. Command and Control (C2) data is transmitted from the surgeon console to the robotic platform. Device telemetry and patient bio-sensor data are received at the Surgeon Console and processed for display on the GUI. Consoles may in some cases also include an eye tracker to identify instances where the surgeon is not focused on the task at hand. This is a safety feature.  The surgeon console may also provide local augmented reality (AR) and virtual reality (VR) capabilities. These capabilities may also be augmented or replaced by a cloud service implementation. 

<h2> Robotic Platform </h2> 
The robotic platform may be encompassed within a larger set of components. The robotic platform includes the robotic arm(s) that perform the actions as commanded by the surgeon. The robotic arm transmits telemetry data to the surgeon console and to the cloud. Haptic feedback may be generated based on the positioning of the robotic platform and fed to the surgeon console. 

<h2> Bio-Sensors </h2> 
(Rashid, 2020) identifies various bio-sensor data that may be monitored in real-time by the surgeon and other medical professionals. This includes blood pressure, EMG, EEG and temperature.

<h2> Networking Components </h2> 
Networking components are used to connect the surgeon console and the robotic platform, as well as to provide connectivity to cloud services. Connectivity between the surgeon console and the robotic platform may be through wired Ethernet. Connectivity with the cloud SaaS service may be through a 5G cellular link that provides the bandwidth and low latency required for this use case.

<h2> Cloud Services </h2> 
The cloud service may provide numerous capabilities. Actual services offered will be dependent on the vendor and each unique product offering. Examples of services that may be offered in the cloud include:

●        Telemetry data storage and monitoring
●        Bio-health data storage and monitoring
●        Digital twin configuration of the robotic platform
●        3D Visualization of the robotic platform
●        Machine Learning support
●        Simulation Services
●        Remote Management

(Rashid, 2020) Telemetry data transmitted from the robotic arm to the cloud may include operating speed, velocity and force of the robotic arms. Bio-health data may include temperature, blood pressure, EEG, heat rate, respiration rate, EMG, and EEG. Digital twin configuration data may include the positioning of the robotic arm(s). This may include angular and linear positions that can inform the 3D visualization capability.

<h2> Electronic Health Record </h2> 
The Electronic Health Record (EHR) may be linked to the telesurgery event. This connection may be through multiple mechanisms, including a link between the EHR vendor cloud and the robotic SaaS service. 

