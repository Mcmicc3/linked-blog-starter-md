# Terms, Concepts, and Technologies

~ Centralized model
		- Centralized is an architecture model that involves using a single point of control or authority to manage a system or service. 
		- Centralized systems or services can have advantages such as simplicity, consistency, and security, but also disadvantages such as single point of failure, scalability issues, and lack of autonomy.
~ Decentralized Model
		- Decentralized is an architecture model that involves using multiple distributed points of control or authority to manage a system or service. 
		- Decentralized systems or services can have advantages such as resilience, scalability, and autonomy, but also disadvantages such as complexity, inconsistency, and security challenges.
~ On-Premises model
		- On-premises is an architecture model that involves hosting and managing infrastructure on the organization’s own premises. 
		- It can be centralized *or* decentralized.
~ Regulated data
		- Regulated data implies that it's a category of data that adheres to specific compliance standards due to its sensitive nature.
~ Rule-based access control
		- "Rule-based access control" is a broad term that can encompass various access control mechanisms.
~ Gap Analysis
		- A gap analysis identifies the differences between the current state of a system or process and its desired future state, providing a roadmap for achieving those desired outcomes.
~ Threat scope reduction
		- Threat scope reduction refers to the proactive steps and strategies taken to reduce the potential areas of attack within a system or network. 
		- By limiting the avenues that attackers can exploit, organizations can more effectively secure their assets.
~ Recurring Report
		- A recurring report is a report generated at regular intervals, such as weekly, monthly, or quarterly, to keep stakeholders updated on ongoing security metrics, trends, and concerns.
~ Policy Review
		- A policy review is a periodic assessment of the organization's security policies to ensure they remain current and effective.
~ Threat Intelligence Briefing
		- A threat intelligence briefing is a specialized report highlighting current and emerging threats, often sourced from external threat intelligence providers.
~ Incident Report
		- An incident report is a detailed account of a specific security breach or event, outlining what occurred, its impact, and the steps taken in response.
~ Directive Control
		- Directive controls guide actions and ensure consistent behavior or actions within an organization.
~ Synchronized backups
		- Synchronized backups refer to the continuous updating of backup copies as changes occur in real-time, but the location isn't necessarily offsite.
~ Serverless Architecture
		- Serverless architecture is a cloud-computing model focusing on applications’ runtime
~ Responsibility Matrix
		- A responsibility matrix in cloud architecture is crucial for clearly defining the roles and responsibilities between the client and the cloud service provider, ensuring accountability and security compliance.
~ Horizontal Password Attack
		- In a horizontal password attack, an attacker targets multiple accounts by trying a few common passwords across them.
		- It's a method to bypass account lockout policies that would trigger if too many failed attempts are made on a single account.
~ Vertical password attack
		- A vertical password attack involves targeting a single user account and trying a large number of password combinations until the correct one is found.
		- Brute force??
~ Credential Stuffing
		- In a credential stuffing attack, an adversary uses previously stolen username-password pairs to gain unauthorized access.
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
~ Dynamic Analysis (Dynamic Code Analysis)
		- Dynamic analysis evaluates software during its runtime, aiming to uncover vulnerabilities that might not be visible in a static state.
~ MITRE ATT&CK Framework
~ Diamond Model of Intrusion Analysis
~ Normalization
~ acquisition

~ VM Sprawl
		- Occurs when an organization has many VMs that aren't appropriately managed.
		- Someone makes a test VM. The admin orchestrates a software patch for all the VMs, but because he's unaware of this one, it doesn't get updated, leaving it vulnerable for an attack. 
~ Resource Reuse
		- In the context of cloud computing risks refers to the potential for data or resources to remain on a shared infrastructure even after a customer has finished using them, making them potentially accessible to other users of the cloud service.
		- Leads to risk of data leakage, as well as unauthorized access to sensitive data or systems. 
~ Agent NAC
		- Agents on clients can be either *permanent* or *dissolvable*. A permanent agent (sometimes called a *persistent NAC agent*) is installed on the client and stays on the client. NAC uses the agent when the client attempts to log on remotely
		- A dissolvable agent is downloaded and runs on the client when the client logs on remotely. It collects the information it needs, identifies the client as healthy or not, and reports the status back to the NAC system. Others remove themselves after the remote session ends.
