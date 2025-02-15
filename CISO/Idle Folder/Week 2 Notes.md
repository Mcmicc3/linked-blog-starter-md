
live database that stores user accounts and their passwords, computers, printers, file shares, security groups and their respective permissions

We use groups frequently for security purposes. It can work in conjunction with group policy to assign specific permissions for objects within AD. 

## Purpose of AD
Handles security authentication across the domain. 
- Only authorized users can logon to network computers

Centralized security management of network resources
- User accounts are stored in one place instead of each individual computer. 

## Common tasks 
Reset passwords 
Create / delete user accounts

# Without AD
You would need to create a local user account on each computer. If someone needed a pw reset, you had to go to each individual computer
- Imagine a situation where you're supposed to be able to log on from multiple devices, like school

## With AD
Centralized management
- Each individual computer that is part of the domain, queires active directory for the users password
- Saves tedious management

---

## Which Windows Server should we pick?

Windows Server 2012 R2?
- Support ended 2023

Windows Server 2016?
- Support ends 2027

Windows Server 2019?
- Support ends 2029

Windows Server 2022?
- Support ends 2031

Windows Server 2025?

---

## Windows Server Standard vs. Essentials: Key Differences

|**Feature**|**Windows Server Standard**|**Windows Server Essentials**|
|---|---|---|
|**Intended Use**|Mid-to-large businesses|Small businesses (≤25 users, ≤50 devices)|
|**Maximum Users/Devices**|Unlimited (based on licensing)|**25 users / 50 devices** (hard limit)|
|**Domain Controller (DC) Role**|Can have multiple DCs|Must be the **only DC** in the domain|
|**Virtualization Rights**|**2 Virtual Machines (VMs) allowed**|**1 physical instance only** (no Hyper-V rights)|
|**Active Directory (AD)**|Full AD DS capabilities|Limited (no multi-domain support)|
|**Remote Desktop Services (RDS)**|Requires additional CALs|**Limited to 10 Remote Desktop connections**|
|**Licensing Model**|**Core-based licensing** (requires CALs)|**Per-server licensing** (no CALs needed)|
|**Built-in Features**|Supports full enterprise features|Simplified for small business needs|
|**Hyper-V Support**|**Yes** (2 VM rights)|**No VM rights** (must run on physical hardware)|
|**Best For**|Businesses needing **scalability** and **virtualization**|Small offices that need a simple **file, print, and AD server**|

---
## Recommended Resource Allocation

### **Recommended System Requirements for Windows Server 2019 in VirtualBox**

| **Component**              | **Minimum**    | **Recommended (For Smooth Experience)** | **Optimized (For Larger Labs)**     |
| -------------------------- | -------------- | --------------------------------------- | ----------------------------------- |
| **CPU Cores**              | **2**          | **2-4**                                 | **4-6**                             |
| **RAM**                    | **4 GB**       | **8 GB**                                | **12-16 GB**                        |
| **Storage (Virtual Disk)** | **40 GB**      | **80-100 GB**                           | **120+ GB**                         |
| **Networking Mode**        | NAT or Bridged | Bridged (for network realism)           | Internal (for isolated lab network) |

### **🔹 Other Important VirtualBox Settings**

✅ **Enable I/O APIC** (required for multiprocessor support)  
✅ **Enable PAE/NX** (ensures Windows Server can use more than 4GB RAM)  
✅ **Enable Nested VT-x/AMD-V** (if your laptop’s CPU supports virtualization)  
✅ **Set Display Memory to at least 128MB** (helps with GUI responsiveness)  
✅ **Take VirtualBox Snapshots** before making major changes

### **🔹 Final Recommendations**

- **For a single AD setup:** 🖥 **4 cores, 8GB RAM, 80GB disk**
- **For AD + one Windows 10 workstation:** 🖥 **6 cores, 12-16GB RAM, 120GB disk**
- **For a multi-student lab where each person has a different role:** 🖥 **8+ GB RAM, 4+ cores, 100GB disk**

