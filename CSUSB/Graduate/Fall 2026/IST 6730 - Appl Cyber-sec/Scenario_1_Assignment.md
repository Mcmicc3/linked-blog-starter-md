# Task

"Implement a new technology"

 Teams will write a business memo to discuss issues on how introduce a new technology to an organization

Focus on the key issues that affect cyber security.

­­Team of 1 or 2

­­4 pages – business memo format (single spaced)

**Due September 10th**


## Draft 2
5. Cybersecurity Risk Assessment

The implementation of Agentic AI introduces cybersecurity threats that must be assessed before deployment and continuously evaluated throughout its operation. Major threats include prompt injection, stolen credentials, malicious or inaccurate inputs, excessive system permissions, vulnerable plugins, APIs, or third-party models, employee misuse, and incorrect or unintended autonomous actions.

These threats create risks to the confidentiality, integrity, and availability of organizational systems and information. Confidentiality may be affected if prompt injection, compromised credentials, excessive permissions, or external integrations allow sensitive organizational information to be disclosed. A compromised account may create additional risk because an attacker could use the agent to retrieve information from multiple authorized sources more efficiently.

Integrity may be affected when malicious inputs, employee misuse, or inaccurate AI reasoning cause the agent to modify data, code, or system configurations incorrectly. These same autonomous capabilities may also affect availability if unintended actions interrupt services or modify systems required for business operations. The potential impact increases as the agent receives broader permissions and greater autonomy.

Risk Level and Organizational Tolerance

The likelihood and impact of these risks will depend on the systems, information, and authority available to the Agentic AI. Low-impact risks involving non-sensitive information or easily reversible actions may fall within organizational tolerance. Risks involving sensitive data, production systems, external integrations, or consequential autonomous actions should be reduced before implementation.

The organization should not accept deployments that allow the agent to independently expose highly sensitive information, make unrestricted changes to critical systems, or perform high-impact actions without oversight. Therefore, Agentic AI should be considered a moderate-to-high cybersecurity risk before security controls are implemented, with deployment proceeding only after higher-impact risks have been reduced to an acceptable level.

6. Security Controls and Countermeasures

The risks identified above should be reduced through layered access, technical, and administrative controls. Least-privilege access should limit the agent to only the information, systems, and functions required for its assigned role. Multi-factor authentication and individual user accounts should protect against stolen credentials while allowing actions to be attributed and reviewed. Access to sensitive information should be restricted, and external-facing agents should operate with greater limitations than those available to authorized internal users.

To reduce risks from prompt injection, inaccurate inputs, and vulnerable external components, untrusted input should be restricted from accessing sensitive functions, and plugins, APIs, and third-party models should require organizational approval. High-risk actions, particularly changes to data, code, configurations, or production systems, should require human approval rather than unrestricted autonomous execution.

Security logging and continuous monitoring should be used to detect abnormal access, unauthorized actions, or behavior outside the agent's intended purpose. Employees should also receive security awareness and acceptable-use training to reduce misuse and inappropriate disclosure of sensitive information. Finally, emergency shutdown and containment procedures should allow the organization to quickly restrict or disable the agent if its behavior threatens confidentiality, integrity, or availability.

7. Implementation and Cybersecurity Resilience Plan

Agentic AI should be introduced through a limited pilot using test data, non-sensitive information, and low-risk systems. During the pilot, the organization should establish and validate an acceptable security configuration that includes least-privilege access, authentication requirements, approved integrations, logging, data restrictions, and human approval for high-risk actions.

Before broader deployment, the organization should conduct vulnerability and penetration testing against the major risks identified in Section 5, including attempts to manipulate the agent, gain unauthorized access, exceed assigned permissions, or cause unintended system changes. Identified weaknesses should be corrected before the agent receives additional access or autonomy. Employees participating in the deployment should also receive security and acceptable-use training before being granted access.

Once deployed, the agent's behavior should remain continuously monitored. The organization should maintain containment, recovery, and incident-response procedures that allow credentials or integrations to be disabled and affected systems or data to be restored following an incident.

Access should only expand after the pilot demonstrates that the Agentic AI operates within the organization's established risk tolerance. Additional access to sensitive data, production systems, external users, or autonomous functions should be granted incrementally and reassessed as the agent's responsibilities increase.

## Draft

### 5. Cybersecurity Risk Assessment
The implementation and benefits associated with introducing Agentic AI are accompanied by cybersecurity threats that must be understood and assessed before implementation and continuously evaluated throughout its operation. Major threats include prompt injection, stolen agent credentials, malicious or inaccurate inputs, excessive system permissions, vulnerable plugins, APIs, or third-party models, employee misuse, and incorrect or unintended autonomous actions.

These threats present varying levels of risk to the confidentiality, integrity, and availability of organizational information and systems. Regarding **confidentiality**, a compromised or improperly configured agent could expose sensitive organizational data or information about the structure of internal IT systems. Prompt injection attacks may manipulate an agent into providing information that it would not normally disclose. Similarly, compromised employee credentials could allow an attacker to use the agent to rapidly retrieve and compile information from multiple authorized sources, potentially increasing the speed and scope of data exposure. Connections to external APIs, plugins, and third-party models may also create additional pathways through which sensitive information could be unintentionally disclosed.