~ Agentless NAC
		- Scans a client remotely without installing code on the client, either permanently or temporarily,. This is similar to how vulnerability scanners scan network systems looking for vulnerabilities.
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
		- Used to protect against BPDU-related attacks
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
~ Attestation
		- Formal process for reviewing user permissions. 
		- Managers formally review each user's permissions and certify that those permissions are necessary to carry out the user's job responsibilities
~ Measured Boot
		- Form of boot integrity. 
		- Goes through enough of the boot process to perform these checks without allowing a user to interact with the system. If it detects that the system has lost integrity and can no longer be trusted, the system won't boot. 
~ TPM
		- Hardware chip *embedded* on the *computer's motherboard* that stores cryptographic keys used for encryption. Most Desktop and laptop computers include a TPM
		- Once enabled, the TPM provides full disk encryption capabilities. 
		- It keep shard drives encrypted and protected until the system completes a system verification and authentication process
		- Has an endorsement key, which is a unique asymmetric key pair burned into the TPM chip that provides a hardware root of trust. 
~ Secure Boot Attestation
		- A process that is supported by TPM
		- When the TPM is configured, it captures signatures of key files used to boto the computer and stores a report of the signatures securely within the TPM. 
		- When the system boots, the *Secure boot* process checks the files against the stored signatures to ensure they haven't changed. 
		- If it detects that the files have been modified, such as from malware, it blocks the boot process to protect the date on the drive. 
~ HSM (*Hardware security module*)
		- Security device you can add to a system to manage, generate, and securely store cryptographic keys. 
		- High-performance HSMs are externel network appliances using a TCP/IP network connection. Smaller HSMs come as expansion cards you install within a server or as devices you plug into computer ports
		- Difference between TPM is that HSMs are *removeable* or *external devices*. 
		- Both HSM and TPM provide secure encryption capabilities by storing and using encryption keys. 
~ microSD HSM
		- microSD card that includes an HSM. 
		- Supports cryptographic operations like encryption, decryption, digital signatures, generates hashes.
		- 
~ Remote Attestation
		- Form of Boot integrity through TPM
		- A process that works like the secure boot process. However, instead of checking the boot files against the report stored in the TPM, it uses a separate system. Again, when the TPM is configured, it *captures* the *signatures of key files*, but *sends this report to a remote system*.
		- When the system boots, it checks the files and sends a current report to the remote system. The remote system verifies the files are the same and attests, or confirms, that the system is safe. 
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
~ Wireless Footprinting
		- Creates a detailed diagram of wireless access points and hotspots within an organization. 
		- Typically displays a heat map and dead spots if they exist
~ Wi-Fi Analyzers
		- Provide a graph showing channel overlaps but not a diagram of wireless access points
~ Air gapping 
		- Network of devices that are separated from the internet and LANs. No physical or wireless connection to other networks
		- An air-gapped network is a network that is physically isolated from other networks and the internet. This provides a high level of security, but also limits the functionality and connectivity of the network.
~ Race condition 
		- 
# Acronyms

~ DKIM
		- implementing DKIM (DomainKeys Identified Mail), allows companies to sign emails originating from their domain cryptographically.
		- This allows receivers to verify that an email claiming to be from the domain genuinely is.
~ SPF
		- SPF (Sender Policy Framework) is valuable in identifying which servers are authorized to send emails on behalf of a domain, it doesn't cryptographically sign the emails for this assurance.
~ DMARC
		- DMARC (Domain-based Message Authentication, Reporting, and Conformance) uses the results of DKIM and SPF checks, but on its own, it doesn't cryptographically sign emails.
~ DRP
~ ISA
~ SDN
		- Software-defined networking (SDN) is a paradigm that decouples the control plane from the data plane in a network, allowing for centralized and dynamic management of network resources and policies. 
		- This provides greater flexibility, efficiency, and automation of the network.
