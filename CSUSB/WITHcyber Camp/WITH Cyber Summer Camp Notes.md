
# Orientation

One on One meetings for the week of the 27th

We can get started now or wait until UAC gets a hold of us.

Might be $1500 in total, could be more

On the Thursday, the week of the camp, Amy will help us with the submission process. Normally we'll submit 40 hours, and the week prior is 40 hours as well. 
* 2 weeks, 80 hours
* If anything changes Amy will let us know

Arcky changed the curriculmn for this year to test the waters for next years vision.
The change this year is that they're adding AI to everything

We have to be there at 8 AM, and we leave at 4:30 PM, BUT, we usually talk at the end to see what worked and what didn't


#### Incident Response
Guided activity
* You do's
* Three tired challenges where they applied the knowledge

Starts with covering the work role first, presenting that. Then you pivot to the phases of Incident responses
* Wants to work a hand off between the IR and other activities.

# 1:1

There's gonna be a theme:
* We do (something I guide them through on PCs). 
	* They'll follow along,
* You do activity
	* Tiered, easy win, and provide tips. We create flags
	* Tier 2, they'll be given a hint, more difficult, builds off of 1
	* Tier 3, will be difficult and not all students will solve it. Forces htem to analytically think. Have a true winner. **No Guidance**

They'll interact with an artificat. All artifiact will be given to ivonne, she'll take them and figure out how to unfold them from an incident response perspective. 

Defense in cyber:
He wanted to do a handoff, 1 artificat from each session will be handed off over time. 
* We're still trying to find the right artifact
	* PCAP is easy, but we're thinking of what else.

Defense analyst: Focus on SOC analytical perspective, triage events, system logs, they'll be able to deep dive analysis into the system to extract logs and find a piece of the artifact on how they were compromised. Find how the attacker pivoted.
* This is an idea as starting point.


Explain what is defensive security. Identify a basic SOC alert lifecycle. Explain how it escalates. Starts with triaging, then something else 

From there, have the activites make them determine if it was a false or positive flag. They have to learn how to grep and parse data, **or**, we can use a tool for them to expedite. THink of a specific tool to work with. Something I want to learn. 
***Keep thinking of what tool to learn, I suggested jq***
* He used Jira. 
* We have to find an open source tool, 
* Letting them do the analysis,.....**The focus is finding**. 

Mine in session 2 is showing them defense in depth. Ways to inpleemtn security controls. 

they do traige in 1.  Learn how to find the issues. 

2 would be showing them mitigation and security controls in a system. Learn how to resolve them. 

When they get to the comp, they get vulnerable systems, they're applying what they learned from my course.

We could pipe things to a SIEM, but we'd have to customize the files piping to it. 

They'll use mini PCs with proxmox

Snort is really slow when they use target VMs (metasploitable). 

We'll see if Snort has a containerized version. 

In the past, defense analyst used grep and analyzed logs. Parsing the data, and learning to find the threat actor in it. He wants to move away or build on it. 

***We're going to be making our own dataset***

He'll make a breakdown, we can add to it and make adjustments. Once it's done, we make the slidedecks, the activities. Since the mini PCs arent' made yet, we're going to use VMs, kali with proxmox. Once we're done, he's going to install them on a mini PC. 

If I make anything custom, ... Last year, students used AI to make PCAP files, there's a lot of libraries to use a lot of PCAP files. He's willing to do it for me or with me. If there's a new tool I need to learn, let him know, and he'll help make what I need to make so I can learn the tool.

Start with system analysis, then segway how to defend what was shown.

The technical level they'll be at, before it was 30 - 60 students, they're selective to students who have been more technically exposed. It will be too easy for some, good enough for most, and some that need extra help. In the past 60% of students new networking and security+ concepts. A select few new beyond that (3 - 4 students). We'll have about 40% that only understand networking, or very little. 

He'll give us a template to work off of. We start off defense analyst. We explain that, the technical then the lamen terms. We'll use NIST and CISA glossery for definitions. We make up the lamen terms. Basically, we cover both sides. We'll utilize metaphors for them to understand. 

We'll start off with what is a defensive analyst. Then the knowledge skills and abilities pertaining to an analyst. THen we'll go into specific objectives for that work role. Then we make the connection from the objectives to the tools. We're telling a story and guiding them through it. 

The activities guide the core content that we'll be teaching. IF WE'RE teaching an XDR, then first we're going to explain it and show how they use it. Then we do you do challenges. 30% will be us talking and 70% will be them doing. 

---

Debrief everyday. THere'll be five minutes at the end talking with them and giving them a chance to make sure that they learned. He's tieing all of this in, because we're collaborating with cal soap. they're going to make a board game, still technical, utilizing the information that they're learning in each course. THen, during the competition, we'll select one of the five board games, we'll choose to present it. 

Expect to be interviewed so they can use it for their boardgame. 

He's making a folder for us. It will come with a slidedeck and a template. He wants us to make a theme. Nate did Among us, Friday kept that going. There'll be structure to that with the WITHCyber logo, but we can change the color, and make it highschool friendly. Make it intersting. 

