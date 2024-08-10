# Terms, Concepts, and Technologies

~ Policy-driven access control
		- Policy-driven access control is an approach where permissions are set based on organizational policies, roles, or requirements, ensuring that users have the right level of access that aligns with their job functions or responsibilities. 
		- Permissions are assigned based on predefined roles in an organization, and individuals are then assigned to those roles. 
		- Users are given the minimum levels of access necessary to perform their job functions. If a condition is not explicitly met, access is denied by default.
~ Unique Secret Keys
		- Unique secret keys for programmatic access are crucial for ensuring that interactions with the cloud are secure and authenticated.
~ Infrastructure Monitoring
		- Infrastructure monitoring is focused on ensuring the foundational IT components, like servers, data centers, and networking equipment, are both functional and secure.
~ Systems Monitoring
		- Systems monitoring evaluates the hardware, operating systems, and the essential services that applications run on
~ Application Monitoring
		- Applications monitoring pertains to overseeing individual software solutions and ensuring their security and performance.
~ Passive Mode
		- In passive mode, the firewall monitors traffic without actively blocking or allowing it. 
		- This can be useful for observing traffic patterns but wouldn't be ideal for a mission-critical system where active protection is essential.
~ Fail-Open
		- A fail-open mode would allow all access requests during a malfunction. 
		- In a high-security environment, this could lead to unauthorized access to sensitive data.
~ Fail-closed
		- When security is paramount, as with sensitive data storage, a fail-closed mode ensures that all access requests are denied during system malfunctions, preventing any potential unauthorized access.
		- This method involves limiting traffic based on a predefined rate.
~ Technical Debt
		- Technical debt represents the future cost of rectifying present-day shortcuts or less optimal solutions. 
		- It can arise when known inefficiencies aren't addressed due to various constraints, like time.
~ Salting
		- Salting is a technique used in cryptography to add random data to the input of a hash function to increase security.
		- The *key difference between key stretching and regular hashing or salting* is the number of times the hashing is done. Hashing is the process of converting an input of any length into a fixed size string of text, using a mathematical function. Hashing doesn't add data to the input before completing the conversion.
~ Key Stretching
		- Key stretching is a method used that repeatedly hashing the password to make it more random and longer than it originally appeared.  This should make the key more time consuming to break.
		- The **key difference between key stretching and regular hashing or salting** is the number of times the hashing is done. Hashing is the process of converting an input of any length into a fixed size string of text, using a mathematical function. Hashing doesn't add data to the input before completing the conversion.
~ Integrated Penetration Testing
		- Integrated penetration testing refers to a comprehensive approach that combines different types of penetration tests to assess an organization's overall security posture.
~ Screen-locking ransomeware
		- This type of ransomware intimidates users by locking them out of their device and displaying threatening messages.
~ Crypto-malware ransomware
		- Crypto-malware encrypts a user's files and holds them for ransom.
~ Virtualization Detection
		- Virtualization detection refers to methods used by malware or attackers to detect if they are operating within a virtual environment, often to alter their behavior accordingly.
~ Security Zones
		- Security zones are used to segment a network into smaller, more manageable areas
~ Adaptive Identity
		- Adaptive identity allows for more flexible and dynamic access control by using contextual data to make dynamic access control decisions. 
		- For example, the system might grant access to a sensitive resource based on the user’s location or the time of day.
~ Database Segmentation
		- Database segmentation involves dividing a database into separate segments based on criteria such as user roles or data sensitivity.
~ Operational Audits
		- Operational audits focus on evaluating the efficiency and effectiveness of an organization's operating procedures
~ Malicious Update
		- Malicious update is an application-based attack that involves replacing a legitimate update for a program with a malicious one. 
		- The attacker can compromise the program, steal data, or perform other malicious actions.
~ Directory Traversal
		- A directory traversal attack is a type of application attack that involves manipulating the input parameters to access files or directories that are not intended to be accessible by the user, such as configuration files, source code, or system files.