---
## Vbox setup
We want the machine to communicatewith the internet, and other virtual machines

1. File Menu
	1. Preferences
	2. Go to Network
	3. NAT Networks --> Hit plus button to add network
	4. Hit tool wrench to rename NAT Network
	5. Change IP to: 192.168.0.0/24
	6. We can leave DHCP enabled
2. Configure ethernet adapter for NAT Network
	1. Change the drop down to the NAT we just created


---
## Setup Notes
Install VirtualBox Guest Edition CD Image
- Devices --> Insert Guest Additions CD image
- Open Windows Explorer --> Select VBoxWindowsAdditions
- All the defaults should be good

*This is for resizing resolution issues & Copy and paste from Host*

Select Local Server
3. Ethernet --> IPv4 assigned by DHCP
	1. Put it on the LAN
	2. **I noticed he put 127.0.0.1 for DNS Primary**
4. Computer name --> Select name
	1. Click Change
	2. Somethingthen DC for domaincontroller then 01
		1. ITFDC01
	3. Restart the computer

---

## Configuring a domain controller
#### What the hell is a domain controller?

A **Domain Controller (DC)** is a **server that manages authentication and security in an Active Directory (AD) domain**. It is responsible for verifying **user identities**, enforcing **security policies**, and controlling access to network resources.
##### Key Functions 
- **Authentication** 🆔
    
    - When users log in to their computers, the DC checks their credentials against the **Active Directory database**.
    - It uses **Kerberos** or **NTLM** authentication protocols.
- **Authorization** 🔑
    
    - Once authenticated, the DC **grants or denies access** to shared files, printers, or applications based on **user permissions** and **group memberships**.
- **Active Directory Database Storage** 📂
    
    - The DC **stores and manages** the **NTDS.dit** database, which contains:
        - User accounts
        - Groups
        - Computers
        - Policies
        - Security settings
- **Enforces Group Policies (GPOs)** 🏛
    
    - A DC applies **Group Policy Objects (GPOs)** to enforce security settings (e.g., password policies, firewall rules, software restrictions).
- **Manages DNS for AD** 🌎
    
    - AD **requires** DNS to function, and a DC often acts as a **DNS Server** to resolve domain-related queries.
- **Time Synchronization (NTP Server)** ⏳
    
    - The **Primary Domain Controller (PDC) Emulator** in an AD environment ensures all devices have **synchronized clocks**, critical for Kerberos authentication.
- **Replication and Redundancy** 🔄
    
    - In multi-DC environments, **domain controllers synchronize data** to ensure redundancy and high availability.

### Configuration steps

We're going to install Active Directory Domain Services, or ADS role. 
- Any server running the ADS role is considered a domain controller.

We need to add this role to our server to make it a domain controller.

1. Select manage then Add Roles and Features
2. Choose Role-Based or feature-based installation
3. Make sure the name of your PC is selected
4. In the services role, select Active Directory Domain Services Role
	1. Select the add features button if it pops up
5. We don't need any additional features, hit next
6. AD DS services, We're about to install DNS, hit next
7. Hit install and wait for installation to finish

Once this is done, select the flag with the triangle in the exclamation point, and click "Promote this server to a domain controller"

1. Wizard pop ups

**Things to note**:
- this is where we can create subdomains
- separates data and resources, separates logins
	- Example: CSUSB.EDU (admins & Developers), 
	- Courses.CSUSB.EDU (Students & Teachers)
- 

1. Change the option to select a new forest



---

## Certs

### Beginner
##### Prerequisites: Understand networking
- Active Directory heavily relies on a stable network infrastructure (DNS, DHCP, etc.). Understanding networking is foundational before diving into directory services

**Microsoft 365 Fundamentals (Exam MS-900)**
- **What It Covers**: High-level overview of Microsoft 365 services (including an introduction to identity and access management).
- **Why It Helps**: You’ll gain familiarity with the Microsoft ecosystem and basic Azure Active Directory (Azure AD) concepts. It’s a stepping-stone for more in-depth Microsoft certifications.

