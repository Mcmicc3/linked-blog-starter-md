
## Speech

1. ***(Update from CISA)*** Important news related to the Cybersecurity and Infrastructure Security Agency (CISA). Starting September 28, 2026, CISA is discontinuing its weekly Vulnerability Bulletin.

2. ***(Explain the Bulletin)*** For years, this bulletin has provided a weekly roundup of newly reported vulnerabilities. It included information such as affected products, CVE numbers, severity ratings, CVSS scores, descriptions of vulnerabilities, and available patches. *The reason CISA is making this change is the more important part of the story.*

3. ***(Explain the new initiative)*** This is part of CISAs broader transition away from vulnerability management that is based primarily on severity and toward vulnerability management based on actual risk.
	1. Back in June of 2026, CISA released Binding Operational Directive 26-04, called "Prioritizing Security Updates Based on Risk." That directive established a new vulnerability-management model for federal civilian agencies.
	2. Instead of treating every vulnerability the same, or simply looking at a CVSS score and patching the highest numbers first, CISA wants administrators to consider the actual circumstances surrounding that vulnerability.

4.  ***(Important questions CISA asks)*** CISA identifies several important questions.
	1. Is the vulnerable system exposed to the Internet?
	2. Is the vulnerability already being exploited by attackers?
	3. Can exploitation of the vulnerability be automated?
	4. And if an attacker successfully exploits it, how much control would they actually gain over the system?

5. ***(Explain the difference in through process)*** 
	1. This a very different way of thinking about vulnerabilities. Right now, administrators are running vulnerability scans and are seeing hundreds, sometimes thousands of vulnerabilities in their network. 
	2. They might have one vulnerability with an extremely high CVSS score on a system that is isolated, difficult for an attacker to reach, and for CISA currently sees no evidence of exploitation
	3. Meanwhile, another vulnerability might have a lower severity score, but it exists on an Internet-facing server and attackers are actively exploiting that vulnerability in the real world.
	4. If the administrator only looked at severity scores, they might focus all of their attention in patching the high CVSS vulnerability first, but if they looked at vulnerability management from a risk-based approach they would more likely see that the second vulnerability deserve their immediate attention first.
	   
6. ***(Introduce KEV)*** This is where CISA's Known Exploited Vulnerabilities Catalog, or KEV Catalog, becomes especially important. Introduced under binding Operational Directive 22-01, in 2021, The KEV Catalog contains vulnerabilities for which there is evidence of active exploitation. In other words, these aren't just theoretical security problems. Attackers are actually using them.
	1. So instead of asking administrators to work their way through a massive list of vulnerabilities from highest CVSS score to lowest, CISA is emphasizing the need to identify which vulnerabilities present the greatest real-world threat to the systems an organization actually operates.

7. ***(Conclusion)*** What this means is that we shouldn't depend entirely on one number like a CVSS score to make our vulnerabilitiy managmeent decisions.
	1. **To be clear**, CVSS is still useful. CVE information is still useful. And CISA isn't getting rid of either one.
	2. What is changing is how that information should be used.
	3. After September 28, CISA recommends that defenders rely on resources such as the KEV catalog, CISA's cybersecurity alerts and advisories, CVE.org, and security advisories directly from software and hardware vendors.

*focus more on which vulnerabilities pose the greatest actual risk to their own environments.*