~ Injection Attack
		- An injection attack is a type of application attack that involves inserting malicious code or commands into an application or database to execute unauthorized actions or access sensitive data.
~ Virtualization
		- Virtualization is a technology that allows creating multiple isolated environments on a single physical device. 
		- It can offer benefits such as resource optimization, isolation, flexibility, and security.
~ Containerization
		- Containerization is a technology that allows running applications in isolated environments called containers, **NOT** creating multiple isolated environments on a single physical device.
~ Data Sovereignty
		- Data Sovereignty governs the jurisdiction and legalities of data based on its geographical location
~ Input (BPA)
		- Inputs define the required information for a process and the implications of their timing, not the human and support resources.
~ Output (BPA)
		- Outputs concern the data or products generated by the function, not the resources that support the function.
		- Outputs relate to the final products or data produced by the function
~ Process Flow
		- Process flow describes the operational steps in detail
		- process flow details each operational step, describing how the mission essential function is systematically executed.
~ CPU Starvation
		- CPU starvation is a type of performance issue that occurs when a process or thread does not receive enough CPU time to perform its tasks. 
		- It can affect the responsiveness and functionality of the process or thread.
~ Centralized Environment
		- A centralized work environment is a traditional setup where all employees work from a single location or office.
~ Decentralized Environment
		- A decentralized work environment is a system where different departments or teams work from separate, independent locations but not necessarily from home.
~ Collaborative Environment
		- A collaborative environment is setup prioritizing team collaborations, often involving open spaces and group project areas but not focused on location.
~ Configuration Management
		- Configuration Management is the process of systematically handling changes to a system in a way that it maintains integrity over time, not necessarily implying an automated process.
~ Information-Sharing Organization
		- Information-sharing organization are entities that facilitate the sharing of threat and vulnerability information among different organizations.
~ Expansionary Risk Appetite
		- An expansionary risk appetite involves embracing higher risks for potential higher returns
~ Risk Appetite
		- Risk appetite refers to an organization's willingness to take on risk in pursuit of its business objectives. 
		- It reflects the organization's strategic approach to risk and how much risk it is willing to undertake to achieve specific goals.
~ Neutral Risk Appetite
		- An organization with a neutral risk appetite would take a more balanced approach
~ Conservative Risk Appetite
		- Example: Focusing on products with predictable returns and markets with stable regulatory environments, preferring to avoid unpredictable ventures. 
~ Risk Tolerance
		- Risk tolerance is the extent to which an organization is comfortable with the level of risk it is willing to take. 
		- It represents the organization's ability to withstand potential losses or disruptions.
~ Risk Acceptance
		- Risk acceptance means that an organization understands the level of risk that in involved in an activity and is willing to accept the outcomes of taking the risk. 
		- The risk is either accepted or not, there aren't levels of risk acceptance.
~ Risk Deterrence
		- Risk deterrence involves taking measures to reduce or mitigate the impact of an event.
~ Software Authentication Tokens
		- Software authentication tokens generate time-sensitive codes on devices like smartphones, providing an added layer of security without the need for a physical device other than the user's own device.
~ Chain of Custody
		- Chain of Custody is the process of securing and preserving evidence related to a security incident for potential use in legal proceedings. 
		- When handling digital evidence, it is crucial to maintain a clear and documented Chain of Custody. 
		- This ensures that the evidence is collected, stored, and transferred in a way that maintains its integrity and authenticity, making it admissible and reliable in legal proceedings.
~ Control Plane
		- The Control Plane within the Zero Trust model is fundamentally responsible for deciding on access based on policies and threats, which is a dynamic and multifaceted task.
~ Operational Efficiency
		- Operational Efficiency refers to the effectiveness and productivity of operations
~ RFID Cloning
		- Radio Frequency Identification cloning involves copying the data from one RFID tag (like those found in many security pass cards) and then using a duplicate or "clone" to gain unauthorized access. 
		- The mysterious nighttime entries using legitimate employee credentials suggest this.
