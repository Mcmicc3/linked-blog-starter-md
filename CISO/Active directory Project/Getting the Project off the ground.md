
## As of Now
I don't know how much I should heavily rely on HTB
I don't know if I'm committed to making new slides from scratch each week..
	*Hence HTB*
My problem with HTB, is that my main goal is to come up with a project 

14 weeks (Roughly)
Beginner - Advance
Lecture & Hands-on
*Explain the vision of becoming an expert*
Benefits: Resume Builder, Job opportunities people haven't considered
Target Audience: Blue team (Sys Admins, SOC analysts, enterprise architect), Red Team (Penetration Testing) 
Make it clear in the first slide of each week, the difficulty increasing based on ChatGPT learning curve.
List a set of goals I want to teach each week 
*Maybe I should take a poll on whether there's more people interested in Blue or Red team?*
*Lookup AD certificates (Azure AD)*

## Rough Overview of Lesson Plan
1. Fundamental Active Directory concepts
	1. Domain controllers, OUs, Forests, Domains, and trusts
	2. Understanding Kerberos, NTLM, and LDAP
	3. Understanding Privileged accounts (Domain Admins, Enterprise Admins)
2. Develop Administration skills
	1. Enforcing GPOs
	2. Setting up email servers?
	3. Setting up tiered administration models (separating user, server, and admin accounts)
3. Interesting concepts
	1. Active Directories integration with the cloud 
	2. ?? *Ideally important modern technologies*
4. Attack Techniques and Defense Strategies
	1. Learn common AD Attacks (Pass-the-Hash, Kerberoasting, DCSync, Golden Ticket)
	2. Learn how to detect threats using **Windows Event Logs, Sysmon, and SIEM tools**.
	3. Secure AD with **LAPS, ESAE (Red Forest), admin tiering, and robust GPOs**.
		1. *Maybe I can prepare students for Christians project in doing goal 3?*
5.  EXPERT TOPICS (Talk about them?)
	1. Implement **Zero Trust principles** in AD security.  
	2. Learn how **Azure AD integrates with on-prem AD** and how to secure hybrid identities.  
	3. Work with **Security Operations Center (SOC) teams** to monitor AD threats in real time.

#### Ideas to consider squeezing in
6. AD Cloud
7. Common AC Sysadmin stuff - Email servers, ???, ???
8. Hack the Box (AD) - {LINK}
9. Deep talk into the careers you can get into by going down this path.
	1. *Great idea for week 1*

## Project source material
10.  ChatGPT
11. Cyber Mentor: [Hacking Active Directory for Beginners](https://www.youtube.com/watch?v=VXxH4n684HE&list=PLCxGvpyaPXZdDithYGh3NQTGFbMAJJq3v&index=34&t=5504s)

## ChatGPT prompts:
12. I want to lead a project that teaches cybersecurity students Active Directory. Can you explain to me the ideal target audience that my project would be for, and the possible careers opportunities they could get if they choose to become experts in the field? I want to reach a wide target audience, from folks interesting to blue, red, and purple teaming. 
13. Please help me design a 14-week lecture plan on teaching students Active Directory? This project is intended for students with different levels of expertise. I'm teaching this to cybersecurity students, so I want to dive into active directory cybersecurity-related topics at some point in the lecture plan. Maybe things along the lines of protecting against breaches or giving demonstrations of exploiting active directories when protective measures aren't set. I want it to be a mix of me giving a lecture to students and a mix of students being involved, downloading the software on their computers, and following along with me. Each lecture is only an hour long.
14. I'm looking to design a concise 14 week lesson plan that is geared towards teaching cybersecurity students skills and concepts related to Active Directory. I want the lesson plan to be both lecture based and hands on, and I want the lesson plan to cover fundamental topics in Active Directory, and then overtime cover some cybersecurity related topics for blue team and red team students. Focus on creating a lesson plan that will result in real world skills that my students will learn so that they may put a project they've done into a resume. 
15. What are alternatives to Active Directory for enterprises that choose not to use it? Why would they want to choose something else?

### Prompt Suggestions from ChatGPT:
#### **Deeper Dive Questions:**

16. **Would you like recommendations for hands-on AD security labs and tools to practice penetration testing and defense?**
17. **Are you interested in real-world case studies of AD attacks and how companies responded?**
18. **Would you like a breakdown of specific AD security tools like BloodHound, Mimikatz, and Purple Knight?**

## ChatGPT: Learning curve from beginner to expert
### **The Learning Curve: From Understanding AD to Securing It as a Cybersecurity Expert**

#### **1. Basic Understanding of Active Directory**

🔹 Learn about AD **domain controllers, organizational units (OUs), forests, domains,** and **trusts**.  
🔹 Understand **Kerberos authentication, NTLM, and LDAP**.  
🔹 Get hands-on experience setting up a **Windows Server AD lab** (install AD DS, create users, groups, and policies).

#### **2. Intermediate: Administration & Security Best Practices**

🔹 Learn **Group Policy Objects (GPOs)** and how they enforce security.  
🔹 Study **privileged accounts** (Domain Admins, Enterprise Admins) and how to protect them.  
🔹 Implement **tiered administration models** (separating user, server, and admin accounts).

#### **3. Advanced: Attack Techniques & Defense Strategies**

🔹 Study **common AD attacks** (Pass-the-Hash, Kerberoasting, DCSync, Golden Ticket).  
🔹 Learn how to detect threats using **Windows Event Logs, Sysmon, and SIEM tools**.  
🔹 Secure AD with **LAPS, ESAE (Red Forest), admin tiering, and robust GPOs**.

#### **4. Expert Level: Enterprise Security & Incident Response**

🔹 Implement **Zero Trust principles** in AD security.  
🔹 Learn how **Azure AD integrates with on-prem AD** and how to secure hybrid identities.  
🔹 Work with **Security Operations Center (SOC) teams** to monitor AD threats in real time.

Mastering AD security will prepare you for roles in **red teaming, blue teaming, penetration testing, and identity security architecture**.