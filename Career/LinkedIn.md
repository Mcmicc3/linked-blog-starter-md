
# 2025

Continuing my three post series. Fast forward a year, here is a review of what I was up to in the year of 2025.

This is the year where I was able to participate in my first real cybersecurity team. More than capture  the flag, we were actively setting up and defending servers on a network. What made it even more exciting, was the fact that it was only the second time that our University had competed in this specific regional competition, and we won first place. I can not explain the significance this competition had on me, in terms of understanding the skills needed to setup services, maintain them, defend them, and fullfill tasks while actively being attacked by hackers.

After placing first, NCAE was nice enough to invite us over to compete in Florida for the regional competition, and although we didn't win, the experience had a tremendous impact in my life, and the direction I wanted to take my cyber career.

While preparing for the competition, I was participating in a capstone project called the NAVSEA Enterprise Project. For our Enterprise Network Security course, we were given the task of creating a network from a map that was provided by members of NAVSEA. 
* I'm the not the best at explaining this, so here's a post a teammate of mine made regarding the network: https://www.linkedin.com/in/mikegonzo/details/projects/
* https://www.linkedin.com/posts/mikegonzo_excited-to-share-a-recent-cybersecurity-project-activity-7337181688466198528-1OhU/?utm_source=share&utm_medium=member_desktop&rcm=ACoAABXFXxcB3IBpyj6pAcXZgGVZ92Yj24CMRgI