~ Exposure Factor
		- Exposure Factor is an estimate of the potential damage to an asset if a given threat exploits a vulnerability, and it is not directly connected to the asset’s total value or frequency of threat events. 
		- An exposure factor of 100% suggests that a security incident or threat event would render the asset entirely unusable or worthless. 
		- The exposure factor is the proportion of an asset's value estimated to be affected or jeopardized during a particular security incident or threat event. 
		- Exposure factor is usually expressed as a percentage representing the portion of the asset's value likely to be lost in an incident.
~ Resource Consumption
		- Resource consumption is an indicator of malicious activity that shows that an attacker or malware has used a lot of system resources, such as CPU, memory, disk space, or bandwidth, affecting the performance or availability of the system.
~ Blocked Content
		- Blocked content is an indicator of malicious activity that shows that an attacker or malware has tried to access or deliver content that is prohibited by the system’s security policy, such as malicious websites, files, or emails.
~ Preparation Phase
		- The Preparation phase in the incident response process involves activities such as developing an incident response plan, defining roles and responsibilities of the incident response team, and conducting regular training and drills. 
		- These preparations ensure that the organization is ready to respond effectively and efficiently to any potential security incidents.
~ Detection Phase
		- Identifying and classifying incidents based on severity and impact.
		- It involves recognizing that an incident has occurred and understanding its potential implications.
~ Triage
~ Risk Identification
		- Risk identification is the first step in the risk management process. It involves identifying potential threats and vulnerabilities that could pose a risk to an organization's assets or operations.
		- Risk identification is the proactive process of recognizing and recording potential threats that could adversely affect an organization.
~ Vulnerability Assessment
		- A vulnerability assessment is a specific method **used within risk identification** to determine the weaknesses within an organization's IT infrastructure.
~ Risk Assessment
		- comes after risk identification and involves evaluating the identified risks to determine their potential impact and likelihood.
~ Risk Analysis
		- Risk analysis is a subsequent step that follows risk identification. It involves evaluating the identified risks and their potential impact on an organization.
~ Risk Register
		- risk register is a tool used in the risk management process to document and track identified risks
		- It comes after risk identification and analysis.
~ Homomorphic Encryption
		- Homomorphic encryption allows for computations on ciphertext, without the need for decryption first.
~ Digital Certificate Rotation
		- Digital certificate rotation is the practice of changing digital certificates at regular intervals.
~ Geographic Restrictions
		- Geographic restrictions primarily deal with ensuring data resides or is accessible only in certain locations due to legal or regulatory reasons.
		- Dictates where data can be
~ Infrastructure Diversification
		- Diversifying infrastructure ensures that organizations are not overly reliant on a single data center, network, or platform. 
		- By distributing their assets and systems across multiple locations or platforms, they can significantly reduce the risk of total service disruption if one component fails.
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
~ Recurring Risk Assessment
		- Recurring risk assessment involves conducting risk assessments at regular intervals to adapt to changing threats and vulnerabilities over time.
~ Continuous Risk Assessment
		- Continuous risk assessment involves ongoing and real-time monitoring of risks as part of the organization's daily operations. It aims to quickly identify and address emerging risks.
~ One-time Risk Assessment
		- One-time risk assessment is conducted only once and does not involve periodic evaluations of risks. 
		- It may be suitable for specific projects or situations but is not focused on continuous monitoring.
~ Ad hoc Risk Assessment
		- Ad hoc risk assessment refers to conducting risk assessments on an as-needed basis or when specific events trigger the need for assessment.
~ Recurring Report
		- A recurring report is a report generated at regular intervals, such as weekly, monthly, or quarterly, to keep stakeholders updated on ongoing security metrics, trends, and concerns.
~ Policy Review
		- A policy review is a periodic assessment of the organization's security policies to ensure they remain current and effective.
~ Threat Intelligence
		- Threat intelligence involves the collection and analysis of information about current and potential attacks that threaten the security of an organization but does not directly refer to the broader process of risk identification.
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
		- Serverless is an architecture model that involves running code without provisioning or managing servers.
