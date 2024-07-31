# Terms, Concepts, and Technologies

~ IRP Life cycle
~ IRP Process
~ Known Environment
~ Unknown Environment
~ Partially Known Environment
~ Cyber Kill Chain
~ Pharming
~ smishing
~ Vishing
~ Pretexting
~ Static Code Analysis
~ Risk Register
~ Dynamic Code Analysis
~ MITRE ATT&CK Framework
~ Diamond Model of Intrusion Analysis
~ Normalization
~ acquisition
~ VPN concentrator
		- Dedicated device used for VPNs, popular with Larger organizations
		- Includes all the services needed to create a VPN, including strong encryption and authentication techniques, and it supports many clients
		- Typically placed in a screened subnet
		- The firewall between the internet and the screened subnet would forward VPN traffic to the VPN concentrator
~ IEEE 802.1x
		- Port-based authentication protocol.
		- Requires users or devices to authenticate when they connect to a specific WAP or physical port
		- Works for both physical, VPN connections and wireless networks
~ Heuristic-based
		- Also known as *Anomaly based*, or trend based.
		- Identifies issues by comparing it against a baseline
~ Policy enforcement point
		- 
~ Policy administrator
		- The policy administrator exists in the control plane, and it sends decisions to the policy enforcement point (PEP). 
~ BPDU Guard
~ Key escrow
~ Integrity Measurements
~ IV Attack
		- IV is a number used by encryption systems
		- A wireless IV attack attempts to discover the pre-shared key after first discovering the IV
		- Some encryption systems reuse the same IV, making it easier to discover.
		- Attackers use packet injection techniques. AP responds with more packets, increasing the probability that it will reuse a key. 
~ Bluesnarfing
		- Refers to the unauthorized access to, or theft of information from, a bluetooth device. 
		- Attack can access information, such as email, contact lists, calendars, and text messages
~ Bluejacking
		- Practice of sending unsolicited messages to nearby bluetooth devices. 
		- Messages are typically text but can also be images or sounds
		- Relatively harmless but does cause some confusion when users start receiving messages. 
~ Bluebugging
		- Similar to bluesnarfing
		- In addition to gaining full access, the attacker installs a backdoor
		- Attackers can also listen to phone calls, enable call forwarding, send messages, and more
~ Full tunnel VPN
~ Split tunnel VPN
~ Site-to-site VPN
~ Attestation
		- Formal process for reviewing user permissions. 
		- Managers formally review each user's permissions and certify that those permissions are necessary to carry out the user's job responsibilities
~ Remote Attestation
~ HoneyToken
		- Fake record inserted into a database to detect data theft
		- If you receive a message from an intentionally fake account that's never meant to be used, you know that your data was stolen
~WPA2
		- Supports PSK
~SAE Mode (WPA3)
		- Supports SAE
		- SAE uses a passphrase but adds strong security defenses to the technology
		- Replaces PSK mode of WPA2
~ Enhanced Open mode (WPA3)
		- Replaces the insecure and unencrypted open mode of WPA2 with technology that uses strong encryption to protect the communications of unauthenticated users. 
		- *Allows you to easily run a secure guest network*
~ Enterprise mode  (WPA3)
		- Just like enterprise mode in WPA2, uses a RADIUS server to authenticate a user
~ Active/active
~ Active/Passive
~ Persistence


# Acronyms

~ DRP
~ ISA
~ Air gapping - Network of devices that are separated from the internet and LANs. No physical or wireless connection to other networks
~ IPsec
~ VPC endpoint?
~ VPC - Virtual Private Cloud    (VPC Endpoint, peering, gateway transit Internet gateway)
~ SED - Self encrypting drive 
~ PBKDF2 - key stretching
~ COOP - Continuity of Operations
~ IoC - Indicators of Compromise
~ MOA - Memorandum of Agreement
~ ISA - Interconnection Security Agreement
~ MSA - Measurement System Analysis
~ DPO - Ensure data privacy regulation compliance
~ Custodian/steward - responsible for managing data in alignment with data owner **big distinction between the data owner and the custodian**
~ Data Processor - Handles data in accordance with privacy guidelines
~ Data Controller - Ensures data complies with applicable regulations
~ PHI (Protected Health Information)
~ RPO
~ RTO
~ MTBF
~ MTTF
~ MTTR

~ auth.log
~ aggregating
~ syslog
~ NetFlow
~ sFlow
~ OpenID Connect
~ privileged access management
~ SELinux
		- MAC (access control) built into the linux operating system
		- When you think about it, Windows is build with DAC
		- Has three modes: Enforcing mode, Permissive mode, Disabled mode. 
~ SAML (*Security Assertion Markup Language*)
		- Used for SSO
		-  XML based data format used for SSO on web browsers. 
		- Ex: Two websites host by two different organizations, the organizations trust each other, and use SAML as a federated identity management system. 
		- Authenticate with one website and don't have to authenticate with the other. (Google, Facebook)
