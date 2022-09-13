<H1> Clinical Use Case </H1> 

Cloud connectivity may be provided through various methods, including 5G cellular. The scope of cloud computing support associated with any particular RAS may vary significantly. Some systems may implement substantial capability in the cloud, including 3D visualization, digital twin support, data fusion and analysis, etc. Other systems may limit cloud support and instead provide localized computing and networking capabilities (e.g,. networking cart).  The following diagram provides a view of the interactions between major components in a typical RAS. 

 
 <H2> Activity Diagram </H2> 
 
 ![image](https://user-images.githubusercontent.com/10893218/160676965-f49f338f-6d20-4afd-bfb8-2fa2b6115491.png)

 
 Standard Sequence: The basic flow of the best case scenario for this use case is:
 
1.       Operating environment cameras start recording
2.       Video data transmitted to cloud for monitoring
3.       Robotic platform initializes/starts
4.       Surgeon logs into the robotic operating environment
5.       Robotic platform begins transmitting telemetry data to cloud
6.       Robotic platform begins transmitting configuration data to cloud for continuous digital twin update
7.       Surgeon requests simulation support from technician/ cloud service (at some time prior to beginning operation)
8.       Patient arrives and is prepped
9.       Robotic platform begins collecting bio-sensor data 
10.      Surgeon commences operation using robotic platform
11.      Technician monitors video feeds
12.      Technician monitors 3D models for configuration anomalies
13.      Technician monitors telemetry feeds
14.      Operation concludes


Exception Flows: The following exception flows may arise during operation:

1.         Robotic arm fails to start properly
2.         Technician identifies anomalies in telemetry data
3.         Surgeon is unable to login to robotic operating device
4.         Cameras fail to transmit operating room video
5.         Robotic arm fails to operate properly
6.         Digital twin data fails to update properly

 

 