Depending on when Erinae gets our equipment, will show how much time we have to test our environment. 


***Do research on tools SIEM/QUERING TOOLS***
Open source. Be mindful that we're working with mini PCs.
We might work within both mini PCs and Cyberlab. 
**preferably locally**

***Session 2 needs to stem from session 1, no sharp turn***
* How are we going to defend from this?
* We segway, and introduce zero trust. Aims to optimize, he's the tiered steps to get to optimization...

This is going to prepare them for the competition. 

We haven't flushed out session 2. He's thinking about making it zero trust, but he wants to cordinate that with Noah. We can implement true zero trust. During the comeptition, it will be partly mini PCs, partly cyberlab. Vulnerable. They'll have time to setup...mini dog park. 

***Last thing, find a theme.***

Don't use docker desktop. 
Learn how to use docker compose
* Make our own YAML file.
	* Deploy a database and a web server. 
If we're containerziing
The we do, could be them making logs, and injection.

We do: Perform an injection
You do: analyze the injection from the siem. 

**We do** is a guided activity following along with me. 
**You do** they're own their own and we give them tips, they'll have objectives. 

If they're doing localy, we can make it start on bootup, or create a bashscript that starts it up. 

Maybe day 2 we teach them how ot make their own tool, gives brandon somethng to do. If we explain docker on day 1, we might be able to explain it day 2.



# May 11th Meeting

***Remind Arcky to send his Discord Username***

Our sessions are up? Excel sheets should come through soon.

Matthew needs to review my session 2. 

Arcky threw a tool, the XDR. 

Board game kit. Kelso will be doing with them. Not technical. 
The teams that will be partnered as a team...
We'll be giving direction and guidance. We're also going to leverage and utilize social media during the evening. The students will look at the post and learn more about the role. The role we're teaching is what we'll be looking at. 

It will be direction based using dark readings and assumed events. By thursday, we'll have a part where they have to present the game to us. Help students get out of their shell. They'll earn points. The plan is to raffle off a laptop. The top teams and studnets get more raffle tickets. Arcky will purchase and donate something for the students. Erinea will check tomorrow to see 

I will most likely collaborate with Noah on a kali machine, Matthew will also be working on it with us. 

We'll have individual ones too. 

He will provide us with a template. He wants us to fill out our own template.

There will be a theme to the camp. 
* 909 (San Bernardino area code)

Each of us will have an artifact we're creating, so that we can pass it off for Ivonne's session 2. 

***Everything needs to be finished by June 1st***
* We will also present to arcky that week (with guests)

That way we're good to go by the 7th


# May 12th Meeting (Center)

Instructions will be posted on Instagram for?? The board game
* If the students find our socials, block them.

I'm getting "Working with minors" training. 
	* Must complete before camp starts

**It will be in our trainings.**
* Should be able to find it in CSU Learn, or my csusb
* HR will assign this. 

We'll be reporting on the week before camp and after camp
* Anything to do with the curriculmn, slides, and prep

#### Camp Schedule
Sunday - Arrival Time - 12:00 PM
	* Students come and check in
	* June 7th   (12 - 1:30 we will be helping Erinea and arcky setup)
Monday - Thursday Arrival Time - 08:00 AM
	* They'll serve breakfast and lunch. They're scheduled lunches.
	* We will have walky talkies, clip pieces, and ear pieces. 
Monday - Thursday Debrief - 4:30 PM, once students leave
	* We will debrief after each day. 

There will be a schedule for everything. Split by groups of 15. There will be two instructors speaking at a time. We need to support other staff members when we're not teaching.

#### Parking
There will be a parking pass (Link) 

##### **We will need to talk to our employers to delegate our hours**
* ***Talk to brian and tell him that I will be gone for a week*** 

#### Dresscode
No shorts, 
Students also have to wear their shirts everyday. 


**DON'T LOSE YOUR BADGE**

**BRING SUNSCREEN**
* They're recommending against the spray one

Sometimes we have to tell them to get off their phones, and that sometimes separating them is necessary.

Bring the giant water bottle

We grab our equipment from room JB 279

Friends aren't allowed to be around the camp
* Only trained staff

Sarah will be doing videos for us.
* Introducing ourselves, talk about our work roles, fun fact.
	* We will be on the WITH cyber instagram (yay....)
	* We will be doing it Thursday and Next Tuesday....
		* 9:30 AM - 5:30 PM

Sarah Ramirez  - Slack - Camp Video 
* Thursday 2:00 PM (JB 279)

#### Timesheets
We do them all together on the last day after camp.
* We're still trying to figure out how many hours we can work....

#### Calsoap
We have to make videos that will be going on Instagram
* It will give instructions to the boardgame
* Students will work on them from Monday - Wednesday
* On Thursday students will present their boardgames

We pickup students after breakfast at 8:45 AM


### ***THE STUDENTS HAVE TO SIGN OFF WITH THEIR PARENTS BEFORE THEY LEAVE CAMP***