Agentic AI also introduces risks to **integrity** because of its ability to independently modify information or perform actions. A compromised agent could intentionally alter data, code, or system configurations, while a non-compromised agent could produce similar consequences through inaccurate interpretation, faulty reasoning, or unintended autonomous actions. These errors could result in incorrect data, insecure configurations, unauthorized changes, and additional time and resources required to restore affected systems.

Risks to **availability** are particularly significant when an agent is authorized to interact with critical systems. An incorrectly interpreted instruction or unintended autonomous action could interrupt services, modify important system configurations, or otherwise interfere with normal business operations. The potential impact becomes greater as the agent receives broader access and greater authority to perform actions without human intervention.

#### Risk Level and Organizational Tolerance

The likelihood and impact of these risks vary depending on how the Agentic AI is deployed and the level of access and autonomy granted to it. Risks such as malicious inputs, employee misuse, and inaccurate AI-generated actions should be considered reasonably likely because they may occur even without an external system compromise. Their impact may range from low to high depending on the systems and information available to the agent. Prompt injection, compromised credentials, vulnerable third-party integrations, and excessive permissions present a higher organizational concern because successful exploitation could affect multiple systems or expose significant amounts of sensitive information.

The organization may accept **low-impact risks** in situations where an agent operates with non-sensitive information or performs actions that can be easily reviewed and reversed. **Moderate and high risks**, particularly those involving access to sensitive information, modification of production systems, external integrations, or autonomous execution of consequential actions, should be reduced to an acceptable level before implementation.

Certain risks should fall outside the organization's risk tolerance entirely. The organization should not accept a deployment in which an Agentic AI can independently expose highly sensitive information, make unrestricted changes to critical systems, or perform high-impact actions without appropriate oversight. Therefore, the overall cybersecurity risk associated with Agentic AI should be considered **moderate to high prior to the implementation of security controls**. Deployment should proceed only when identified high-impact risks have been sufficiently reduced and the remaining residual risk falls within the organization's established risk tolerance. 

### 6. Security Controls and Countermeasures

The cybersecurity risks identified in the previous section should be addressed through a combination of access controls, technical safeguards, employee policies, and continuous monitoring. Because Agentic AI may interact with organizational data and systems with limited human involvement, security controls should reduce both the likelihood of compromise and the potential impact of incorrect or unauthorized actions.

To reduce the risk of **prompt injection**, the organization should restrict the information and functions available to the agent and separate trusted system instructions from untrusted user input. Inputs received from external users should be treated as untrusted and subjected to stricter limitations than prompts submitted by authorized internal personnel. The agent's responses and actions should also be monitored for attempts to retrieve restricted information or perform actions outside its intended purpose.

The risk associated with **stolen agent or employee credentials** should be reduced through multi-factor authentication, strong identity and access management, and continuous monitoring of account activity. Access to the Agentic AI should be tied to individual user accounts so that actions can be logged and traced. Accounts with access to sensitive systems should receive additional protections because a compromised account could allow an attacker to use the agent to quickly retrieve information from multiple authorized sources.

To address **malicious or inaccurate inputs**, the agent should be configured to validate information before using it to perform significant actions. High-risk decisions should require human approval rather than allowing the AI to automatically act on unverified information. This is especially important when an input could result in changes to code, data, system configurations, or other business-critical resources.

The risk created by **excessive system permissions** should be addressed through least-privilege access. Agents should only receive the minimum permissions and data access necessary to perform their assigned functions. Access should also be separated by task so that compromise of one agent does not automatically provide access to unrelated systems or sensitive information. Permissions should be reviewed as the agent's responsibilities change.

**Vulnerable plugins, APIs, and third-party models** should be limited to services that have been reviewed and approved by the organization. Connections to external systems should be monitored and restricted to the data necessary for the agent's assigned task. Vulnerability testing and secure configuration reviews should also be conducted before new integrations are introduced, reducing the possibility that a third-party component becomes a pathway for unauthorized access or data leakage.

The possibility of **employee misuse** should be reduced through employee security awareness training and acceptable-use requirements. Employees should understand what information may be provided to the Agentic AI, which tasks the agent is authorized to perform, and when human review is required. Access restrictions should further prevent employees from using the agent to retrieve or modify information outside the scope of their responsibilities.

Finally, **incorrect or unintended autonomous actions** require controls that limit how independently the agent can operate. High-impact activities, including changes to production systems, sensitive data, system configurations, or critical business processes, should require human approval. Security logging and continuous monitoring should be used to identify abnormal behavior, while emergency shutdown and containment procedures should allow the organization to quickly disable the agent if its actions threaten the confidentiality, integrity, or availability of organizational systems.

Together, these controls reduce the risks identified in Section 5 by limiting the agent's access, restricting its ability to perform high-impact actions without oversight, and providing the organization with the ability to detect and respond to abnormal behavior. However, these controls should be validated before broad deployment. The organization should therefore introduce Agentic AI gradually and verify that the required security measures operate effectively before granting the technology access to more sensitive data or critical systems.

