# Gameplan

Warn people to make a password list

## Initial Configurations

1. Install guest services thing
2. Configure a static IP
	1. Local server
	2. Ethernet: IPv4: 192.168.0.10
	3. Uncheck IPv6
3. Assign DNS
	1. 127.0.0.1
	2. 8.8.8.8
4. Rename computer name from local server tab
	1. Expect to restart
	2. Keep in mind, the file tab sections are now at the bottom of the screen, instead of the top.
5. Connect to the internet
	1. cmd
	2. ping google

## Adding AD services
1. Manage -> Add roles & Features
	1. Leave role based,
	2. Hit Next 
	3. Choose Active Directory Main Services Role
		1. Expect it to requests other roles to add
		2. Click add features
	4. No need to add any additional features
	5. ADDS Screen, click next, 
	6. confirmation screen, you'll see role , hit next
	7. Click flag with triangle exclamation point
		1. **Choose promote this server to a domain controller**
2. This is when we choose to create a subdomain, new domain to an existing forest, or a new forest
	1. **We don't have a domain yet**
	2. Create a root domain name and make sure it ends in .com
	3. It's gonna be hard to change the name after its been created
	4. Forest functional level and Domain Functional level will specify which OS to use. 
		1. **You might see Windows Server Technical Preview**
	5. Make sure DNS is checked
	6. GC - Will list all active directory objects
	7. RODC - Domain controller won't be able to make changes to domain
	8. DRSM Password needs to be set. This is how you take an instance of AD offline for maintenance or troubleshooting
3. DNS Options screen
	1. DNS Delegation - People on the internet won't be able to resolve local dns names on your local dns server. ITflee.com itf01? We don't want people to access our server.
	2. Leave unchecked
4. NetBIOS Name
	1. Populated by default, FQDN
5. Paths, Folders needed by AD to save storage
6. You'll see a preview and an option to view script.
	1. This gives you a powershell script you can save that was made by the wizard
	2. You can give this to an AI
7. Hit next
8. The server will now verify if its prepared to be a DC
	1. **You might see errors...**
	2. If necessary, make changes, then click rerun prerequisites check
9. Install

## New login
1. Expect to see {FQDN}\DomainUserName
	1. If we were a part of more domains, we'll see them on the left.
2. Now we'll see some new roles at the bottom of the server manager screen.

# Install Windows 10 Pro/Education
- **Doesn't have to be licensed**
- **You can't join a windows 10 to a domain if it's home**
- He left RAM at minimum
- Changed storage to 80

- Set a password
- Turn off all of those choose privacy settings thing.

# Adding Computer to domain
- They both have to be powered on at the same time
- They both have to be on the same NAT network
 1. Open cmd
 2. Run ipconfig until you get an IP
 3. You might get a 10 address, this is fine, make it static.
	 1. 192.168.0.100
	 2. Default gateway, consider that it might eduroam
	 3. DNS Server: 192.168.0.10 (**Server IP**)
 4. Confirm settings with ipconfig
 5. We can try pinging the DC, but Microsoft made it where we can't ping DC's unless we allow them first. 
###### Now to rename the computer and join it to a domain
1. Go to settings -> system -> about
2. Rename the PC
	1. CSUSBWS01
	2. Restart later
3. You should see a tab underneath name that says connect to work or school
	1. Click connect
	2. Click, join this device to a Local Active Directory Domain
	3. Type {domain-name.com}
	4. Hope to get a pop up that says Windows Security (Join a domain)
		1. *If you see this, it means you're connected to the DC.*
	5. Type admin username and password
	6. You can create custom permissions on the add an account screen. For now, hit skip.
	7. Let it reboot and power back on
	8. Move back to Windows Server

###### Windows Server
1. Manage -> Active Directory Users and Computers
2. Expand Domain name, Click Computers, Confirm that the workstation is there. 
3. Now we can move it into another organization unit, or GPOs. 
4. We'll learn that another time. 


---
# Windows 10 Education vs. Windows 10 Pro

![[Pasted image 20250221114657.png]]

