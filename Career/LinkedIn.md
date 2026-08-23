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

It's been a while since I've shared what I've been up to here, and three years is certainly to much to talk about all in one post. So, with a new academic year beginning (and my last), I thought it would be interesting to share what I have been up to and catch up on some of the experiences that have shaped me over the last few years. With that being said, I’m going to break this into three posts, starting with 2024: the year I really started getting involved in cybersecurity.

~~One of the first experiences that pushed me outside of my comfort zone was **INSuRE**, CSUSB’s honors cybersecurity research course.~~

~~After joining the Cyber Intelligence & Security Organization (CISO), I met students who already knew they wanted careers in cybersecurity research. I had never seriously considered research as a career path before, but hearing about their interests made me curious enough to give it a try.~~ 

When I joined the CISO Club (Cyber Intel & Security Organization) I met folks who knew they wanted a career in cyber security research, and I thought that was an interesting career choice to make, so I decided to apply myself and take the honors research course at CSUSB, INSuRE. 

I applied to INSuRE, was accepted, and joined a team working on a research problem provided by mentors affiliated with the NSA: **container escape vulnerabilities**.

At the time, I knew almost nothing about containers.

~~Our team had to learn how container runtimes worked, build isolated testing environments, recreate known vulnerabilities, and compare how different runtimes responded to them. We tested containerd and gVisor against CVE-2024-21626 and CVE-2024-23652, two container escape vulnerabilities affecting different parts of the container ecosystem.~~

~~One of our most interesting findings was that gVisor successfully mitigated the runc-based CVE-2024-21626 exploit, while the BuildKit-based CVE-2024-23652 attack could still succeed because it occurred before the container runtime could provide protection.~~

More important than any single technical result, though, INSuRE taught me how to approach something I knew nothing about.

I learned how to teach myself unfamiliar technologies, build controlled testing environments, document research, work collaboratively with a team, and communicate with faculty and government mentors. I’m incredibly grateful that I had the opportunity to participate in the program and work on a problem connected to the NSA.

That experience also made me much more comfortable exploring technologies outside of what I already knew.

Later that year, I became interested in the rapid growth of generative AI and joined an AI research group on campus. For our cybersecurity club’s annual Open House, I experimented with **PraisonAI**, an early AI-agent framework that could integrate with a phone system.

We configured a demonstration that allowed visitors to call a phone number, speak with the AI, and watch the interaction appear on the computer in real time. The larger idea behind the project was to demonstrate how AI agents could eventually receive instructions and interact with external tools to perform tasks.

We never reached the point of having the system autonomously deploy agents and complete those tasks during our demonstration, but that was part of the learning experience. The goal was to give visitors a hands-on look at where AI technology appeared to be heading and start conversations about what might soon be possible.

2024 also marked another important step for me: I was elected to serve as **Treasurer of CISO**.

When I first joined the club, I was simply looking for a place where I could meet other people interested in cybersecurity. Being given the opportunity to help lead the organization meant a lot to me. It gave me a chance to contribute back to the same community that had introduced me to research, competitions, projects, and many of the people who helped shape my college experience.

Looking back, 2024 was less about having everything figured out and more about saying yes to opportunities I didn't initially feel prepared for.

That turned out to be a pretty good strategy.

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