~ IPsec
		- Method of encrypting data in transit
		- Supports both Tunnel mode and Transport mode
		- IPsec provides security in two ways, *Authentication* and *encryption*
			- IPsec includes an Authentication Header (AH) to allow each of the IPsec conversations hosts to authenticate with each other before exchanging data
~ Tunnel mode (IPsec)
		- Encrypts the entire IP packet, including both the payload and the packet headers
		- VPNs commonly use Tunnel mode
		- **Benefit**: IP addressing used within the **internal network is encrypted** and not visible to anyone who intercepts the traffic
~ Transport mode (IPsec)
		- Only encrypts the payload and is **commonly used in private networks**, but **not with VPNs**.
~ Full tunnel VPN
		- All traffic goes through the encrypted tunnel while the user is connected to the VPN. 
		- Disadvantage is that it's slow
~ Split tunnel VPN
		- An administrator decides what traffic should use the encrypted VPN tunnel. 
		- Possible to configure the tunnel to encrypt only the traffic going to the private IP address used within the private network.
~ Site-to-site VPN
		- Includes two VPN servers that act as gateways for two networks separated geographically. 
		- Example: One VPN is on the headquarters, and the other is a remote site
		- Transparent to end users, they're unaware of it
~ Always-On VPN
		- Can be used with site-to-site VPNs and direct access VPNs
		- On mobile, if a user connects to free internet access at a coffee shop, the device will automatically connect to the always-on VPN
~ L2TP as a Tunneling Protocol
		- Also used for VPNs. 
		- Doesn't provide encryption, usually used with IPsec, then passed to L2TP for transport
~ PAP
		- Used for authentication, *No longer supported*
		- Used with dial-up connections
~ CHAP
		- Uses Point-to-Point (PPP) for authentication but more secure
		- Goal is to allow the client to pass credentials over a public network without allowing attackers to intercept the data and later use it in an attack
		- Client and server both know a shared secret
~ TACACS+ 
		- Alternative to RADIUS, and provides two essential security benefits
		- First, it encrypts the entire authentication process, whereas RADIUS encrypts the password only (by default)
		- Second, TACACS+ uses multiple challenges and responses between the client and the server
		- **Cisco** created TACACS+, and it can interact with Kerberos, allowing a VPN concentrator to interact in a Active Directory environment. *Reminder, AD uses Kerberos for authentication* 
~ RADIUS
		- Centralized authentication server. All requests for every sensitive resources gets authenticated by the RADIUS server
		- Can be used as an 802.1x server with WPA2 & WPA3 Enterprise mode. 
		- Can be used with EAP to encrypt entire sessions
~ VPC endpoint?
~ VPC - Virtual Private Cloud    (VPC Endpoint, peering, gateway transit Internet gateway)
~ SED - Self encrypting drive 
~ PBKDF2 - key stretching
~ COOP - Continuity of Operations
~ IoC - Indicators of Compromise
~ MOA  (*Memorandum of Agreement*)
		- The Memorandum of Understanding (MOU) outlines the terms of a partnership between two organizations and how they will collaborate on specific projects or initiatives.
		- While it may establish the overall collaboration, it does not include service levels and performance metrics.
		- Not legally binding
~ ISA - Interconnection Security Agreement
~ MSA - Measurement System Analysis
~ MSA (*Master Service Agreement*)
		- The Master Service Agreement is a comprehensive document that establishes the overall framework for a long-term business relationship between a company and a vendor 
		- It outlines the general terms and conditions, but it does not specifically detail the service levels and performance metrics.
~ SOW (*State of Work*) or WO (*Work Order*)
		- The Work Order (WO) or Statement of Work (SOW) is a document that provides detailed instructions and requirements for specific tasks or projects to be carried out by the vendor. It may include information on deliverables, timelines, and costs, but it **does not** focus on service levels and performance metrics.
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
~ DLP (*Data Loss Prevention*)
		- Techniques and technologies used to prevent data exfiltration
		- They can block USB flash drives and control the sue of removable media. They can also examine outgoing data and detect many types of unauthorized data transfers
		- In network-based DLP, all traffic leaving the network is directed through an appliance that can examine the traffic by searching for specific key words, phrases, or character strings. 
		- Software based DLP is installed on individual systems, identifying data exfiltration attempts and blocking them from succeeding. 
		- It can sniff through email attachements, zip folders, emails