## Related Links
[Dark Reading — CISA Ditches Weekly Vulnerability Roundups for Risk-Based Focus](https://www.darkreading.com/cyber-risk/cisa-ditches-weekly-vuln-roundups-risk-based-focus?utm_source=chatgpt.com)

[CISA announcement — BOD 26-04: Prioritizing Security Updates Based on Risk](https://content.govdelivery.com/accounts/USDHSCISA/bulletins/41b445a?utm_source=chatgpt.com)

[SecurityWeek — CISA Retires Weekly Vulnerability Bulletin in Risk-Based Pivot](https://www.securityweek.com/cisa-retires-weekly-vulnerability-bulletin-in-risk-based-pivot/?utm_source=chatgpt.com)

---
## Draft 

For example, imagine that I am an administrator and my vulnerability scanner gives me hundreds or even thousands of findings.

I might have one vulnerability with an extremely high CVSS score on a system that is isolated, difficult for an attacker to reach, and for which there is currently no evidence of exploitation.

Meanwhile, another vulnerability might have a lower severity score, but it exists on an Internet-facing server and attackers are actively exploiting that vulnerability in the real world.

If I only looked at the severity scores, I might patch the first vulnerability before the second.

A risk-based approach would tell me that the second vulnerability may actually deserve my immediate attention.

And that This is where CISA's Known Exploited Vulnerabilities Catalog, or KEV Catalog, becomes especially important.

The KEV Catalog contains vulnerabilities for which there is evidence of active exploitation. In other words, these aren't just theoretical security problems. Attackers are actually using them.

So instead of asking administrators to work their way through a massive list of vulnerabilities from highest CVSS score to lowest, CISA is emphasizing the need to identify which vulnerabilities present the greatest real-world threat to the systems an organization actually operates.

For us as IT administrators, I think there is an important lesson here.

Our responsibility isn't simply to install every patch as quickly as possible.

We have limited maintenance windows. We have systems that can't always be rebooted immediately. We have compatibility concerns, business requirements, limited staff, and potentially thousands of vulnerabilities to investigate.

That means vulnerability management is also a prioritization problem.

We need to know what assets we have, which ones are exposed to the Internet, how important those systems are to the organization, what vulnerabilities affect them, and whether attackers are actively targeting those vulnerabilities.



So, if I were managing an organization's infrastructure, one of my takeaways from this news would be to review how our vulnerability-management process actually works.

Are we just sorting vulnerabilities from critical to low?

Or are we asking which vulnerabilities affect our Internet-facing systems?

Which affect our most important assets?

Which have working exploits?

Which are currently being exploited?

And which ones could give an attacker significant control over our environment?

I think that distinction between severity and risk is the most important part of this story.

CISA isn't saying severity doesn't matter. It is saying that severity by itself isn't enough.

As future cybersecurity professionals, we're going to have more vulnerability information available to us than ever before. The challenge isn't simply finding vulnerabilities anymore.

The challenge is determining which ones matter most and acting on those before an attacker does.


## Notes
Yes. I found enough corroborating information to say that the Dark Reading article is accurately describing a **real and broader change in CISA’s vulnerability-management strategy**, rather than simply a change to one newsletter.

### What I verified

Dark Reading reported on September 17, 2026 that CISA will discontinue its **weekly Vulnerability Bulletin on September 28, 2026**. That bulletin has historically aggregated newly disclosed vulnerabilities and included information such as the CVE, affected product, CVSS score, severity, and available patches. Importantly, the bulletin itself generally **did not tell administrators which vulnerabilities they should remediate first**.

The September 28 change is real, but the larger shift actually began earlier. On **June 10, 2026**, CISA issued **Binding Operational Directive 26-04: Prioritizing Security Updates Based on Risk**. CISA's announcement explicitly says federal agencies should prioritize rapid remediation of high-risk vulnerabilities while allowing lower-risk vulnerabilities to be deferred.

That distinction is important for your speech. I wouldn't say that CISA suddenly changes its vulnerability-management philosophy on September 28. A more accurate way to explain it is:

> **CISA began formalizing its risk-based vulnerability-management strategy with BOD 26-04 in June 2026, and retiring the weekly vulnerability bulletin on September 28 is another step in that broader transition.**

The new framework looks beyond a vulnerability's numerical severity. CISA identifies **four major factors** for determining remediation urgency: whether the affected asset is publicly exposed, whether the vulnerability is in CISA's **Known Exploited Vulnerabilities (KEV) Catalog**, whether exploitation can be automated, and the technical impact—essentially, how much control an attacker gets if exploitation succeeds.

That's probably the most important concept for your audience:

**Severity asks, "How bad could this vulnerability theoretically be?"**

**Risk asks, "How dangerous is this vulnerability to _our organization, right now_?"**

CISA is not eliminating CVEs or saying that CVSS is useless. Newly recorded vulnerabilities will still be available through CVE.org. Instead, CISA is directing defenders toward the **KEV Catalog, CISA cybersecurity alerts and advisories, and vendor security advisories** for actionable information.

There's another useful nuance for your class: BOD 26-04 is legally binding on covered **Federal Civilian Executive Branch agencies**, not every private organization or IT department. However, CISA explicitly encourages other organizations to adopt risk-based vulnerability management and prioritize KEV vulnerabilities as well.

That gives you a strong IT-administrator angle because this isn't really a story about CISA discontinuing an email. **It's a story about how vulnerability management itself is changing.**

Here is a draft I'd recommend using as the foundation for your speech. I've written it to sound like something you'd actually say aloud rather than an essay you'd read.

CISA's Shift Toward Risk-Based Vulnerability Management — Speech Draft

I deliberately built the speech around a **"severity versus risk"** theme because I think that gives you something much more interesting to explain than simply reporting that CISA discontinued a bulletin.

There's also a very good visual you could put on a slide or whiteboard:

**Old mindset:**  
`CVSS → Critical → Patch first`

**Risk-based mindset:**  
`Vulnerability + Asset Exposure + Active Exploitation + Exploitability + Impact → Priority`

And one point I'd especially emphasize verbally is that **September 28 is the date the weekly bulletin ends, not the date the entire risk-based philosophy suddenly begins**. The major formal shift came with BOD 26-04 on **June 10, 2026**; retiring the bulletin is the latest visible consequence of that change.

For your references, I'd use the original **Dark Reading article**, CISA's **June 10 BOD 26-04 announcement/directive**, and the independent **SecurityWeek September 17 report**. That gives you a news source, the primary government source underlying the policy, and independent confirmation of the September announcement.