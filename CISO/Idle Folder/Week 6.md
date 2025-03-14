
# Troubleshooting Group Policy with MMC (RSOP.msc)

Troubleshooting steps for when there's issues with group policy.
- Resultant Set of Policy (RSOP)

Something that allows us to see which policies are being pushed to the computer and to the user that you're currently logged into.

*Open RSOP*
1. Click search bar
2. Type rsop.msc   (Only found on Windows)

![[Pasted image 20250313204957.png]]
**Note:** You can also get there by its file path. 

![[Pasted image 20250313205317.png]]
**Note**: You can see the source of where the GPO is being inherited from. This helps to discover if your GPO is being conflicted from another. 

You can double click the source GPO and get more info
*Example for one of them*
![[Pasted image 20250313205851.png]]

Great tool to use if group policy is not operating in the way that we expected.
# Troubleshooting Group Policy with CMD



# Creating Non-Inheriting Organizational Units for GPO Testing


