An RAS must also be setup and managed. Operational management processes can be targeted by attackers to attempt compromise of the system. These processes include the initial onboarding of the device into the system as well as the calibration and configuration of the device. The backend cloud system must also be configured. Identities must be provisioned and billing /entitlements are setup. Vendor representatives may play a significant role in this process. 

<h2> Activity Diagram </h2> 

![admin Use Case](https://user-images.githubusercontent.com/10893218/189974766-5155ce81-7b11-442d-9e6b-61f908c74a74.png)

Standard Sequence: The basic flow of the best-case scenario for this use case is:

1.       Robotic device is physically installed in operating environment
2.       Robotic device is turned on for first time
3.       Configuration menu allows device to associate with cloud services, etc
4.       Technician logs into cloud service to begin configuration
5.       Technician begins onboarding process to generate appropriate credentials, keys, etc
6.       Technician configures endpoints for transmission of telemetry data and configuration data (APIs)
7.       Digital twin established for device in cloud
8.       Billing /Entitlements setup/configured in cloud
9.       Video cameras in operating environment configured.
10.      Robotic devise is configured and ready to operate


Exception Flows: The following exception flows may arise during operation:

·         Configuration Error