~ Responsibility Matrix
		- A responsibility matrix in cloud architecture is crucial for clearly defining the roles and responsibilities between the client and the cloud service provider, ensuring accountability and security compliance.
		- It clarifies who is accountable for what aspects of security, compliance, and operations in a cloud environment.
~ Microservices
		- Microservices is a form of software architecture. 
		- It describes a highly decentralized system that doesn't depend on one type of platform to work.
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
~ Image-Based Attacks
		- Image-based attacks use malicious images, such as JPEGs, PNGs, or GIFs, to exploit vulnerabilities in image processing software or embed malicious code in the image metadata.
~ Pretexting
		- Pretexting uses a story to create a sense of trust with the victim. It makes it more likely that the victim will do what the attacker wants them to do.
~ Removable Device Attack
		- Removable device attacks use devices such as USB drives, CDs, or DVDs to infect systems with malware or perform other malicious actions.
~ File-Based Attacks
		- File-based attacks use malicious files, such as executables, documents, or archives, to infect systems with malware or perform other malicious actions.
~ Static Code Analysis
~ Sanction
		- A sanction is a broader term that encompasses various penalties or restrictions imposed on individuals or entities for non-compliance or misconduct. 
		- While it can include fines, sanctions may also involve trade restrictions, asset freezes, or other punitive measures intended to enforce rules and regulations.
~ Deductible
		- A deductible is an agreed-upon amount that an insured individual must pay out-of-pocket before an insurance company will cover the remaining costs of a claim. 
		- It represents a portion of the financial responsibility that falls on the policyholder and can vary based on the terms of the insurance policy.

~ Dynamic Analysis (Dynamic Code Analysis)
		- Dynamic analysis evaluates software during its runtime, aiming to uncover vulnerabilities that might not be visible in a static state.
~ MITRE ATT&CK Framework
~ Diamond Model of Intrusion Analysis
~ Normalization
~ acquisition
		- During a digital investigation, the goal of the the acquisition phase is to obtain data in a way that doesn't alter the original evidence. Imaging a hard drive is a standard practice to achieve this.

~ VM Sprawl
		- Occurs when an organization has many VMs that aren't appropriately managed.
		- Someone makes a test VM. The admin orchestrates a software patch for all the VMs, but because he's unaware of this one, it doesn't get updated, leaving it vulnerable for an attack. 
~ Resource Reuse
		- In the context of cloud computing risks refers to the potential for data or resources to remain on a shared infrastructure even after a customer has finished using them, making them potentially accessible to other users of the cloud service.
		- Leads to risk of data leakage, as well as unauthorized access to sensitive data or systems. 
		- Resource reuse is a type of vulnerability that involves accessing or modifying data or communications from other virtual machines by exploiting the shared CPU between them. 
		- It can allow an attacker to execute malicious code or commands on other virtual machines.
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
		- Key escrow is a system in which a copy of a cryptographic key is given to a third party. 
		- This allows for the recovery of keys if they are lost.
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
~ RoT (*Root of Trust*)
		- Root of Trust (RoT) is a source that can always be trusted. It is the foundation of a cryptographic system and is the central point of the chain of trust within that system.  It can be a piece of hardware (a Hardware Root of Trust) or software based.
~ CA (*Certificate Authority*)
		- Certificate Authorities (CAs) are trusted entities that issue and manage security credentials and public keys for message encryption.
~ CRL (*Certification Revocation List*)
		- Certificate Revocation Lists (CRLs) are lists of certificates that have been revoked by a Certificate Authority before their scheduled expiration date.
~ OCSP (*Online Certificate Status Protocol*)
		- Online Certificate Status Protocol (OCSP) is an internet protocol used for obtaining the revocation status of a digital certificate.
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
		- Race condition is a situation where the outcome of a process depends on the timing or order of execution of other processes. 
		- It can cause errors, inconsistencies, or security breaches, depending on the nature and importance of the resource.
