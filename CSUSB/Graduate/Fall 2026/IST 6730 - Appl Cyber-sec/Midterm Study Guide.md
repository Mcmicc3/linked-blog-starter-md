
### The big picture

This is a **management-focused cybersecurity course** built around the **CompTIA CySA+ (Cybersecurity Analyst)** certification. The instructor says so directly in Week 1: his bias is toward _managing the enterprise and the process_, not hacking. The course isn't trying to make you a hacker. It's teaching you to think like the person responsible for an organization's security: someone who weighs risk against cost, picks frameworks, designs controls, spots when something is wrong, and knows how to respond.

The weeks follow a logical order that mirrors how a real security program works:

1. **Understand the landscape** (frameworks, risk, governance)
2. **Build defenses** (networks, firewalls, access control)
3. **Detect problems** (monitoring, logs, malicious activity)
4. **Know your enemy** (threat intelligence, reconnaissance)
5. **Find and fix weaknesses** (vulnerability management)

The first half lines up with CySA+ Objectives 1 (Security Operations) and 2 (Vulnerability Management), which is what the Week 8 midterm covers.

### Week-by-week

**Week 1: Foundations and Frameworks**  
This week covers course logistics and the "security mindset": defenders must be right 100% of the time, while attackers only need to be right once. Security spending is an economic and legal decision, not just a technical one. The main content is a tour of the governance frameworks and standards the rest of the course leans on: NIST CSF, ITIL, COBIT, COSO, the CIS 18 Controls, and the CISSP domains. It also covers threat-modeling and vulnerability vocabularies (STRIDE, CVE, CVSS, CWE) and an overview of certifications.

**Week 2: Risk and Building a Secure Environment**  
This is the core defensive toolkit. It starts with risk theory (Risk = Threat × Vulnerability, and the NIST 800-30 assessment process) and privacy principles. Then it covers the controls that reduce risk: network access control, firewalls and rule ordering, network segmentation, preventing lateral movement, Zero Trust, deception/honeypots, endpoint management, and access control models (MAC, DAC, RBAC). It ends with penetration testing, reverse engineering, and automation (SOAR).

**Week 3: Detecting Malicious Activity**  
Once the defenses are built, how do you tell when something is wrong? This week covers network monitoring (flows, active vs. passive), warning signs like beaconing, traffic spikes, scans, DoS attacks, and rogue devices, and host-level red flags like odd processes, registry changes, and scheduled tasks. It also touches on log sources, packet capture, and email analysis.

**Week 4: Threat Intelligence**  
This week is about understanding who attacks and how. Topics include open-source intelligence (OSINT) and its dark side (attackers use it too), the intelligence cycle, threat actor types, TTPs, threat hunting, indicators of compromise, and the CVE/CVSS/NVD ecosystem and MITRE ATT&CK.

**Week 5: Tools, Incidents, and Reconnaissance**  
This week surveys common security tools (antivirus, scanners, IDS/IPS, packet sniffers, encryption) and the ten common incident types and how to prevent them. It introduces the **Cyber Kill Chain** (the stages of an attack) and reconnaissance techniques, with hands-on port scanning in Kali Linux.

**Week 6: Designing a Vulnerability Management Program**  
The week starts with a detailed walkthrough of all 18 CIS Controls as a practical checklist and a comparison of CIS with NIST. Then it covers how to build an ongoing program to find vulnerabilities, including the OWASP Top 10, and a lab installing and running Nessus.

**Week 7: Analyzing Vulnerability Scans**  
This week covers how to interpret scan results and prioritize what to fix, plus midterm prep. It also assigns a memo comparing three real major breaches (e.g., Target, SolarWinds, Colonial Pipeline, Equifax).

A useful way to hold it all together: each week answers a question a security manager faces. Weeks 1–2 answer "What should we protect and how?" Week 3 answers "Is something wrong?" Week 4 answers "Who's coming?" Week 5 answers "How do they get in?" Weeks 6–7 answer "Where are we weak, and what do we fix first?"