# Add the Workstation to the domain
1. Log into Windows 10
2. Configure IPs
	1. IPv4: 192.168.0.100
	2. GW: 192.168.0.1
	3. DNS: 192.168.0.10
3. Change hostname
	1. System: About 
	2. Rename PC
	3. CSUSBWS01
	4. Restart later
4. Connect to work or school (Same page)
	1. Connect
	2. Join this device to a local active directory domain
	3. csusb.com {domain name}
	4. credentials for DC
	5. Hit skip
	6. Restart now
5. Boot into server and confirm it's been added
	1. Active directory users and computers
	2. On the computers folder, we'll see the workstation.


# What is Active Directory Users & Computers
![[Pasted image 20250227210622.png]]
![[Pasted image 20250227210628.png]]
![[Pasted image 20250227210642.png]]
![[Pasted image 20250227210713.png]]

##### Users & Computers Window
1 Tools
	1. active Directory users and computers
1. File
	1. Options - delete any changes made to the view of users and computers
2. Action 
	1. Same options when you right click on an object. 
3. View
	1. Quickly add or remove columns to show or hide information as necessary. You can enable advanced features. 
	2. Filter options: Advanced searches, including users, groups, contacts, computers, etc. 
	3. Customize option. You can show or hide components
4. Help: You can get version numbers from here.

Saved Queries - default folder, you'll find expired or locked out user accounts here. Accounts who haven't been logged into for over 30 days. 
- You can create searches and save them for later use. 
- Makes redundant tasks easier. 

*Right click the domain* {**CSUSB.edu**}
**Delegate Control**: - There is a set of users and groups who have control over the domain by default, and with this option, we can extend that control. You can use this to give a specific user control over the OU. 

**Find**: Search button, allows you to find users, objects, where to search, type the name and click find. 

**Change domain**: you can change domain. You would do this if there's a sub domain. You can change to a sub domain or trusted domain. 

**Change domain controllers**: Expect to only see one. 

**Raise domain functional level**: Add AD features when you have multiple domain controllers on a network. Some features are only available when all the servers are on the latest version. 

**Operations Masters**: Allows us to choose which servers operate master roles like the schema master, domain name naming, master relative identified or ID master Primary domain controller emulator (PDC Emulator), or infrastucture master.

**New**: 