### 7. Implementation and Cybersecurity Resilience Plan

The introduction of Agentic AI should follow a phased implementation process that allows the organization to validate security controls before the technology is given access to sensitive information or critical systems. Because the risks identified in Section 5 may increase as the agent receives greater permissions and autonomy, deployment should begin with a limited pilot in a controlled environment.

The initial pilot should use **test data, non-sensitive information, and low-risk systems** whenever possible. This allows the organization to evaluate how the agent processes instructions, responds to malicious or inaccurate inputs, interacts with approved APIs or plugins, and performs autonomous actions without creating unnecessary risk to production systems. During this phase, the organization should establish a baseline security configuration that includes least-privilege access, multi-factor authentication, data-access restrictions, approved integrations, logging requirements, and human approval for high-risk actions.

Before the Agentic AI is expanded beyond the pilot environment, the organization should conduct **vulnerability and penetration testing** to determine whether the controls established in Section 6 effectively reduce the identified risks. Testing should include attempts to manipulate the agent through prompt injection, misuse compromised or unauthorized credentials, access information beyond assigned permissions, exploit connected APIs or plugins, and cause unintended system changes. Identified vulnerabilities should be corrected and retested before the agent receives additional access or autonomy.

Employees who interact with the Agentic AI should also receive **security awareness and acceptable-use training** before being granted access. Training should explain what information may be provided to the agent, which actions require human approval, how to recognize suspicious or abnormal behavior, and how potential security incidents should be reported. This helps reduce the risks associated with employee misuse, improper handling of sensitive data, and overreliance on AI-generated outputs.

Once deployed, the agent's behavior should be **continuously monitored and logged**. The organization should review activity for unusual access patterns, attempts to reach restricted information, unexpected system changes, abnormal API activity, and other behavior that may indicate compromise or incorrect autonomous operation. Monitoring should also be used to determine whether the agent continues to operate within its intended purpose as its responsibilities change.

The organization should also prepare **containment, recovery, and incident-response procedures** before broader deployment. If the agent behaves unexpectedly, is compromised, or threatens the confidentiality, integrity, or availability of organizational systems, personnel should be able to restrict its access, disable integrations, revoke credentials, or shut down the agent entirely. Recovery procedures should address the restoration of modified data, configurations, or systems, while incident-response processes should support investigation and determine whether additional security controls are required.

Access and functionality should only be expanded after the pilot demonstrates that the Agentic AI can operate within the organization's established risk tolerance. Greater access to sensitive data, production environments, external users, or autonomous functions should therefore be granted incrementally rather than all at once. Each expansion should be reviewed to determine whether new risks have been introduced and whether existing security controls remain sufficient.

This phased approach strengthens cybersecurity resilience by allowing the organization to identify weaknesses before they affect critical systems and by maintaining the ability to contain or recover from unexpected Agentic AI behavior. Continued monitoring, testing, and reassessment will be necessary as the technology's responsibilities and level of autonomy increase.


---
##  Free Write 

**Cybersecurity Risk Assessment.**
The implementation and benefits associated with introducing Agentic AI comes alongside various threats that need to be ?understood? and assessed before implementation, and analyzed carefully with the mentioned threats ?in mind? during the monitoring phase.

*Agentic AI  Threats*
- Prompt injection
- Stolen agent credentials
- Malicious or inaccurate inputs
- Excessive system permissions
- Vulnerable plugins, APIs, or third-party models
- Employees misusing the agent
- Incorrect or unintended autonomous actions

Each of these threats introduce a varying degree of potential impact to the organization that must be considered. To protect the confidentiality of the organizations data, agents must be carefully assessed in the level of access it is required to do its job to avoid the risk of exposing sensitive information. This also includes the risk of having information pertaining to the structure of the organizations IT systems through non filtered AI responses in a prompt injection attack. Employees must also be restricted from giving the AI access to sensitive information, to prevent the risk of the information being leaked outside of the organization. The added risk is that if a user were to have their account compromised, and that user had access to an agentic AI, there is also the possibility of leaking several sources of accurate information in a much quicker rate to the attacker during the enumeration phase. Misconfigured and unmonitored outputs to APIs and third party modules have the potential of leaking of sensitive information if this is not carefully monitored. 

This loss of control to a compromised Agent AI has the potential loss of Integrity to information that has been modified by the AI after initial compromise. Non Compromised Agent AI introduce the risk of modifying existing code, data, or system settings, leading to the potential risk of incorrect data, insecure configurations, and loss of time and data for reparations. If the AI fails to correctly process and operate inputs pertaining to system servers, it could halt the availability of operations. 

Inputs and actions carried out by the agentic AI must be carefully considered and configured for prompts from internal and external network. If the organization decides to introduce external availability to its customers through solutions such as a chat bot, they must be secured and stricture than the version available to internal staff. 

The liklihood of 



**Security Controls and Countermeasures**
The outputs created by the AI must be analyzed and periodically reviewed to ensure it is not leaking out sensitive information to APIs and third party modules. 


**Implementation and Cybersecurity Resilience Plan**






---
