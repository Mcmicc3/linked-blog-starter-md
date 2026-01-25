1. Create Security Groups for each section of my organization 1. 
2. Create users and assign them to their corresponding groups 
3. Organize Computers into their corresponding OUs 
4. Assign GPOs to those OUs limiting local login to just their respective security group and the admin group. 
5. Push a password policy for all domain users
6. Limit local root access with LAPS
7. For Linux machines, use SSSD
8. Create a script to audit GPOs 
9. Harden user accounts to limit their privileges 1. Complex, rotating passwords, lockout policies 2. Prompt UAC for actions that require sudo privileges 
10. Create a network share for each respective group 
11. Harden the AD Administrator account.
12. Create a Break Glass Account



# Remember to get this done
I have to manage account permissions (Linux)
- Lock down /etc/sudoers
- Don't allow people to brute force the local admin password
- Make sure only admins are in the sudoers group

*Consider denying internet access for privileged accounts and logging their activity separately*


# Understanding SSSD
I can still manage Authentication rules for accounts like password policies, but I can't configure GPOs settings. For this I need SSSD

## 🛠 How You Control Login Access on Linux Machines (SSSD)

Instead of GPOs, on Linux you would:
1. **Use SSSD (System Security Services Daemon)** rules to control **which domain users/groups can log in**.
2. **Use `/etc/sssd/sssd.conf`** configuration to specify **allowed groups*
3. **Use `/etc/security/access.conf`** to control login permissions even tighter.
4. **Configure `/etc/sudoers`** to control **who can escalate privileges**.
✅ SSSD allows you to define _only users in a specific AD security group_ can log into the Linux machine.


# Prompts to ask later
Wait a minute, I created a {nmacdonald-admin} account, but what happens to root when somebody tries to log into it? Is it a domian root account? local root account?
- We use LAPS to manage that local Root Account

Thank you for clarifying that for me. My next question, aside from delegating controls to admins, I'm still creating GPOs to control local logins. Is this method that you suggested previously, still going to work for Linux machines?
- No, you need to use SSSD. 

Oh okay interesting! So SSSD is simply a client, but how are these rules going to get pushed onto every machine? Once I configure the config files for local logins and things like who's in sudoers, how will that get distributed? Would I need to manually log into each machine and configure these settings each time?
- Use ansible to automate the configurations, or ssh into each machine and run a bash script

So, I ended up creating GPOs for each role, just like you suggested yesterday, but this was before I learned that the GPOs will not effect or control Linux machines. I still have those computers in the OU. Would leaving the GPO as it is, create any errors? Should I reorganize my Domain OUs? 
- No, no error messages will be produced

Showing you a **Linux hardening checklist** you can follow (just like the AD checklist we built earlier)?
- done

Excellent, I have all my OUs named properly, all my computer objects and users are organized just how you suggested they should. There's only one Object that I've left in its default location. The DC controller. As you know, by default, It's listed inside the domain controllers OU. Should I leave it here? I was thinking about pushing the complex passwords policies and other suggestions you had, underneath my domain in Group Policy Management. That way the GPO policy gets pushed out to all of my users, including the domain controller. Is this a good idea? What about the administrator account that is created by default? I think this is the same administrator account I'm using to log into my Domain Controller. It's currently in the users container, should I do something about that? 
- Yes. Everything should stay where they belong

I just realized something. I'm using the default administrator account to log into my DC controller and edit my AD environment. Lets say I enforce the password policy, including account lock out thresholds. If somebody attempts to brute force my default administrator account, it's going to be locked up. How could I prepare for this so that I may log back into AD and unlock my default administrator account?
- Solution: Create a break glass account

I want to understand. When I log into the default admin account, why do I have permissions to move users into groups, delete and create OUs, among many other things. Where are all these permissions given on AD? I want to see where the configurations come from. 

Why are there security groups in the builtin folder, and the users Container?

# Hardening Linux
1. Authentication Hardening
2. SSH Hardening
3. Local Privilege Hardening
4. Filesystem and Data Protection
5. Patching Updates
6. Logging and Monitoring
7. Network Hardening
8. Application and Service Hardening
9. Physical and Console Security

# Things I noticed
There's a Key Distribution Center Service Account here that is disabled. Is this why I was having problems with kerberos before??
- Apparently works even if its disabled