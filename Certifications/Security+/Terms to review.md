IRP Life cycle
IRP Process
Cyber Kill Chain
MITRE ATT&CK Framework
Diamond Model of Intrusion Analysis

Normalization
acquisition
ISA
Air gapping - Network of devices that are separated from the internet and LANs. No physical or wireless connection to other networks
IPsec
VPC endpoint?
VPC - Virtual Private Cloud    (VPC Endpoint, peering, gateway transit Internet gateway)
SED - Self encrypting drive 
PBKDF2 - key stretching
COOP - Continuity of Operations
IoC - Indicators of Compromise
MOA - Memorandum of Agreement
ISA - Interconnection Security Agreement
MSA - Measurement System Analysis
DPO - Ensure data privacy regulation compliance
Custodian/steward - responsible for managing data in alignment with data owner **big distinction between the data owner and the custodian**
Data Processor - Handles data in accordance with privacy guidelines
Data Controller - Ensures data complies with applicable regulations
PHI (Protected Health Information)
RPO
RTO
MTBF
MTTF
MTTR

~ auth.log
~ aggregating
~ syslog
~ NetFlow
~ sFlow
~ OpenID Connect
~ privileged access management
~ SAML
~ Kerberos
~ OAuth
~ ESP
~ TPM
~ HSM (*Hardware security module*)
	- SD card used for smart phones
	- Supports cryptographic operations like encyption, decryption, digital signatures, generates hashes, 
~ WAF
~ DNSSEC
~ L2TP
~ IPsec using Tunnel mode and transport mode
~ CYOD
	- Choose your own device
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
~ SLE  - *Single loss expextancy. Cost of loss per occurrence*
~ ARO
~ ALE
~ Credentialed scan - *Vulnerability scan that includes credentials*
~ Non Credentialed scan - *Vulnerability scan that doesn't include credentials*
~ MTBF - *Mean Time Before Failure. Average time things that can't be repaired break, like HDDs or routers*
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
~OAuth
~ SAML
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
## Secure ports
FTPS: port 990
SRTP: port 5004
SFTP: port 22 (just like SSH)
LDAPS: 636
LDAP: 389



