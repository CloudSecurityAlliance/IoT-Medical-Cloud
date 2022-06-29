**We want to protect the patient from harm, so we must guard against misconfigurations / firmware tampering, etc in the robotic device.**
- Attack Flow: Attacker tricks authorized personnel to uploads malicious firmware to robotic device due to failure to authenticate firmware upload.  
-       //real-world...  biomed firmware mfg rep coming in to service the device; infected copy of firmware used to restore device to service.  
- Attack Flow: Attacker modifies robotic device firmware through compromise of the vendor software update process (note: potential multi-patient effect). 
-       automated software update on the device is not configured properly... 
- Attack Flow: Attacker modifies robotic device configuration file through compromise of a management system on the network... (differntiate from next one)... 
-       most devices have mgmt console; any way to compromise the mgmt console will work/ phishing, etc... 
- Attack Flow: Attacker modifies device configuration settings through physical access to the device. 
-        phyiscally in the room, with access to front panel of device... 
- Attack Flow: Attacker infects robotic device with virus/malicious code through cloned hard-drive, other means. 
-        changing a part in the system, that has a software/firmware component, results in compromise... real-world; compromised medical supply chain... Chris to look up... 

**We want to protect the patient from harm, so we must ensure the availabiity of the supporting cloud services. **(e.g. can't perform radiation verification because csp was attacked). 
- Attack Flow: Attacker performs a denial of service through a network flood. 
-       device telemetry, biohealth data, target the egress circuit, or the cloud endpoints
- Attack Flow: Attacker encrypts critical file on the device through ransomware. 
-        file to boot device, configuration file, various files could be targeted... 
- Attack Flow: Attacker performs attack on cloud service provider (CSP) that renders biohealth data unavailable. 
-      attack on the collection of biohealth data in the cloud, or the analysis from that data back to system... 
-      note: scope is restricted to device operations... add this to introduction... 
- Attack Flow: Attacker performs attack on cloud provider resulting in a lack of AI capability (results in further delay to care). 
-      note: scope is restricted to device operations... add this to introduction... 

**We want to protect the patient from harm, so we must ensure that a remote clinician has an accurate view of patient status.**
- Attack Flow: Attacker modifies bio-sensor readings through tampering with biosensor data, or devices
- --- most surgeries have nurse to monitor vitals; if vitals change, change course of surgery by notifying doctor; halt surgery, take medical action, etc... 
- Attack Flow: Attacker modifies notification messages meant for the clinician through tampering with data. 
- ----- hold on this one, get feedback first... 

**We want to protect the patient from harm, so we must ensure that remote commands to the robotic device cannot be modified.**
- Attack Flow: Attacker modifies commands sent to the device through tampering with the data. 
- need to get confirmation from vendors, is remote link active typically for manufacturing access, updates, etc... ... 

**We want to protect the patient from harm, so we must ensure the abailability of supporting communication infrastructure**
- Attack Flow: Attacker disables / disrupts network connectivity within the operating environment.
- --- e.g., access to router, etc to turn off, change settings, etc... 
- --- clinical impact: no telemetry, typically all in room, ask manufacturer, are commands sent to robotic system going over HDO network or through seperate manufacturer connection (eg.. cellular)  

**We want to ensure that if something goes wrong in the system, that the root cause can be traced and identified**
- Attack Flow: Attacker modifies log files within a device
- Attack Flow: Attacker modfies log files within a CSP

**We want to ensure that patient privacy is protected**
- Attack Flow: Attacker gains unauthorized access to PHI data
- -perhaps local data (PHI) for performance issues; 
- --- verify with manufacturer, maybe on the hard drive, etc... 

Add: Loss of power to the device... 
- reliance of industrial control system support
- --- Attacker modifies hvac settings in operating room
- --- other OT devices as well... 
- --- medical air (needed for some devices in operating room; used to mix gasses
- ---humidity 
- ---pressure sensors to keep positive/negative airflow to room
- ---water needed to run 
- ---temp regulation  
- 



Add to introduction: scope anything that would disrupt the operation would be in scope... 
Add to introduction: our methodology - public vs theoretical attacks.... 

wherever we can cite a public attack is best; 


**Add another category for setup of attacks; staging of malicious files, etc... phishing, ... **












Ransomware attacks
- define clinical impacts

Telemetry monitoring issues impacts nursing 