~ Security Custodian
		- The security custodian is a role responsible for the day-to-day management and implementation of security controls.
		- They work under the guidance of the security officer or security owner to ensure that security measures are correctly applied.
~ Security Owner 
		- The security owner is an individual or entity responsible for the overall security of a specific asset or resource within the organization. 
		- They may have authority over the security of a particular system or data repository
# Acronyms

~ SASE (*Secure Access Service Edge*)
		- SASE (Secure access service edge) combines network security and WAN capabilities in a single cloud-based service, making it an ideal solution for ensuring secure and reliable access to data and applications irrespective of user/device location.
~ SIEM (*Security Information and Event Management*)
		- Their primary purpose is to provide real-time analysis of security alerts and to offer a holistic view of an organization's security scenario
		- SIEM systems can indeed create and maintain a record of an organization's IT equipment as a part of their comprehensive data collection. 
		- One of the critical roles of SIEM is the real-time monitoring and analysis of security alerts across an organization's network. 
		- SIEM systems collect and aggregate log data from an array of sources within an organization’s IT infrastructure, providing a centralized view of the security landscape.
		- SIEM systems are **NOT** primarily used for software procurement or asset management.
~ RDP (*Remote Desktop Protocol*)
		- Remote Desktop Protocol (RDP) port is a type of open service port that is commonly used for remote desktop servers and can be exploited by attackers to perform screen capture, keystroke logging, or malware delivery attacks. 
		- It is the default port for RDP, the protocol used to remotely control a Windows based system’s desktop.
~ SSH (*Secure Shell*)
		- Secure Shell (SSH) port is a type of open service port that is commonly used for remote access servers and can be exploited by attackers to perform on-path attacks, such as session hijacking or replay. 
		- It is the default port for SSH, the protocol used to securely access remote systems. SSH is cross-platform, not Windows based.
~ VNC (*Virtual Network Computing*)
		- Virtual Network Computing (VNC) port is a type of open service port that is commonly used for remote desktop servers and can be exploited by attackers to perform screen capture, keystroke logging, or malware delivery attacks. 
		- It is the default port for VNC, the protocol used to remotely view and interact with a system’s desktop. It is not specific to Windows-based systems.
~ SQLi (*Structured Query Language Injection*)
		- SQLi is a web-based vulnerability that occurs when an attacker injects malicious SQL statements into a database query that is then executed by the database server. 
		- The statements can manipulate or extract data from the database, or execute commands on the server.
~ PKI  (*Public Key Infrastructure*)
		- Public key infrastructure (PKI) is a set of roles, policies, and procedures needed to create, manage, distribute, use, store, and revoke digital certificates and manage public-key encryption.
~ OSINT
		- OSINT (Open-source intelligence) leverages publicly available data sources to gather intelligence on targets, providing valuable insights without breaching any laws.
~ CISO (*Chief Information Security Officer*) / Security Officer
		- The security officer, also known as the Chief Information Security Officer (CISO) or Information Security Manager, is a senior-level role responsible for leading and overseeing the organization's information security program. 
		- They are tasked with defining, implementing, and enforcing information security policies and procedures throughout the organization. 
		- The security officer collaborates with various stakeholders, including management, IT teams, and compliance personnel, to ensure that security measures align with the organization's objectives and industry best practices.
~ ROI (*Return on Investment*)
		- ROI (Return on Investment) evaluates the profitability or benefit of a particular investment
~ CAPEX (*Capital Expenditure*)
		- CAPEX (Capital Expenditure) pertains to the **initial costs** to purchase the asset or tool, not the ongoing or total costs throughout its lifecycle.
~ TCO (*Total Cost of Ownership*)
		- The TCO (Total Cost of Ownership) not only includes the initial purchase price of the tool but also the ongoing expenses related to maintenance, updates, and other associated costs over its lifecycle
~ FMEA (*Failure mode and affects Analysis*)
		- FMEA (Failure mode and effects analysis) is a proactive method to identify possible failures, separate from quantifying time between failures.
