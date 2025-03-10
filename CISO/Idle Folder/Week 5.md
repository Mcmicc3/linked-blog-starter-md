
# Group Policy Management

## What are group policy's

### What does Group Policy do?
- A tool used by IT pros (System Administrators, Help Desk, etc...)
- Deploy Configuration Changes
	- Users
	- Computers
- Make configurations in Group Policy ONE time and configure 1000s of computers

Quickly and easily make changes that affect thousands of users on the domain
- You can restrict user access to certain computers
- Restrict User access to specific files & folders
- Or deploy specific software on a group or domain

### Group Policy Cont.
Group policy is a MUST HAVE skill
Active Directory knowledge is a prerequisite.


### How does Group Policy Work 

Applying (link) a GPO to OUs
	- GPO = Group Policy Object
	- OU = Organizational Units
GPOs contain user and computer configuration settings 

When a GPO is applied to an OU,  the settings configured in the GPO are applied to the users and the computers that are within that OU.

You can also configure the GPOs to only apply to certain objects by defining the security filtering. 

The most common default choice is the authenticated users group, which is basically any valid user or computer object within Active Directory. 
### GPO Recursion 
A GPO will apply recursively to all sub OUs and objects
- This means that any setting that is applied to a parent OU or towards the domain will also apply to all sub OUs beneath the original OU that the GPO is applied to. 

### Open GPO Management
Tools --> Group Policy Management
![[Pasted image 20250303174213.png]]
When you expand a forest, you'll see:
1. Domains
	1. Contains all of domains under forests
2. Sites
	1. Contains all of our sites confiured through AD
	2. Used when there's servers, physically located in different locations (Cities, countries)
3. Group Policy modeling
4. Group Policy Results

*The last two folders are tools that can be used to troubleshoot any group policy issues that may arise while working with GPO*

Expand domain we created
We'll see a similiar view from users and computers. 
**Note that we don't see any containers like users**
We can see OUs that we created and default domain controllers OU.

![[Pasted image 20250303175642.png]]
**Note:** He created an OU that is the same name as the domain
- Within the OU, he made three more OUs called: Disabled Users, Domain Controllers, & Domain Users
- *He's simply pointing out that we can see them from here*

**Default Domain Policy**: A pop up comes up. "We selected a link t o a group policy object, not a GPO itself."
- Ignore it for now
![[Pasted image 20250303185445.png]]
Comes by default when a new domain is created.
*Since it is directly under the domain CSUSB.com, it will be applied to all AD objects, beneath the AD domain.*
- This includes Domain Controllers, *Our future csusb.com OU and it's folders*

**Group Policy Objects**: Inlcudes all GPOs that are inside of the domain, whether they are in use or not. 
![[Pasted image 20250303190027.png]]
*Note:* that the Default Domain Controllers Policy within Group Policy Objects is linked to the Domain Controllers OU

**Default Domain Policy**:  TBD
**Default Domain Controllers Policy**:  TBD

###### WMI Filters
![[Pasted image 20250303190249.png]]
**Note**: Allows us to add specific rules when a GPO should or should not be applied. 
- Example: You could only apply a particular GPO if the computer is using operating system of Windows 7 or newer.

###### Starter GPOs
![[Pasted image 20250303192211.png]]
**Note**: Used when you want to import or export GPOs for distribution to other environments

## Creating and Linking Group Policy Objects (GPOs)
Domains can contain several GPOs and will almost never contain just one. 
It's important to know that one individual GPO can be linked or applied to multiple OUs simultaneously.

Example: You can install a GPO that installs Adobe Flash Player and apply that GPO to all of the OUs that contain computers which need Adobe Flash Player.
- Or create one that prevents users from launching IE and link that to everyone

### How to create a GPO
Right click group policy object 
![[Pasted image 20250307031643.png]]
*Note*: You can right click on the domain (or OU), and select, create a GPO in this domain, and Link it here..
![[Pasted image 20250307031805.png]]

**The difference**, is that the latter will create a GPO and it will create a link for the GPO, which means that the GPO will take effect wherever we create the link