**All Tasks**: result set of policy (We'll see what changes get applied to)

**Properties**: information on the domain, the name, who it's controlled by, etc.


# Understanding Organizational Units and Containers

Expand domain and click the name
- To the right under type, we'll see Containers, Builtin Domains, and Organizational Units.

**Containers:** Are structural objects that are included by default within Active Directory. Same thing with OU's (or organizational units)
- An important distinction, is that you cannot apply group policy objects, or (GPOs), to containers. 
- You also can't create a container within AD, although you could ADSI-edit to make one. *Might never have to do that*, unless we're working with Sccm.

Normally we'll see a few types of default containers:
- **Computers**: Default location for new comptuers that join a domain. New AD account or computer account objects will be created inside of this container for the computer. 
- This is important to know, because we want to move computers from the container, into an OU, so we can apply appropriate group policy objects directly to that computer account. This allows us to enforce company security policys. 
- **ForeignSecurityPrinciples**: Holds proxy objects for security principles from other trusted domains. A security principle from another domain could be a user account or a security group that resides inside of another domain. 
- We won't be using this container at all unless we establish a trust between our domain and another domain. 
- **Managed Service Accounts**: Holds the user accounts that are used to operate applications or services that run on our servers or workstations. 
- Since Managed Service Accounts or MSAs, is supposed to be used for services and not by end users, you do not need to create passwords for these accounts, they're typically handled automatically. 
- To create an MSA, you need to use a powershell command line
- **Users**: You'll see administrator, guest (disabled), as well as several default users created by the domain. 
- Know that they're all important, and we don't want to delete any of them. 

Go back to clicking domain, and select the **Builtin** folder for **builtinDomain**
- This object contains security groups, that are required for our domain to operate. We can't delete them because they're all required. We don't even get the option. 
- More information required by the domain.

Go back to clicking the domain, and select *Domain controller* of the type **Organizational Unit**. 
- Used to organize and separate objects within Active Directory. 
- Objects could be anything, including user accounts, computers, printers, file shares, or security groups. 
- let's say you're working in a company that has a marketing team. You want to create an OU called marketing and you'd then store all your marketing users inside of that OU. 
- Used to help make an organized AD, but it's also used to assign specific permissions to that OU. Maybe the marketing team has to use a specific desktop background and special permissions to a file that others may not have. 
- This is why we put the correct user, computer, and printer into the correct OU. Putting them in the wrong one could lead to users having security privileges they shouldn't have. 
- By default, we have a domain controller OU. We can't see the policies from here, but we will eb able to see them from group policy

Make a new OU
- Right click on domain --> New, Organizational Unit.
- Name it
- There's an option to protect from deletion, if you leave this, you have to remove the protection first, then delete it. Useful if the OU is important.

Right click Domain Controller OU
- Choose Export List
- We're asked where to save it
- Save it on Desktop as OU list

Go to Desktop
- Click OU List
- We'll see the contents of the OU. 

Do the same thing with the domain folder
- Name it domain list

Compare the OU list and the domain list
- You won't see information of sub OUs
- Lists are not recursive

Delete OU
- Right click, select delete
- Say yes to the pop up
- We'll be warned that we don't have permission
- Either for permissions or because *it's protected*.

Remove protection
- Select view at the top, and enable advanced features
- Right click the OU
- Go to properties --> Object
- Uncheck protect object from accidental deletion.

Change the view back, and delete the OU again.


# Note about logging into - Domain Controllers with new AD Users

We're going to be creating a new AD user and logging into our domain controller. 
**Windows has changed the default policy** so that normal domain users CANNOT log into a domain controller without the **Domain Admin** role. 

To fix this, we need to add the **Domain Admins** group to our new AD Users that we create in the next lesson.  

Consider adding them to **Remote Desktop Users** if we plan on using RDP

Lesson 21 (Understanding Groups and Memberships) teaches us how to add Domain admins group to our new AD user. 

# Creating User Accounts with AD

Create an OU
- Name it CSUSB (**We're intentionally making it the same name as our domain**)
- Not required, but people do this
- Create another OU within CSUSB and name it Domain Users, protect it
- Make another OU within CSUSB and name it Domain Computers.

*Why did we create a domain user, when there's a container right here?*
- Remember, we can't apply a GPO to a container. We can't apply special policies for users in that container.

Right click domain users
- Select new --> User
- Fill name like normal
- use nomenclature {first.last}
- To the right of user logon is the option to choose a domain.
- Make them a password
- Uncheck  - User must change password at next logon. Sometimes people make passwords right from your computer.
- Finish

At this point, he signs out of the account, attempts to log into that newly created account, and it shows that he can't, because he's not a member of the domain administrators, but we were still able to authenticate. 

### Switch over to Windows 10 
Select other user
- type in the credentials for the account you created.


# Searching for Objects in Active Directory

Go back to users and computers
- Select domain object
- On the banner, 2nd to the top right, select *Find objects in Active Directory Domain Services*
- Or just right click the domain and click find..

Decide what object we're looking for
- Make sure you select the correct object, before searching
- *Users contacts and groups*
- Choose a domain. Decide if it's more practical to use entire directory (including trusts) or a specific domain
- enter the username you made
	- Image putting in the name "Chris" in an enterprise. 
- hit advanced to the right
- Notice the field tab: It goes really in depth
- Hit find

Our user should be located
- Right click, some new options. 
- Notice that it doesn't tell us where the user is located. 
- We can move them, but what if we want to find where they're sitting?

Hit view, select advanced features
- Perform the search again
- Right click user, select properties, now there's a ton of new tabs
- Click object
- We now have the exact path of where the user is sitting 

Lets pretend we just created a new user, and now we want to move it to our domain computers OU
- Remeber, by default, they're put in the computers container. We need to move them
- You could click and drag, but lets say we need to use the search feature.
- Hit the search button, change the find to computers, under the *in* change it to the correct domain
- Remember, all of the workstations contain *ws*. So now we're going to use a wildcard. 
- Under computer name, but a wildcard: 1`*WS*`
	- This looks for anything with WS 
- Hit find

We should see some results, maybe 2. 
- If we perform the same task without including the wildcard, we wouldn't get anything if the name has letters before the "WS"
- Highlight both, select move, and move them to the correct directory path. 
- Hit f5 to refresh
# Resetting User Passwords in AD Users and Computers

Everybody has to know how to do this
Somebody forgot their password.

Get their first and last name, then run a find. 
- Might have to verify spelling or search for the correct domain
- Find user --> Select properties --> Account
- It's good to ask for their logon name
	- *MFA - Something you know*
	- Also good for ensuring its the correct account
- Right click their account and click reset password
	- You have choices to reset a new password, force them to make a new password, and unlock their accounts from here. 
- If you want to reset the password without changing the password, go to properties, account, and just select unlock account. You'll probably see an error to the right that somebodies locked out.
- Apply and save



# Understanding Groups and Memberships

We're going to create and manage groups, and memberships.

We're going to create a new security group within domain users. 
- Right click the folder (or pane), and select new --> group
- Make a group name {**Sales**}
	- Pre windows can't have names too long
- **Group Scope** - the accessibility of this group
- **Group Type** - choose between a security group or a distribution group
- If we choose a **domain local** scope, this group will only be accessible from within this domain. If we have another domain and we established a trust, this group will not be accessible outside of the domain, because of **Domain Local**
- Notice that the scope goes from least accessible to most accessible
- **Global scope** - same as domain local, except the group can be accessed from another domain, if there is a trust established 
- **Universal scope** - Same as global, except that the group can be accessed by other forests that trust our domain. 

when it comes to group type:
- **Security group** - used to specify permissions within our active directory domain. Accessing specific files, printers, servers, file shares and much more. 
- **Distribution group** - solely used as an email distribution list. If we have an exchange server, we could create a distribution group, and add all our IT support to that group. When an email is sent to the IT support group. It will also be sent to all the users who are a member of the IT support distribution group. 

We're making a {**Sales**} group, with a **Global Scope**, and it's a **Security Group**.
- Click ok

We should see our new group. It should list the type, and the scope.
- Right click the new group and select properties.
- We can put in information: Description, email
- We can expand the group scope, or change the group type. We can also add notes
- We can add members
- We can say what this group is a member of
- Who it is managed by
- Two **most important** groups within the properties tab are: *members & members of*
- Add our user as a member of our group
- Select add, we'll enter the name (full name or username)
- Check names - we should get a result
- Hit ok
- We should be able to verify our user in members

Switch to members of tab:
- Works the same as members, but the function is different. We can essentially make this group a member of another group.
- Lets say we want sales to also be a member of the customer service group, we'd select add, type in customer service, hit check name and add. 
- We can also add them to default groups already created by the system, like administrators or RDP. *Do what makes sense*

Right click our created user account
- Go to properties --> Member of
- We can now verify what they're members of

Lets look at default system created security groups
- On the left, click the built in folder
- Look for administrators
- If you have issues looking for a group, remember to use the find option.
- Right click administrators and go to properties
- and look at members
- Remove sales from administrators

He pointed out the icons are different between users and group. 

After he kicked sales out of administrators
- Go back to sales and verify that we're no longer a member of administrators.

Delete sales
- Right click, hit delete

# Disabling and Deleting User Accounts with AD
Create a new OU underneath the OU that is named after the domain
- Name this OU disabled users
- Quick way to see who's disabled
- **Leave disabled accounts** here for 30 days, just in case you need to reactive it, or need to investigate into teh account further
- Pick an account and disable it
- Move it to our disabled accounts folder
	- We might get a pop up warning us about GPOs

He then tried logging into the disabled account from a remote workstation
- We should see a notice

He then renabled it








