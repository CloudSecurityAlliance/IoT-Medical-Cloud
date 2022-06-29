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
- Attack Flow: Attacker performs attack on cloud service provider (CSP) that renders services unavailable. 
-        
- Attack Flow: Attacker performs attack on cloud provider resulting in a lack of AI capability (results in further delay to care). 

**We want to protect the patient from harm, so we must ensure that a remote clinician has an accurate view of patient status.**
- Attack Flow: Attacker modifies bio-sensor readings through tampering with biosensor data. 
- Attack Flow: Attacker modifies notification messages meant for the clinician through tampering with data. 

**We want to protect the patient from harm, so we must ensure that remote commands to the robotic device cannot be modified.**
- Attack Flow: Attacker modifies commands sent to the device through tampering with the data. 

**We want to protect the patient from harm, so we must ensure the abailability of supporting communication infrastructure**
- Attack Flow: Attacker disables wireless connectivity within the operating environment. 

**We want to ensure that if something goes wrong in the system, that the root cause can be traced and identified**
- Attack Flow: Attacker modifies log files within a device
- Attack Flow: Attacker modfies log files within a CSP

**We want to ensure that patient privacy is protected**
- Attack Flow: Attacker gains unauthorized access to PHI data


**Add another category for setup of attacks; staging of malicious files, etc... phishing, ... **












Ransomware attacks
- define clinical impacts

Telemetry monitoring issues impacts nursing 