**Microsoft Azure Fundamentals (Exam AZ-900)**
- **What It Covers**: Core cloud concepts, Azure services, security, privacy, and pricing models.
- **Why It Helps**: Offers a broad introduction to Azure, including Azure AD (Microsoft’s cloud-based identity service). It’s not AD-specific, but it sets a good foundation for more advanced Azure identity certifications.

### Intermediate
##### Prerequisite: Security+
**Why It Helps**: While not specifically AD-focused, strong security fundamentals are critical for managing and securing AD (especially privileged accounts and group policies).

**Microsoft 365 Certified: Modern Desktop Administrator Associate (Exams MD-100, MD-101)**

- **What It Covers**: Deployment, configuration, security, maintenance, and management of Windows client devices and services in an enterprise environment.
- **Why It Helps**: You’ll get hands-on with Windows client administration, including Group Policy basics and integration with Azure AD or on-premises AD for identity and access.

**Microsoft Certified: Windows Server Hybrid Administrator Associate (Exams AZ-800, AZ-801)**

- **What It Covers**: Administration of core Windows Server workloads and services on-premises, hybrid, and in Azure, including Active Directory Domain Services (AD DS), Group Policy, and identity management.
- **Why It Helps**: This certification replaced older on-premises Windows Server exams (like MCSA). It’s more comprehensive, covering modern hybrid environments where on-prem AD links with Azure AD.

### Advanced / specialized certs

2. **Microsoft Certified: Identity and Access Administrator Associate (Exam SC-300)**
    
    - **What It Covers**: Azure AD identity management, authentication methods (e.g., MFA, passwordless), conditional access, identity governance, and more.
    - **Why It Helps**: If you’re leaning into Azure AD and cloud-based identity, this certification is a prime choice. It demonstrates your capability to manage and secure both cloud and hybrid identity solutions, including directory synchronization with on-prem AD.
3. **Microsoft 365 Certified: Enterprise Administrator Expert**
    
    - **What It Covers**: Planning, migrating, deploying, and managing Microsoft 365 services (including identity, security, compliance, and supporting technologies like Azure AD Connect).
    - **Why It Helps**: The “Enterprise Administrator Expert” title indicates higher-level proficiency in orchestrating complex Microsoft 365 deployments. There’s a strong focus on identity and security across on-premises and cloud environments.
4. **Microsoft Certified: Azure Solutions Architect Expert (Exams AZ-305 and prerequisite AZ-104)**
    
    - **What It Covers**: Designing and implementing Azure solutions, which includes identity management, networking, and security.
    - **Why It Helps**: Though broader than just AD, mastering Azure architecture inherently covers Azure AD design considerations for large enterprises. It positions you as someone who understands how identity fits into overall cloud infrastructure.
5. **Microsoft Certified: Cybersecurity Architect Expert (Exam SC-100)**
    
    - **What It Covers**: Advanced identity and security strategies, including securing enterprise identity and access in both on-prem and cloud-based AD environments.
    - **Why It Helps**: If you want to position yourself as a security architect who deeply understands the complexities of AD and Azure AD, this advanced cert may be a goal down the road.

### **Summary**

- **Entry-Level**: Look at broad IT fundamentals (CompTIA A+, Network+), plus Microsoft or Azure Fundamentals (MS-900, AZ-900) to get a foundation.
- **Intermediate**: Progress to more hands-on AD topics with Microsoft 365 Modern Desktop or Windows Server Hybrid Administrator certs, and possibly Security+.
- **Advanced**: Specialize in identity management (SC-300), Microsoft 365 administration at an enterprise scale (Enterprise Administrator Expert), or become an architect (Azure Solutions Architect Expert, Cybersecurity Architect Expert).



---
## UI (Server Manager)

Lets learn the interface:

![[Pasted image 20250214010049.png]]


![[Pasted image 20250214011743.png]]


## Active Directory Users and Computers
![[Pasted image 20250214011845.png]]

You can delegate a domain, search for domains, change domains (subdomain or trusted), filter objects, change domain controllers, 

---