~ Kerberos
~ CASB
~ OAuth
		- Open standard
		- Provides secure access to protected resources
		- Downloading an app, and it requests access to your google calendar, We are giving this application authorization, without giving it our password, or anything else.
		- Auth in this case stands for *Authorization*, not authentication!
~ ESP
~ TPM
~ HSM (*Hardware security module*)
		- SD card used for smart phones
		- Supports cryptographic operations like encyption, decryption, digital signatures, generates hashes, 
~ WAF
~ DNSSEC
~ L2TP
~ AUP
~ IPsec using Tunnel mode and transport mode
~ CYOD (*Choose your own device*)
~ Embedded RTOS
~ Shadow IT
~ Authorized Hacker
~ Criminal Syndicate
~ Race condition exploit
~ Pointer/object dereference
~ Dynamic code analysis
~ Normalization
~ Risk Register
~ SOAR
~ SLE  
		- *Single loss expextancy. Cost of loss per occurrence*
~ ARO
~ ALE
~ Credentialed scan 
		- *Vulnerability scan that includes credentials*
~ Non Credentialed scan 
		- *Vulnerability scan that doesn't include credentials*
~ MTBF 
		- *Mean Time Before Failure. Average time things that can't be repaired break, like HDDs or routers*
~ RTO
~ RPO
~ Rainbow table
~ Password Spraying
~ CRL
~ OCSP
~ CSR
~ DSA
~ TAXII
~ STIX
~ tcpreplay
~ Cuckoo
~ Pseudo-anonymization
~ Tokenization
~ Data Minimization
~ Anonymization
~ SED
~ 
~ MDM
~ SSL
		- SSL is deprecated and shouldn't be used
		- Replaced with TLS
~ VDI
~ MAM
~ COPE
	- Corporate owned personally enabled
	- partitions for remote wipe
~ HOTP
~ FRR  (*False Rejection Rate*)
~ FAR (*False Acceptance Rate*)
		- Both the FRR and FAR do not measure accuracy
~ CER  (*Crossover Error Rate*)
		- Low CER means more accurate
~OpenID Connect
~ RADIUS
		-
~SCAP
~CVSS
~ TPM (*Trusted platform module*)
		- Provides disk encryption
~ Generic account (*Shared account*)
~ Service account
		- An account used by a service or application, *not a person*. 
~ MAC (*Mandatory Access Control*)
		- Uses labels and a lattice to grant access
		- Based on secret privileges (Secret, confidential, etc), not job role
~ PAM (*Privileged Access Management*)
		- Controls over administrator and root accounts
		- Implements *Just-in-time permissions*. Privilege isn't granted unless needed. 
		- Their accounts send a request that needs to be granted for privileges. 
		- PAM temporarily adds the requester to a group with elevated privileges. 
		- Only PAM has access to the passwords. 
~ LDAP 
		- Core component of SSO
		- Allows users and applications to **retrieve information** about users from the organization's directory = a centralized repository of information about **user accounts, devices, and other objects**
		- **Handles queries** for Active Directory 
~ Federation
		- Supports SSO for users in different environments/separate networks
		- With my credentials in this company, I can access files from another without signing in again. 
		- *Requires* a federated identity management system that all members use. 
~ SRTP
~ STP (*Spanning Tree Protocol*)
~ EAP (*Extensible Authentication Protocol*)
		- Wireless authentication protocol
		- Method for two systems to create a secure encryption key, also known as PMK
		- Systems then use PTK to encrypt all data transmitted between the devices
		- Commonly implemented with AES
~ PEAP (*Protected EAP*)
		- Wireless authentication protocol that provides an extra layer of security
		- PEAP protects the communication channel by encapsulating and encrypting the EAP conversation in  TLS tunnel. 
		- Requires a certificate *on the server, but not the client*. 
		- Commonly implemented with MS-CHAPv2
~ EAP-FAST
		- Cisco designed EAP authentication via Secure Tunneling
		- Supports PAC instead of certificates
~ EAP-TLS
		- Secure EAP Standard, similar to PEAP
		- Main difference is that EAP-TLS *requires certificates on the 802.1x server and the clients*
~ EAP-TTLS
		- EAP Tunneled TLS is an extension of TLS
		- Supports older systems to run older authentication methods like PAP, within a TLS tunnel
		- *Requires a certificate on the 802.1x server but not the clients*

## Questions
Which three pieces of information are needed for WPA2-Enterprise mode?
1. IP of RADIUS Server
2. Port of RADIUS Server
3. Shared Secret

What are the three modes of WPA3?
1. Enhanced open mode
2. SAE mode
3. Enterprise mode
## Secure ports
FTPS: port 990
SRTP: port 5004
SFTP: port 22 (just like SSH)
LDAPS: 636
LDAP: 389
587

## General







