## Important Links
[https://47.146.145.136:8006/](https://47.146.145.136:8006/ "https://47.146.145.136:8006/") 
Username: "Name" (with capital) 
Password: iloveciso2025! 
Realm: Proxmox VE


# Active Directory Notes
- **Supporting NTP (Network Time Protocol)** – AD domain controllers automatically function as time sources for domain-joined machines. The Primary Domain Controller **(PDC) Emulator FSMO** role is responsible for time synchronization. Typically, you configure the PDC to sync with an external NTP source (e.g., time.windows.com) and have all other domain members sync from the domain hierarchy.
    
- **ePolicy Orchestrator (ePO)** – This is **McAfee’s centralized security management tool.** It typically integrates with AD for authentication and user/device policies. While AD itself doesn’t “run” ePO, AD simplifies deployment by allowing centralized management and authentication through group policies and security groups.

## ChatGPT Suggestions
#### Getting started
✅ Installing Windows Server (2019 or 2022) in Proxmox  
✅ Setting a static IP and configuring the hostname properly before promoting it to a Domain Controller  
✅ Installing AD DS (Active Directory Domain Services) and DNS together  
✅ Configuring time synchronization properly after setting up AD

# Software Overview

Clusters on proxmox?
- They're considering

Openvswitch - 
- Switch for after the firewall (Opensense)
- **Only Vswitch**
- 

OPNsense - https://opnsense.org/
- Firewall server
- Forked version of PFsense, more modern, more updates.

Vagrant - https://developer.hashicorp.com/vagrant/docs/providers/hyperv
- Hypervisor
- Dependncie for Nos 3

OpenLDAP - https://www.openldap.org/
- Linux version of Active Directory
- Not sure if we need to do this part
- Looking at this for COSMOS

**Cosmos** 
- Software
- Command and Control for Satellites. 
- **Control System Server**

**Nos 3** 
- Satellite
- **Control System**

Rocky Linux - https://rockylinux.org/
- Community version of Red Hat Linux
- Is what CentOS, was
- **Not sure if we're gonna use it**
- 

Encalave Switch
- IDS for Industrial Control Systems

Convert vsphere
- Convert from proxmox to vsphere
- Get the hard parts done on proxmox first. 
- Convert to Vsphere so it works on cyberlab

Admin servers
- Active Directory
- 