~ UTM
		- A UTM (Unified threat management) is an all-in-one security solution that can include a WAF, but it also comprises other functionalities like anti-virus, anti-spam, VPN, and more.
~ mTLS (*Mutual TLS*)
		- Mutual TLS (mTLS) authentication involves both client and server authenticating each other using certificates for secure communication.
~ UI (*User Interaction*)
		- The UI (User Interaction) metric specifies whether an attack can be executed solely by the attacker or if it necessitates user involvement to succeed.
~ PR (*Privileges Required*)
		- The Privileges Required (PR) metric measures the level of privileges an attacker must have to exploit the vulnerability
~ AV (*Attack Vector*)
		- AV (Attack Vector) specifies the context of the exploit, like local or network-based, rather than user involvement.
~ AC (*Attack Complexity*)
		- The AC (Attack Complexity) metric describes the conditions that must be met for an exploit to work
~ XSS (*Cross-site scripting*)
		- Cross-site scripting attacks involve embedding malicious scripts into web content. 
		- These scripts are executed by unsuspecting users
		- XSS is a web-based vulnerability that occurs when an attacker injects malicious code into a web page that is then executed by the browser of a user who visits the page. 
		- The code can steal cookies, session tokens, or other sensitive information from the user or the web server.
~ SD-WAN
		- An SD-WAN is a virtual WAN architecture allowing enterprises to leverage any combination of transport services, making it ideal for the expansion of infrastructure across geographical locations with broad network requirements.
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
		- Software-defined networking (SDN) is a network technology that involves dynamically configuring and managing network devices and services through software
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
~ DPO 
		- Ensure data privacy regulation compliance
~ Data Subject
		- A data subject is an individual to whom the personal data belongs, and they have certain rights regarding the processing of their data. 
		- The subject doesn't play a role in the storage, collecting, and analyzing of data.
~ Data Custodian/steward 
		- A data custodian is typically an individual or entity responsible for managing the system where the data is stored.
		- responsible for managing data in alignment with data owner **big distinction between the data owner and the custodian**
~ Data Owner
		- data owners are responsible for the data's classification and ensuring it meets organizational policies
		- The owner's role is accountable for the data's security and compliance with the organization's strategic objectives.
~ Data Processor 
		- Handles data in accordance with privacy guidelines
		- involves properly collecting, storing, and analyzing the data according to her supervisor's directions
		- A data processor is an entity that processes personal data on behalf of the data controller.
~ Data Controller 
		- Ensures data complies with applicable regulations
		- The data controller is the entity that determines the purposes, conditions, and means of processing personal data. 
		- They make decisions about how and why data is processed.
		- their role is more focused on data **governance** **and compliance** with data protection regulations.
		- The controller is responsible for defining how personal data is handled and ensuring it meets GDPR and other regulatory requirements.
~ Data Broker
		- A data broker collects and sells data to other organizations
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
		- Implementing a federation protocol, such as Security Assertion Markup Language (SAML), is the most effective approach for achieving a seamless user login experience for both internal employees and external partners. 
		- SAML allows for the secure exchange of authentication and authorization data between different organizations, enabling users to log in using their own organization's credentials while accessing resources and applications from other federated organizations without the need for separate accounts. 
		- It simplifies identity management and enhances user experience while maintaining centralized control.
		-  XML based data format used for SSO on web browsers. 
		- Ex: Two websites host by two different organizations, the organizations trust each other, and use SAML as a federated identity management system. 
		- Authenticate with one website and don't have to authenticate with the other. 0\(Google, Facebook)
		- SAML is an XML-based standard for exchanging authentication and authorization data between parties. It's focused more on Single Sign-On (SSO)
~ Kerberos
		- Used to authenticate inside Active Directory environments
		- Kerberos is an authentication protocol that uses tickets to prevent eavesdropping and replay attacks. It relies on a trusted third-party, the Key Distribution Center (KDC), to facilitate mutual authentication between clients and services.