~ EDR (*Endpoint Detection and Response*)
		- Endpoint Security Software technology that focuses on detecting and responding to threats at the endpoint level, often using advanced behavioral analysis techniques to identify suspicious activity and contain threats before they can cause damage
~ XDR (*Extended Detection and Response*) 
		- Is a next-generation security technology that goes beyond the endpoint to include other types of devices and systems, such as network devices, cloud infrastructure, and IoT devices, providing a more comprehensive view of the entire IT environment and enabling faster threat detection and response. 
		- The main significance of implementing XDR in the given scenario is its ability to integrate and correlate security data from various sources, such as endpoints, network, and cloud environments. 
		- By doing so, XDR can detect and respond to sophisticated, multi-vector cyber threats more effectively, which aligns with XYZ Corp's goal to address the increase in sophisticated cyberattacks. While XDR may contribute to enforcing security policies, its **primary role** is to detect and respond to multi-vector cyber threats across the IT environment.
		- XDR's primary purpose is to enhance threat detection and response capabilities.
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
		- Used to authenticate inside Active Directory environments
~ CASB
~ OAuth
		- Open standard
		- Provides secure access to protected resources
		- Downloading an app, and it requests access to your google calendar, We are giving this application authorization, without giving it our password, or anything else.
		- Auth in this case stands for *Authorization*, not authentication!
~ ESP

~ WAF
~ DNSSEC
~ L2TP
~ AUP
~ CYOD (*Choose your own device*)
~ Embedded RTOS
~ Shadow IT
~ Authorized Hacker
~ Criminal Syndicate

~ Pointer/object dereference
~ Dynamic code analysis
~ Normalization
~ Risk Register
~ SOAR
~ SLE (*Single loss expextancy*) 
		- Cost of loss per occurrence
~ ARO (*Anual Rate of Occurance*)
~ ALE (*Annual Loss Expectancy*)
~ Credentialed scan 
		- Vulnerability scan that includes credentials
~ Non Credentialed scan 
		- Vulnerability scan that doesn't include credentials
~ MTBF (*Mean Time Before Failure*)
		-  Average time things that can't be repaired break, like HDDs or routers
~ RTO
~ RPO
~ Rainbow table
~ Password Spraying (Spraying Attack)
		- A spraying attack is a type of password attack that involves trying common passwords against multiple accounts, hoping to find a match.
~ TOU (*Time of Use*)
		- A Time-of-use (TOU) vulnerability arises when there's an opportunity for an attacker to manipulate a resource after its creation but before its use by an application
		- An application creates a temporary file with stored data in it to be used later, but an attacker deletes it, or manipulates it before the application can use that file
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

What is the significance of SNMP?
1. SNMP's main main purpose is the managing and monitoring network devices.
2.  It provides capabilities to handle network performance, control network configurations, and store data related to various network components.
3. It allows network administrators to monitor performance, troubleshoot issues, as well as plan for future network growth
4. SNMP does aid in collecting data from different network devices to maintain proper functionality and security

How do you calculate the ALE?
- The ALE is calculated by multiplying the SLE by the ARO

What is the difference between an amplified attack, and a reflected attack
1. An amplified attack is a type of DDoS attack that involves sending requests with spoofed source IP addresses to servers that generate large responses, amplifying the traffic sent to the target server. 
2. A reflected attack is a type of distributed denial-of-service (DDoS) attack that involves sending requests with spoofed source IP addresses to servers that redirect the responses to the target server, reflecting the traffic back to it.

In digital forensics, What is MOST crucial to consider when determining the requirements for an investigative report?
- Understanding the audience, whether it's legal professionals, executives, or technical teams, determines the report's depth, language, and emphasis.
## Secure ports
FTPS: port 990
SRTP: port 5004
SFTP: port 22 (just like SSH)
LDAPS: 636
LDAP: 389
587

## General






