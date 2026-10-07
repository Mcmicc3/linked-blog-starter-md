Two-Part Question:

Describe key concerns and recommendations practical to EA Landscapes? Discuss how Outlines can estimate over all business impact and value in the initiative proposal process?


Hello Astou,

I like your point about the challenges organizations face when their IT Landscapes become fragmented or difficult to understand. As you mentioned, dependencies, legacy systems, isolated data, and limited visibility can make it difficult for executives to understand how changes to one application might affect the rest of the organization. draft3 This is especially important because Landscapes are intended to show relationships between IT assets, including applications, databases, infrastructure, and the business capabilities they support. Chapters12&13 A centralized Landscape could therefore provide more than documentation; it could help reveal dependencies that might otherwise remain unnoticed until a change causes an operational problem.

Your discussion of Outlines also shows how Enterprise Architecture can connect these technical considerations to business decisions. Outlines allow organizations to evaluate expected business value, costs, risks, dependencies, and capability improvements before committing to an initiative. draft3

I think this becomes particularly valuable when dealing with legacy technology. An organization might recognize through its Landscape that an aging system creates technical or security concerns, but that alone does not necessarily justify replacing it. An Outline can help determine whether replacement provides enough business value to justify the cost and disruption. In this way, Landscapes help organizations understand **where change may be necessary**, while Outlines help leadership decide **whether a particular change is worth investing in**.


---


Hello Joel,

I agree with your point that the usefulness of a Landscape depends heavily on keeping its scope manageable. Attempting to document every system and technical detail can consume significant resources while making the artifact increasingly difficult to maintain. As you mentioned, this becomes particularly problematic because IT environments constantly change, meaning outdated Landscapes can quickly lose their value for planning. draft2 This reinforces the importance of treating Landscapes as living artifacts rather than documentation projects that are completed once and forgotten. Kotusev similarly explains that Landscapes should evolve alongside the IT environment and be updated as changes occur. Chapters12&13

I also thought your banking example demonstrated an important connection between architecture and cybersecurity. Consolidating overlapping SIEM and analytics platforms would not only reduce costs but could also simplify the security environment by reducing the number of systems that administrators must maintain and monitor. draft2

Your discussion of Outlines extends this idea into executive decision-making. Because Outlines summarize benefits, costs, timelines, risks, and alternatives, they allow leadership to evaluate an initiative before committing substantial resources. draft2 Together, these artifacts provide complementary perspectives: Landscapes establish **what currently exists**, while Outlines help determine **whether a proposed change is worth pursuing**.


---


**Landscapes and Outlines in Enterprise Architecture Practice**

Landscapes are IT-focused artifacts that document the current state of an organization's IT environment, including its systems, their connections, and their lifecycle status (Kotusev, 2021). Because they are mainly facts rather than decisions, architects can build them by collecting information from support teams, project documentation, and configuration management databases. Their value lies in helping architects rationalize the landscape, reuse existing assets, reduce duplication, and decommission legacy systems.

Kotusev (2021) identifies two main concerns with Landscapes. The first is misusing them for strategic planning. In most organizations, business executives set the long-term direction and control the budget, so future plans should appear in Landscapes only after they have been approved in business-focused artifacts such as Visions or Outlines. Creating IT target states ahead of business direction amounts to IT trying to lead the business, which is risky. The second concern is excessive detail. Fine-grained Landscape Diagrams and Inventories are hard to keep current, so Kotusev recommends focusing on architecturally significant, slowly changing details. An accurate high-level Landscape is more useful than a detailed but outdated one.

Outlines, by contrast, are business-focused artifacts that describe individual IT initiatives in language executives understand. Kotusev (2021) characterizes them as benefit, time, and price tags for proposed investments. Architects develop them with business sponsors during the initiation step, alongside the business case. The process often moves from an Initiative Proposal, which presents an early idea and rough estimates to secure seed funding or reject weak ideas, to an Options Assessment that compares alternatives, and finally to a Solution Overview. Throughout, Outlines estimate business impact by describing process changes, expected tactical and strategic benefits, CAPEX and OPEX costs, timelines, and risks. They also show strategic alignment through Principles, capability footprints, or Roadmaps. Their level of detail should be just enough to support the investment decision. After implementation, archived Outlines can support benefit reviews that check whether the promised value was achieved, which improves the efficiency and ROI of IT investments.

**Reference**
Cap
Kotusev, S. (2021). _The practice of enterprise architecture: A modern approach to business and IT alignment_ (2nd ed.). SK Publishing.