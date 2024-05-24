## Statement of interest (Container Escape)
- I recognize the importance of containers, it's wide usage, and how it's not going anywhere
- I recognize that it can integrated with the cloud
- I am interested in understanding how technology can be vulnerable and how to harden said technologies
- There are areas in IT that interest me, that I've been wanting to learn more about, including cloud technology, and containerization
- This project, would be a great opportunity for me to learn about this subject deeply
- I'm attracted to the idea of contributing to the solution for this problem, and the improvement of this technology
- I like learning technical things, and understanding how to operate software. I want to get my hands dirty (in dust? lol), and learn the commands required to run this software.


### Description of the research problem skeleton

- Comprehensive description of the problem
	- Explain containers, but only briefly
		- I don't want it to be a long crash course right away, that way we don't lose the PM's interest right away.
	- Then talk about container escape. 
- It's Significance for the overall domain of cyber security
	- Get creative, talk about everything that can go wrong if this happens. 
	- Talk about how container escape can be the entry point that leads to something worse. (Rootkits, mass distribution of malware?, lateral transition to other internal machines)
	- Mention that this is terrible for developers, companies, consumers
	- Lost of trust in the technology, the product, and possibly the company
	- Finish by explaining the importance of protecting these containers
- Segway back into the description of the problem,
	- Talk about container escape, and the importance of understanding it's unique attack surface. 
	- Provide a brief example
		- MicroVMs are created quickly
		- Test VMs can be easily forgotten and misconfigured, and for this reason can be abused
	- List the major risks, and then explain how the countermeasures are listed in the NIST document
	- Despite these countermeasures, we can never gurantee complete security. Zero Days, and CVE's are still being found to this day
- Current status in respect to possible solutions of the problem
	- Talk about, trying to harden these measures, by using what was proposed in the first bullet. Sandboxed container runtimes, in conjunction with MicroVms
	- Briefly give examples and talk about these technologies, gVisor and Firecracker respectively. 
	- Explain that MicroVMs use hardware-based virtualization for isolation, creating separate virtual machines. Sandboxed containers, on the other hand, rely on Linux kernel features like namespaces and cgroups for isolation within the same operating system instance.
	- Tie in how this technology working in conjunction, attempts to solve the project problem. 
	- The question becomes, how effective is this security in depth solution. Is it effective in containing a security breach? Would it impact an applications efficiency? Is it practical? Is it (Synonym for works well with many different apps).
	- These are the type of questions that our research team wants to answer (mic drop)