After successfully creating and presenting our project, I was then honored with being the first in my family to obtain a bachelors degree. (More filler words to express how proud and happy I am to accomplish this, and how eager I am to use the skills I've learned to serve my community.)

"I don't know what to say for this part, essentially, I applied for SFS, but because Trump kept threatening to defund the department of Education, they cancelled SFS for a year. I was then provided an alternative offer by my University, and was awarded the WITH Cyber Scholarship. Because of that scholarship, I had the honor of serving in the second cohort for the Universities Security Operations Center. That job gave me my first experience in working in cybersecurity, and it taught my Threat Hunting and Incidence Response."

"Somewhere in this paragraph I discuss community involvement and mentorship. here, I mention Defcon, and my committment to serving as a mentor for the CISO club, where I helped lead a group of students form their own NCAE team to compete alongside ours. There's a random picture of me at WiCyS club opener, I was gonna share the link"

I don't really know how to end this post gracefully. 

# 2024


Good news, everyone — I remembered my LinkedIn password!

It's been a while since I've shared what I've been up to here, and three years is certainly to much to talk about all in one post. So, with a new academic year beginning (and my last), I  *thought it would be interesting to share what I have been up to since 2024* thought this would be a good opportunity to catch LinkedIn up on what I've been doing since 2024.

I'll be breaking it into three posts. Starting with 2024...

https://www.youtube.com/watch?v=m1cwrUG2iAk

1. insure
When I joined the CISO Club (Cyber Intel & Security Organization) I met folks who knew they wanted a career in cyber security research, and I thought that was an interesting career choice to make, so I decided to apply myself and take the honors research course at CSUSB, INSuRE. 

I was accepted, and was then assigned to do research in container escape for the NSA. They wanted explore how container escape was possible, and if there were any existing technologies available at the time, or methods that could have prevented an attacker from exploiting the vulnerability. During our research, we learned about runtime software, and the role it plays transcribing system requests between the software and the hardware. We then discovered gVisor, an alternative runtime software, and tested it against known container escape vulnerabilities (The name of the vulnerabilities are in the poster). After creating the environment, we were able to simulate the exploit, and successfully proved that the exploit works on the default runtime software, but failed with gVisor.   

At the time I knew nothing about containerization technology, and that class taught me how to teach myself new topics, set up testing environments, and create detailed research reports. It taught me how to work in groups, and how to work alongside mentors. I am forever thankful for that amazing opportunity, and everything it taught me.

2. Open House
After INSuRE, I thought it would be fun to do research on AI since it was an emerging trend at the time, and it also to be around the same time Dr. Nestler, a director of CSUSB Center for Cyber & AI AND OpenAI Cyber pentester, wanted to start his own AI research group on campus. I joined it, and that's how I was given the idea of installing an AI project onto the clubs computer. Essentially, this happened when AI agents were brand new. We downloaded a public project called "Praisen AI". It was installed on a club computer and tied to a phone number (I forget which software technologies allowed me to do this, I can look it up), and would respond on the phone when I call it. The idea is that I give the AI instructions ("Add this to my calendar"), and it would then deploy AI agents to complete the task. When you run the software, you can also see the conversation on the computer as well as running code. (**It's important to understand that we never configured the AI to deploy AI agents, either because it wasn't available at the time, or we couldn't complete the task. The important thing was to show people how it's possible to call AI, and give ideas on what this technology can do.**)


---
## First Draft
Good news everyone, I remembered my LinkedIn password!

It's been a while since I've shared what I've been up to here, and three years is certainly to much to talk about all in one post. So, with a new academic year beginning (and my last), I thought it would be interesting to share what I have been up to and catch up on some of the experiences that have shaped me over the last few years. With that being said, I’m going to break this into three posts, starting with 2024: The year I moved to campus and became involved in my academic cyber security journey~~: the year I really started getting involved in cybersecurity.~~

~~One of the first experiences that pushed me outside of my comfort zone was **INSuRE**, CSUSB’s honors cybersecurity research course.~~

~~After joining the Cyber Intelligence & Security Organization (CISO), I met students who already knew they wanted careers in cybersecurity research. I had never seriously considered research as a career path before, but hearing about their interests made me curious enough to give it a try.~~ 

When I joined the CISO Club (Cyber Intel & Security Organization) I met folks who knew they wanted a career in cyber security research, and at the time I hadn't considered it as a career choice, so I decided to apply myself and take the honors research course at CSUSB, INSuRE. 

I applied to INSuRE, was accepted, and joined a team working on a research problem provided by mentors affiliated with the NSA: **container escape vulnerabilities**. Which was exciting because at the time, I knew almost nothing about containers.


~~Our team had to learn how container runtimes worked, build isolated testing environments, recreate known vulnerabilities, and compare how different runtimes responded to them. We tested containerd and gVisor against CVE-2024-21626 and CVE-2024-23652, two container escape vulnerabilities affecting different parts of the container ecosystem.~~

~~One of our most interesting findings was that gVisor successfully mitigated the runc-based CVE-2024-21626 exploit, while the BuildKit-based CVE-2024-23652 attack could still succeed because it occurred before the container runtime could provide protection.~~


INSuRE taught me how to approach topics that I knew nothing about. By the end of the program, I learned how to teach myself unfamiliar technologies, build controlled testing environments, document research, work collaboratively with a team, and communicate with faculty and government mentors. I’m incredibly grateful that I had the opportunity to participate in the program and work on a problem connected to the NSA.

That experience also made me much more comfortable exploring technologies outside of what I already knew.

Later that year, I became interested in the rapid growth of generative AI and joined an AI research group on campus. For our cybersecurity club’s annual Open House, I presented an AI project I was experimenting with named **PraisonAI**, an early AI-agent framework that could integrate with a phone system.

We configured a demonstration that allowed visitors to call a phone number, speak with the AI, and watch the interaction appear on the computer in real time. The larger idea behind the project was to demonstrate how AI agents could eventually receive instructions and interact with external tools to perform tasks.

We never reached the point of having the system autonomously deploy agents and complete those tasks during our demonstration, but that was part of the learning experience. The goal was to give visitors a hands-on look at where AI technology appeared to be heading and start conversations about what might soon be possible.

Lastly, 2024 also marked the year I became elected to serve as **Treasurer of CISO**.

I joined the CISO club looking to meet other highly motivated and passionate cyber students, and in the end, it ended up being one of the most highly influential organizations of my life.~~When I first joined the club, I was simply looking for a place where I could meet other people interested in cybersecurity~~. Being given the opportunity to help lead the organization meant a lot to me. It gave me a chance to contribute back to the same community that had introduced me to research, competitions, projects, and many of the people who helped shape my college experience.

2024 was the year I became involved in my academics, and my community, and it later provided me with opportunities that I will forever be thankful for, and I look forward to sharing more of those experiences in my 2025 post!

~~Looking back, 2024 was less about having everything figured out and more about saying yes to opportunities I didn't initially feel prepared for.~~

~~That turned out to be a pretty good strategy.~~

**A few moments from 2024:**

1. Our INSuRE research poster, _Keep It Contained! Detecting Container Escape_
    
2. Demonstrating our AI project during the CSUSB Center for Cyber & AI Open House
    
3. Joining the CISO executive board as Treasurer
    

**Related:**

CSUSB Center for Cyber & AI — 2024 Annual Open House  
[https://www.csusb.edu/inside/article/584671/csusbs-center-cyber-ai-hosts-annual-open-house](https://www.csusb.edu/inside/article/584671/csusbs-center-cyber-ai-hosts-annual-open-house)



---


**INSuRE:** what made you join, what the NSA-sponsored problem was, what you personally worked on, what surprised you or what you learned.

**Open House:** how this differed from simply being a club member, what you presented, what it was like explaining your project to visitors.

**Treasurer:** why you decided to run/accept the position, what the club meant to you, and what you hoped to contribute.

Then at the bottom:

**Photos**

1. INSuRE research poster — _Keep It Contained! Detecting Container Escape_
2. Presenting at the annual cybersecurity Open House
3. Joining the CISO executive board as Treasurer

**Related**

- Open House / CSUSB Center for Cyber and AI feature — [link]


---
## Second Draft

Good news everyone, I remembered my LinkedIn password!

It’s been a while since I’ve shared what I’ve been up to here, and three years is certainly too much to fit into one post. So, with a new academic year beginning (and my last), I thought this would be a good opportunity to catch up on some of the experiences that have shaped me over the last few years.

I’m going to break it into three posts, starting with **2024: the year I moved to campus and really became involved in my academic cybersecurity journey.**

When I joined the CISO Club (Cyber Intelligence & Security Organization), I met people who already knew they wanted careers in cybersecurity research. At the time, I had never really considered research as a career path, so I decided to challenge myself and apply to CSUSB’s honors research course, INSuRE.

I was accepted and joined a team working on a research problem provided by mentors affiliated with the NSA: **container escape vulnerabilities**. It was exciting, but also a little intimidating, because at the time I knew almost nothing about containers except for the fact that the world runs on them.

By the end of the program, I had learned how to teach myself unfamiliar technologies, build controlled testing environments, document research, work collaboratively with a team, present our findings, and communicate with faculty and government mentors. I’m incredibly grateful for the opportunity and for everything the experience taught me.

That experience also made me much more comfortable exploring technologies outside of what I already knew.

Later that year, I became interested in the rapid growth of generative AI and joined an AI research group on campus. For our cybersecurity club’s annual Open House, I presented a project I had been experimenting with called **PraisonAI**, an early AI-agent framework that could integrate with a phone system.

We configured a demonstration where visitors could call a phone number, speak with the AI, and watch the interaction appear on the computer in real time. We never reached the point of having the system autonomously deploy agents and complete tasks, but that was part of the learning experience. The goal was to give visitors a hands-on look at where AI technology was heading and start conversations about what might soon be possible.

2024 was also the year I was elected to serve as **Treasurer of CISO**.

I originally joined CISO hoping to meet other motivated and passionate cybersecurity students, and it ended up becoming one of the most influential organizations of my college experience. Serving on the executive board gave me an opportunity to contribute back to the same community that had introduced me to research, competitions, projects, and many of the people who shaped my time at CSUSB.

One of the ways I gave back was by volunteering every Friday to teach an introductory **Active Directory workshop**. We covered topics like domains, Organizational Units, Group Policy, and the fundamentals of managing an Active Directory environment. Being able to share what I had learned with other students was one of the first times I really experienced how rewarding teaching and mentorship could be.

Looking back, 2024 was the year I became much more involved in both my academics and my cybersecurity community. Those experiences eventually opened the door to opportunities I’ll always be thankful for, and I look forward to sharing more about those experiences in my 2025 post!

**A few moments from 2024:**

1. INSuRE research poster — _Keep It Contained! Detecting Container Escape_
2. Demonstrating PraisonAI during the CSUSB Center for Cyber & AI Open House
3. Joining the CISO executive board as Treasurer


**Related:**

CSUSB Center for Cyber & AI — 2024 Annual Open House  
[https://www.csusb.edu/inside/article/584671/csusbs-center-cyber-ai-hosts-annual-open-house](https://www.csusb.edu/inside/article/584671/csusbs-center-cyber-ai-hosts-annual-open-house)


I also volunteered every Friday at the CISO club to teach an introductory **Active Directory workshop** covering domains, OUs, Group Policy, and other fundamentals. Teaching other students was one of the first times I experienced how rewarding mentorship could be.

**Starting with 2024**: the year I moved to campus and really became involved in my academic cybersecurity journey.

In 2024, I was also elected **Treasurer of CISO**.

Later that year, I joined an AI research group and experimented with **PraisonAI**. For our annual Cyber & AI Open House, we created a demo where visitors could call a phone number, speak with the AI, and watch the interaction on a computer in real time. We never reached the point of having the system autonomously deploy agents and complete tasks, but that was part of the learning experience. The goal was to give visitors a hands-on look at where AI technology was heading and start conversations about what might soon be possible.

Looking back, 2024 was the year I became much more involved in both my academics and my cybersecurity community. Those experiences eventually opened the door to opportunities I’ll always be thankful for, and I look forward to sharing more about those experiences in my **2025 post**!

**Related**:

---
## Third Draft

Good news everyone, I remembered my LinkedIn password!

It’s been a while since I’ve shared what I’ve been up to, and three years is a little too much for one post. With my final academic year beginning, I thought it was time to catch LinkedIn up.

Starting with 2024: the year I moved to campus and really became involved in my academic cybersecurity journey.

After joining the CISO Club (Cyber Intelligence & Security Organization), I met students interested in cybersecurity research. I had never seriously considered research myself, so I challenged myself to apply to CSUSB’s honors research course, INSuRE.

I was accepted and joined a team researching container escape vulnerabilities for mentors affiliated with the NSA. It was exciting, but also intimidating, because I knew almost nothing about containers except that the world runs on them.

By the end of the program, I had learned how to teach myself unfamiliar technologies, build testing environments, document and present research, work with a team, and communicate with faculty and government mentors. I’m incredibly grateful for the opportunity and everything it taught me.

Later that year, I joined an AI research group and experimented with PraisonAI. For our annual Cyber & AI Open House, we created a demo where visitors could call a phone number, speak with the AI, and watch the interaction on a computer in real time. While we never reached full autonomous task execution, it was a great opportunity to explore emerging AI technology and demonstrate its potential.

2024 was also the year I was elected Treasurer of CISO.

CISO became one of the most influential parts of my college experience, and serving on the executive board gave me an opportunity to give back to the community that introduced me to research, competitions, projects, and many of the people who shaped my time at CSUSB.

I also volunteered every Friday to teach an introductory Active Directory workshop covering domains, OUs, Group Policy, and other fundamentals. Teaching other students was one of the first times I experienced how rewarding mentorship could be.

Looking back, 2024 was the year I became much more involved in both my academics and my cybersecurity community. I’m excited to share where those experiences led me in 2025!

Related:  
CSUSB Center for Cyber & AI — 2024 Annual Open House  
[https://www.csusb.edu/inside/article/584671/csusbs-center-cyber-ai-hosts-annual-open-house](https://www.csusb.edu/inside/article/584671/csusbs-center-cyber-ai-hosts-annual-open-house)