~ CASB
~ OAuth
		- Open standard
		- Provides secure access to protected resources
		- Downloading an app, and it requests access to your google calendar, We are giving this application authorization, without giving it our password, or anything else.
		- Auth in this case stands for *Authorization*, not authentication!
		- OAuth is an open standard for access delegation. It allows third-party services to use account information without exposing user passwords.
~ ESP
~ WAF (*Web Application Firewall*)
		- Web application firewalls (WAF) are used to prevent attacks on backend databases and web server based software. 
		- They can be deployed as appliances or plug-in software and protect against code injection, DoS, cross-site scripting and SQL injection.
		- A WAF (Web application firewall) protects web applications by monitoring, filtering, and blocking HTTP/HTTPS traffic that can exploit any vulnerabilities in the application. 
		- Typically, it operates on Layer 7 (Application Layer) of the OSI model and can specifically defend against common web-based threats.
~ ECC (*Elliptic Curve Cryptography*)
		- ECC (Elliptic Curve Cryptography) is a form of public key cryptography based on the algebraic structure of elliptic curves over finite fields primarily used for digital signatures and key exchanges.
		- Primarily used for digital signatures and key exchanges, rather than direct encryptions of data
~ DES (*Data Encryption Standard*)
		- DES (Data Encryption Standard) is an older symmetric-key method of data encryption which was largely replaced due to vulnerabilities, focusing primarily on data encryption.
		- **Bad**
~ Twofish
		- Twofish is a symmetric block cipher which, like AES, encrypts data in blocks using the same key for encryption and decryption.
~ DNSSEC
~ L2TP
~ AUP
~ CYOD (*Choose your own device*)
~ Embedded RTOS
~ Shadow IT
		- A shadow IT threat actor does not have malicious intent and uses unauthorized or unapproved devices, software, or services within an organization for convenience, productivity, or innovation purposes.
		- Shadow IT is a type of threat actor that is the result of unauthorized or unapproved IT systems or devices within an organization.  
		- Shadow IT can introduce security risks because the unauthorized system or device may provide attackers with a way to gain access to an otherwise secure system
~ Cyber Mercenaries
		- Cyber mercenaries are hackers-for-hire, who may work for any entity or individual that pays them, regardless of the task's legality.
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

~ OCSP
~ CSR (*Certificate Signing Request*)
		- A CSR (Certificate Signing Request) is a formal message sent to a certificate authority to request a digital identity certificate.
~ DSA
~ TAXII
~ STIX
~ tcpreplay
~ Cuckoo
~ Pseudo-anonymization
~ Tokenization
		- Tokenization is the process of substituting a sensitive data element with a non-sensitive equivalent, referred to as a token. 
		- The token and the data it substitutes are stored in a secure database. 
		- If the original data is needed, it can be accessed using the token and querying the database. 
		- The token will be a different size and have a different structure than the original data so the token can’t be used to decipher the original data.
		- Tokenization replaces sensitive data with non-sensitive substitutes or tokens.
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
~SCAP (*Security Content Automation Protocol*)
		- Its main functionality lies in strengthening the security of systems via a standardized approach to maintaining system security, aiding in automating the process of detecting vulnerabilities, managing configurations, and maintaining compliance with regulatory standards. 
		- SCAP aids in automating vulnerability management and configuration settings in a system. It allows security teams to perform tasks effectively and efficiently. 
		- SCAP provides a standardized, consistent approach to maintaining system security, including a common language for expressing security content in a clear and consistent manner. 
		- SCAP does help in ensuring compliance with security guidelines and regulations. It provides a way for organizations to demonstrate that their systems adhere to certain security standards.
		- Helps facilitate communication between vulnerability scanners and other security and management tools.
		- SCAP is NOT used for data encryption 
~CVSS (*Common Vulnerability Scoring System*)
		- Assesses vulnerabilities and assigns severity scores in a range of 0 to 10, with 10 being the most severe. This helps security professionals prioritize their work in mitigating known vulnerabilities
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
		- LDAP is a protocol used to access and manage directory information over a network.