*We're going to try both methods*
- New GPO window will appear
- Name it: Test GPO
- **Source Starter GPO**: None (because we don't have any other GPOs)
	- GPO is going to be blank, and all the settings wont be configured.
![[Pasted image 20250307032151.png]]
*Note*: the two locations we see Test GPO. The one underneath our domain is considered to be a link.

Right click the link GPO underneath our domain, and choose delete. 
- Note that it says, it won't delete the GPO itself. 
- **Notice**: That our test GPO underneath Group Policy Object's is still there. 

Delete the test GPO itself
- Different warning, do you want to delete the GPO, and all links to it in this domain? 
- This will not delete links in other domains.
- Hit yes.

*He's showing what happens if you create the GPO under the GPO folder*
- When you do it this way, the GPO is not linked anywhere in our domain. 
- It won't take affect because it's not linked anywhere. 
- Even if we made changes to it, it still wont take affect

### Demonstrating linking that GPO
Select "Link to existing GPO"
![[Pasted image 20250307035416.png]]
You'll see a drop down list, if you had multiple domains, you'll see GPO choices from that domain as well
- Now we just created a link.

### Scenario: Apply GPOs to our domain users and computers
- If we link our GPO to our domain, the GPO will apply to everything under the domain.
- This includes domain controllers, and our created OU, and everything inside those OUs. 

We only want to target both our created computers and users OU. 
- Right click them, and select link an existing GPO.
- Same box as before, click ok

Do the same process for both GPOs
- In theory, now we can start editing our GPOs to make changes to objects inside those GPOs


### Configuring our GPO
*After we've linked our GPO to the OU we created*
Right click the GPO
![[Pasted image 20250307040956.png]]

**Edit**: Where we actually configure the user settings, computer settings
**Enforce**: Enforce this GPO to take precedence over other GPOs
**linked enable**: You can temporarily disable the link. Better than deleting the link, if say you want to test it if the GPOs creating problems. It will cause the GPO to not take effect to the domain computers OU. **Note that it's enabled wherever you don't disable it**
**Save Report**: Lets us know all the settings.
**View**: Changes the view
**New Window from here**: only displays GPO on left. Not too useful. 
**Rename**: If you rename it, it will change the name everywhere else. 

Click save report and save to the desktop to see what it does.

![[Pasted image 20250307041824.png]]
Here we see settings of our GPOs
**Note**: At the bottom, we can see specific configurations for Users & Computers, but nothing has been defined yet. 

### Discussing what's within the right
![[Pasted image 20250307043919.png]]
**Scope**: We can display all the links
- Tells us where this GPO is being applied
- You can right click the location and delete the links

**Security Filtering**: We can make the GPO only apply to certain user types
- Hit add, we can type administrators, hit check name
- Now our GPO will effect Administrators
- If we leave Authenticated users, we won't change anything, but if we remove them, now the GPO will only affect administrators
	- You can double click the group and check members

*He ended up deleting both user groups, then re added authenticated users*

**Authenticated Users**: Special group, can't go to properties because it's anybody who's able to authenticate to the domain. This can include user account, computer accounts, even printer accounts. 
- Any AD object that is authenticated, this GPO can affect.

#### WMI Filtering
Down at the bottom
More filtering in addition to security filtering. Only apply GPO to Windows 7 computers. We haven't created an WMI filters, so there's nothing we can do. 

### Details pane
![[Pasted image 20250307044717.png]]
Domain, owner, domain admins, when it was created and modified, user version and computer version, unique ID, status. 

**Note**: If we're going to replicate our GPO onto other computers, we need to make sure that our computer version matches the other devices. This prevents any replication issues. 

### Settings Pane
![[Pasted image 20250307045014.png]]
Same settings that we saw when we created a report. 
- By default, IE will try to block this
- You can hit add to add an exception
- Do this because we trust Group Policy

Expect to see user and computer configuration. 
*He demonstrated going back to Details, switching the status to disabled for computers, goes back to settings, and we can see the change reflected there*

### Delegation Pane
![[Pasted image 20250307045335.png]]

This is a list of users who have permissions to read, edit, delete, or modify the GPO itself. 

**Note**: Any Authenticated user can read our GPO
- We want everyone to read it in case it has a setting that applies to them. 

**Note**: There's an advanced button at the bottom right for more settings.

## Group Policy Precedence

**Precedence**: The order, or way that things are done. With Group Policy, there is a specific order in which GPO settings are applied. 
- Important because sometimes multiple GPOs are trying to configure the same setting and you have to understand the precedence in order to understand which settings will be applied, and which will be ignored. 

**Group Policy order**:
1. Local GP  (**Least Important**)
	1. gpedi.msc
2. Site 
	1. GPOs applied to site
	2. Overwrites any conflicts found between the local and site GP
	3. **Site policy takes precedence over local (Wallpaper example)**
	4. *CSUSB*
3. Domain
	1. Any policies assigned to domain, will now be applied on top of site and local settings
	2. *CSUSB.COM*
4. Organizational Unit
	1. Any GPO linked to a specific OU
	2. Sub organizational units if any. If there's an OU within an OU, that sub OU will be applied last, and therefore its settings will take precedence over anything above it.
	3. *Domain Computers OU*
5. Enforced Group Policy Objects. 
	1.  Any GPO you've right clicked and chose to enforce. 
	2. *Workstations OU*

When we think about precedence, it starts with local GP, and then you end with enforced GPOs. So if there's any conflicting settings between the local GP and the Enforced GP, Enforced GP will take precedence since it runs last. *Last GPO to be applied wins*. 
- Some people remember it with **LSDOE**


### Computer vs User
Within GPOs we have user and computer configurations. 

*The computer configuration is applied first and the user configuration is applied second.*
1. Computer Configuration (Least Important)
2. User Configuration (Most Important)

*Remember, settings applied last, are going to win*
- If there's conflicting settings, the user configuration will win and take precedence

### Blocked Inheritance
- OUs may block inheritance
- Only GPOs inside the OU will apply
- **Except** for enforced GPOs above the OU

![[Pasted image 20250307054638.png]]

Ex: If we block on that specific OU, the test the default domain policy would not apply, but the test GPO would apply. 

*Refer to picture on phone*

Talks about blocking inheritance from Administrators OU
- Test GPO from within CSUSB.com won't apply, and neither will default domain policy.

What happens if we enforce a wall paper policy underneath domain? 
- That enforced GPO will take precedence

## Editing GPOs (Group Policy Objects)

Right click GPO and hit edit
![[Pasted image 20250307060018.png]]

Which do we edit? Users or computers? 
*It depends on what we're linking the GPO to*

**Example**: If we're linking this to an OU that only contains computer accounts, such as domain computers, then we're going to edit settings under computer configuration.
- Same logic if we're configuring settings that are only meant to be applied to an OU with Users. 

*If our logic fails and we apply user settings to an OU with only computers, nothing will happen*

**Note**: What if we're working with an OU that has both users and computers? 
- In that case, we can make changes to either one and they'll take effect, but only the computer configurations would affect computer objects, and only user configurations would affect user objects. 

*It's generally best practice to keep the user and computers in different OUs just to avoid confusion like this*
- Makes it less complicated

### Policies and Preferences
If we expand all the folders, even though they all have the same names, it doesn't imply that making changes in computers, would create the same changes in users. 

Most settings are the same, but a few are different
**Example**: 
1. Under Computer configurations -> Windows Settings, we have Name resolution policy, but it wont be found under user settings
2. Alternatively, folder redirection is not found on Computer configuration
![[Pasted image 20250307061825.png]]

*There's way too many, and we're being encouraged to browse through the settings*![[Pasted image 20250307062029.png]]

Areas to look:
1. Power options
2. Printers
3. Local Users and Groups
4. Event logs

![[Pasted image 20250307063145.png]]

Right click a setting, hit properties, and check what it does. 
- We can learn what it is and enable and disable it from there. 

*Example*: He disabled prevents local guests group from accessing application logs. He went back to GPO manager, right clicked the GPO and hit settings
- To refresh, right click the OU and hit refresh
- We should be able to see under computer configurations, that our policy changed. 

A lot of our own research will be needed to configure GPOs


*He ended by deleting the test GPO*

