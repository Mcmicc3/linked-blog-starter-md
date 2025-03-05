###### Describe virtualization and the best examples you use daily; what are suitable applications for virtualization and what are not?

-- ## Applications of Virtualization
- Collaboration tools: Zoom, Google Docs, Teams 
- Can the solution scale to meet the organizations future needs?
- Is the solution secure? Wheres the data going, how is it being protected? Continuous monitoring, annual assessment
- What are the solutions startup and operational costs?
- How will the solution impact the company's IT staffing and resource requirements? Will you need additional staff 
- What are the solution's learning curve and training requirements? Is it intuitive? or will it require a lot of training for users and admins
- **WEB MAIL**, **VoIP**, **Websites (Wiki, Google)**
- Don't put valuable things on the free versions of google docs, otherwise google owns the data
- blogs, getting news out there, private to public, internal blogs, scientific blogs, collect feedback from readers. Sometimes you can get bad comments and end up with an opinion blogs, instead of a blog that posts facts
- Cloud based meetings: training, board meetings, record sessions, saves time and money (flights)
- Social Media, limit who has access, privitize information or make it public. Most people are already familiar with it. 
- Cloud based calendars, webbased, syncs to other devices and other applications. 
- Streaming video content

-- ## What is virtualization
![[Pasted image 20250223173259.png]]
- Cloud = virtualization
- Virtual resources are being scaled.
- It takes more time to configure and add data to a physical server than on a cloud
![[Pasted image 20250223173421.png]]
Server virtualization
- Supports different OS's
- Smaller hardware footprint
- Better CPU utilization 
- Leverage less power
Desktop Virtualization 
- Allows you to go between multiple OSs
- Centralizes what needs to be updated (thin clients). More efficient since you only have to update one image.
virtual networks
- SDN, smaller device footprint, you can add resources easier than in real life
- Replacing a physicals environment would take months instead of days
virtual storage
- Remove the need for devices. Relying less on virtual 

Virtual Memory
- Appears limitless. RAM is not cheap. 

Servers aren't green, use a lot of power. 

Provides load balancing


Describe the different types of Hypervisors?  What type of virtualization and hypervisor are most commonly used in the cloud?
![[Pasted image 20250223181435.png]]
Type 1 
- Sits between the hardware and the VM
- Sits ontop of the hypervisor
- Performance and security 
type 2 
- Runs in specialized OS that sits between the hardware and virtual OS
- Bare metal, thin client
- Simpler management and configuration

Hyper-V (Microsoft)
- Complex
VMware 
Virtualbox

Desktop Virtualization (Thin client)
- Work is saved to a cloud
- Create images
- Only manage images
- Patching vulnerabilities becomes easier
- You have control over the VM (Security)
- GPO help prevent employees from changing the environment
	- Configuration controls, every time they log on, it will change back to what's in the GPO
- A single desktop can run multiple OS's
- Less need for duplicate hardware
- less power
- *Disadvantage*: there is overhead due to virtualization, meaning it's not as fast as identical standalone systems on single OS's

Simplified OS and Application Administration

--- 


###### Describe hypervisor and SQL injection attacks and at least three other security issues commonly impacting Cloud Service Providers.  
Data centers are often leased 3rd party companies. Physical security becomes important
- Security is so important that Amazon and Google keep the location of their data centers a secret. 
- **Server rooms are never on the first floor**

There are two types of threats. 
1. Threats common to both cloud based and on premise solutions
	1. Needing patch updates for OS
	2. Having firmware issues (Hardware is still utilized)
2. Concerns specific to cloud
	1. VM leak

-- ## Disadvantages
Country or jurisdiction issues. (Logical separation) Possibility that if someone screws up, you might have co-mingling of data on the database. 

Data remnants from one company might be exposed to another in situations where data-strorage devices are shared. 

Malicious insider

Vendor lock in - Could be hard to change providers down the line if an event happens, or the is a SLA problem. 

Cloud providers fail. 
- 

###### Describe the mitigations for each of the security issues you have described above.  

Hardware and software redundancy
Timeliness of incident response

Incident response is like account, it doesn't make money. 

Fix for jurisdiction/country issues  - Ask for physical isolation, your own instance on bare metal. Ask for blade server. 

Fix for malicious insider: Employees should NOT have access to customer data. There should be safeguards. They should be able to access the system, not the data. 

Fix for vendor lock ins: Have two vendors for backups. 

Cloud based antivirus software

Disk wiping is not an option. You need to do *Crypto shredding*. 
- You share disk space with customers
- Unless you asked for physical isolation

DDOS attacks
MITM attacks
Guest-Hopping Attack

###### How can cloud service providers harden their systems to prevent these types of security issues?
*Reduce a systems vulnerability and risks*

![[Pasted image 20250223194504.png]]

Require HTTP/TLS.
Ensure data at rest encryption
Better passwords, deploying firewalls, vulnerability assessments, using encryption. 

Crypto shredding
- Encrypt all of your data, and then shred the keys
- Nobody can recover that data. 
- Allows you to feel confident that your data is secured even after leaving a multi-tenet environment

Leveraging colocation
- One site mirrors another
- Continuity plan
- 