~ Federation
		- Supports SSO for users in different environments/separate networks
		- With my credentials in this company, I can access files from another without signing in again. 
		- *Requires* a federated identity management system that all members use. 
~ SRTP (*Secure Real-time Transport Protocol*)
		- SRTP (Secure Real-time Transport Protocol) provides encryption, message authentication, and integrity for voice communications over IP. 
		- It's designed to protect Real-time Transport Protocol (RTP) and RTP Control Protocol (RTCP) traffic.
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

What is the best explanation for the importance of package monitoring in the context of vulnerability management?
- Package monitoring involves keeping track of software package versions and security patches, which helps identify potential vulnerabilities and ensures that appropriate actions are taken to mitigate risks. 
- By promptly addressing vulnerabilities, organizations can reduce the risk of potential exploits and maintain a more secure environment. 
- The purpose of package monitoring which is keeping track of software package versions and security patches

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
- Understanding the audience, whether it's legal professionals, executives, or technical teams, determines the report's depth, language, and emphasis

What is the value of enumeration in the effective management of hardware, software, and data assets?
- Enumeration, in the context of hardware, software, and data asset management, refers to the practice of assigning unique identifiers, access controls, and attributes to each asset. 
- This process helps in establishing granular control over access permissions, ensuring that only authorized users can interact with the assets.
- It plays a vital role in maintaining data confidentiality, integrity, and availability by preventing unauthorized access and ensuring proper management of resources.

Which characterstic of blockchain technology ensures that the risk associated with having a single point of failure or compromise is mitigated?
- One of the most important characteristics of blockchain is its **decentralized nature**, distributing the ledger across a peer-to-peer network, thus eliminating a single point of failure.

What are the steps involved in the risk management process? 
1. Risk Identification
2. Risk Assessment
3. Risk Analysis
4. ????

What are the different phases of the Incident Response Process?
1. Preparation Phase
2. Detection Phase
3. Recovery and lessons learned phase

Why are cloud backs not always the best option?
- Although they provide flexibility and scalability, relying solely on cloud backups might present challenges if there are internet connectivity issues during a disaster.

What is the primary purpose of internal compliance reporting?
- The primary purpose of internal compliance reporting is to provide updates on compliance status, identify potential issues, and inform the organization's management about its adherence to regulatory requirements and policies. 
- Internal compliance reporting provides information about what exists to a company's managers.
- Internal compliance reporting is not intended for public disclosure; it is focused on internal communications within the organization.

Which components encompasses a BPA?
- Inputs
- Process Flow
- Staff
- Outputs

Which kind of details can we find by examining a TLS handshake?
- Examining the TLS handshake details can help in verifying if the secure connection was established using strong cryptographic algorithms, and it can also reveal the certificate information to check for any anomalies or unauthorized certificates. Analyzing DNS query responses is crucial to understand which domain names were resolved and to identify any potential malicious or unauthorized domain interactions. Both of these details are vital for investigating the incident, especially given the nature of the communication to a sensitive server over a secure port and the observed abnormal DNS requests.

What is an example of the CVE format:
- CVE2022-12345

Why are CVEs important to Cybersecurity Professionals?
- CVEs allow cybersecurity professionals to talk about vulnerabilities in a consistent manner, ensuring everyone is on the same page.
- Standardized way of sharing vulnerability data

What is an example of the importance of automating user provisioning?
- Automated user provisioning helps in granting immediate access rights, reducing waiting times and hence improving productivity

What is the significance of the key length in encryption standards?
- Key length in encryption determines the minimum length that an encryption key can be to ensure a strong level of security. 
- While length will impact the key's complexity, the key length doesn't set other factors beyond the minimum length.

What is a common issue with SCADA systems?
- Many SCADA systems utilize legacy communication protocols that lack modern security features, making them vulnerable to unauthorized interception or tampering.
## Secure ports
FTPS: port 990
SRTP: port 5004
SFTP: port 22 (just like SSH)
LDAPS: 636
LDAP: 389
587

## General






