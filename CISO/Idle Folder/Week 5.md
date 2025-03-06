
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


## Group Policy Precedence


## Editing GPOs (Group Policy Objects)





