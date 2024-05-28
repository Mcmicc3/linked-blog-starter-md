# Chapter 9

**Shared Responsibility**: Security is everyone's responsibility. Organizations have a responsibility to their stakeholders to make goodsecurity decisions. Everyone needs to understand their shared responsibility. 

There are technical mechanisms that can be impleneted to security a system, and each area, is layered into different rings to describe the different areas of a computer. **The four-layer protection ring model**:
- R0 - OS Kernel/Memory, R1 - Other OS Components, R2 - Drivers, Protocols , etc, R3 - User-level Programs and Applications
- Rings 0-2 Run in supervisory or privileged mode
- Rings 3 runs in user mode

Rings allow you to organize the layers of a computer, so you can identify which section of the ring requires privilege, and the more security you need to implement the deeper you go into the ring. 

The different states a process is in, known as **process states or operating states**. 
The different **operating modes**, a person is in, user mode vs privileged mode. 

**Understanding Memory** 
ROM (The different types of ROM), vs RAM (Real and Cache). 

The different registers (Memory addressing)
- Rgiester addresing, immediate addressing, direct addresing, indirect addressing, Base+Offset Addressing

**Seconday Memory**
- Virtual Memory, Pagefile/swapfile

**Data Storage files**
- Primay vs secondary
- Voltile vs nonvolatile
- Random vs Sequential
- Memory Security Issues
- Storage Media Security

**Emanation Security**
- Be aware of radio and wifi signals relaying sensitve information.  Be aware of interception. 
- Faraday cage, white noise, Control Zone

*Types of countermeasures and safeguards used to protect against emanation attacks are known as TEMPEST countermeasures*. 
- Monitors, Printers, Keyboard/Mice, Modems, 

##### **Client based systems**
mobile code

##### local caches
- DNS Cache, Arp Cache, 

#### Server based systems
- Data Flow control
- Symmetric multiprocessing vs asymettric multiprocessing vs massive parallel processing

**Grid computing**
- Form of parallel distributed processing

#### Peer to peer


## Industrial Control Systems

## Distributed Systems

## High-Performance Computing (HPC) systems

## IoT

## Edge of Fog Computing

## Embedded Devices and Cyber-Physical Systems

#### Static systems

#### Network Enabled Devices

#### Cyber-Physical Systems

#### Elements Related to Embedded and Static Systems

#### Security concerns of embedded and static systems

## Microservices

## Infrastructure as Code

## Virtualized Sytems

### Virtualized Networking

### Software-defined everything

### Virtualization Security Management

## Containerization

## Serverless Architecture

## Mobile Devices

#### Mobile Device Security Features

#### Mobile Deice Management

#### Device Authentication

#### Full-Device Encryption

#### Communication Protection

#### Remote Wiping
#### Device Lockout
#### Screen Locks
#### GPS and Location Services
#### Content Managment
#### Application Control
#### Push Notifications
#### Third-Part Application Stores
#### Storage Segmentation
#### Asset Tracking and Inventory Control
#### Removable Storage
#### Connection Methods
#### Disabling Unused Features
#### Rooting or Jailbreaking
#### Sideloading
#### Custom Firmware
#### Carrier Unlocking
#### Firmware Over-The-Air (OTA) Updates
#### Key Management
#### Credential Management
#### Text Messaging

byod vs cyod vs cope vs coms

mobile device deployment policy details
Data ownership
Support ownership
Patch and Update Management
Security Product Management
Forensics
Privacy
Onboarding/offboarding
Adherence to Corporate Policies
User acceptance, Architecture, infratstructure considerations
legal concerns
Acceptable use policy
Onboard camera/video
Recording Microphone
Wi-Fi direct
Tethering and Hotspots
Contactless Payment Methods
SIM Cloning
## Essential Security Protection mechanism
Process Isolation
Hardware Segementation
System Security Policy

## Common Security Architecture Flaws and Issues
Covert Channels
Attacks based on Design or Coding Flaws
Rootkits
Incremental Attacks


# Chapter 10
## Apply Security Principles to Site and Facility Design
Secure facility Plan
Site selection
Facility Design

## Implement Site and Facility Security Controls
1. Deter
2. Deny
3. Detect
4. Delay
5. Determine
6. Decide

Equipment Failure
Wiring Closets
Server Rooms/Data Centers
Smartcards and Badges
Proximity Devices
Intrustion Detection Systems
Motion Detectors
Intrusion Alarms
Secondary Verification Mechanisms
Cameras
Access Abuses
Media Storage Facilities
Evidence Storage
Restricted and Work Area Security
Utility Considerations
Power Considerations
Noise
Temperature, Humidity, and Static
Water Issues
Fire Prevention, Detection, and Suppression
Fire Extinguishers
Fire Detection Systems
Water Suppression Systems
Gas Discharge Systems
Damage
## Implement and Manage Physical Security
Perimeter Security Controls
Fences, Gates, Turnstiles, and Access Control Vestibules
Lighting
Security Guards and Guard Dogs
Internal Security Controls
Keys and Combination Locks
Environment and Life Safety
Regulatory Requirements
Key Perforamnce Indicators of Physical Security