- Include the respective literature review as an integral part of the problem description
	- Find quotes from articles, papers, credible sources, to quote.
	- Mention something from this [paper]([https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjAla-i0OqDAxVwPEQIHSZvBVoQFnoECAQQAw&url=https%3A%2F%2Fpages.cs.wisc.edu%2F~swift%2Fpapers%2Fvee20-isolation.pdf&usg=AOvVaw2ipsex_cG1D0dhngGu3s8K&opi=89978449](https://www.google.com/url?q=https://www.google.com/url?sa%3Dt%26rct%3Dj%26q%3D%26esrc%3Ds%26source%3Dweb%26cd%3D%26cad%3Drja%26uact%3D8%26ved%3D2ahUKEwjAla-i0OqDAxVwPEQIHSZvBVoQFnoECAQQAw%26url%3Dhttps%253A%252F%252Fpages.cs.wisc.edu%252F~swift%252Fpapers%252Fvee20-isolation.pdf%26usg%3DAOvVaw2ipsex_cG1D0dhngGu3s8K%26opi%3D89978449&sa=D&source=docs&ust=1705712062785727&usg=AOvVaw1LxsMXQLqSKqD7wRFiLHzD))



### Outcome
- describe the outcomes relative to their research contribution in providing a novel solution to the problem
	- Putting together a test machine, that will run a sandboxed runtime container within a MicroVM, and loading it with software to test, as well as a few intentional, well known vulnerabilties for us to test it's ability in containing a container escape.
- expected deliverables from the research project, in terms of the final paper, a software product or similar outcome.
	- Final paper. 
	- We'll setup a sandboxed runtime inside of a microVM, test it, and compare those results with an average container
	- We can try different sandboxed runtime technologies, or other microVMs
	- We can ask members from the CISO club to run their software on our container, and see if it runs the same (I want to see Aldo run something on rust), if it's slower, the same.
		- We have classmates with programs written in several languages that could try this out
	- Report if it succeeds, fails, and if there's any specific countermeasures that failed. 
	- Anything else?????
	













As I continue my education in CSUSB, I developed an interest in the are of purple teaming. Although I don't have any personal experience

(4) I have studied Cyber Security for over five years. Before coming to CSUSB, I received my associate's degree in Cyber Security from Fullerton College. while I was there, I learned several areas of IT, including network security, programming, Windows Server, Linux, Virtual machines, Incident response, and more. Between studying for my classes, I obtained my CompTIA A+ and Network+.

In the modern world of software development, containerization is an important tool that is used today for its efficiency, reliability, and security. It offers many features to consumers and developers, but it also has a set of major risks such as Images, Registry, Orchestration, Host OS, and Containers. For these reasons, a cyber security expert, needs to be well rounded in the areas of containerization that need to protection, and understand what one can do to lessen the risk and impact of these possible vulnerabilities. As a group, we’re interested in studying the well known CVEs that are found in containers, and understand how they they work, and study the impact of these vulnerabilities. Then we will look into

(4)    Description of students skill, knowledge, and abilities
1. Five years studying cyber security
2. CompTIA A+ and Network+
3. Virtual machines, programming
4. Network security
6. CISO club? CMP?


1. Interest in learning vulnerability assessments.
2.  Recognizing the importance of this technology, how widely used it is, and how important it is to harden it. (falls into his/her interest)
3. Currently learning penetration testing. (how it is tied with his/her research or practical work.)
4. Wanting to learn how unique the attack surface is for containers.
5. Wanting to understand how to harden these areas
6. Wanting to test current security practices, and see how well they work.
7.  Helping in the advancement of securing this technology?

This project interests me for several reasons. What's always drawn my interest in the field of cyber security, is understanding why technology can be hacked, and how to develop a solution to protect it from abuse. I think it's interesting how this a problem that needs to be addressed in all fields of IT, especially with new emerging technologies like cloud computing and containerization

I recognize the importance of containerization and it's growing popularity, and after spending time learning more about it's unique attack surface, the different methods experts are using to make it more secure, I became more interested and curious about the technology. 

the value it provides to it’s organization, and the importance of having this information well protected. I see the project as an opportunity to learn more about vulnerability assessment, networking, and how to make containers more secure. 

As a student, I want to better understand and develop skills in vulnerability assessment, and understanding how to apply proper security hardening tactics. I want to gain insight, in what it takes to properly setup and configure a secure container. 

That would contribute to the development of secure containerization. 

During my academic career working and studying in IT, I developed an interest in networking. I've taken network security courses, passed the CompTIA Network+ exam, and gained technical experience troubleshooting network issues for security cameras. I'm fascinated with how devices can communicate securely with each other, and It's a field that I enjoy learning more about. I am new to the topic of Quantum Cryptography, but after studying it more Alexander, I learned about the potential of this technology, along with it's potential risk, and I believe the project we have planned for this problem will be an exciting opportunity to explore the effects of quantum cryptography. From a networking perspective, I'm interesting in studying the details of quantum cryptography to get an insight in what the future of networking could be, and the methods necessary to protect it.

What's always drawn my interest in the field of cyber security, is understanding why technology can be hacked, and how to develop a solution to protect it from abuse. One of my career goals is to someday become a SOC analyst, and for this reason, I've focused my studying in the field of ethical hacking, vulnerability assessment, and forensics.  Although I'm somewhat new to this field in particular, I believe I have the foundational IT knowledege required to be an effective member of this project. I'm interested in learning the cyber pyschology behind the hacker, and develop my skills in finding left over artifacts. I think threat detecting software is an interesting technology that I'd enjoy researching at a deeper level to help improve TTP detection analytics. 


This project aims to further evaluate the security of popular container runtimes including Docker and CRI-O. A systematic analysis of known vulnerabilities will shed light on the severity of runtime weaknesses and whether enhancements like sandboxed runtimes and microVMs provide sufficient remediation. Testing different configurations and access controls can uncover remaining risks from misconfiguration. Comparing multiple runtime architectures will also highlight security benefits and deficits of each unique approach. Beyond just vulnerability analysis, the project goals include developing proactive solutions for hardening runtimes against known and zero-day threats. Additionally, techniques to detect compromise after the fact will aid incident response. Meeting these goals will require expertise in areas like vulnerability research, exploitation, mitigation, reverse engineering, and container internals.