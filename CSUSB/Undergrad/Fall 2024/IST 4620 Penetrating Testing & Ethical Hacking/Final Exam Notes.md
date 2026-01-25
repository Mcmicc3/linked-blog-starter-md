
# **Part A - Kali** 

Login to Kali with the default userid and password. Use leafpad a create a file called Machines.txt. Find the other VMs on the network (use a scanning tool such as netdiscover, nmap, etc.) 

The following are questions/actions for the Kali machine (Answers go in the Machines.txt): 

- What is the IP Address for Kali? 
	- IP Address: 192.168.1.56

- There is a “flag” on this machine. Find it. What is the name of the flag on the machine? (yes, this is all the information you have as it relates to the flag.) 
- Save the flag for upload.   
![[Pasted image 20241213181323.png]]
      
        
      
# **Part B - Win7**   
Target: 192.168.100.202 or 203

      
This machine has three user accounts which you need to discover. You will need to get the hashes, passwords and flags that are in each account. A bootable CD similar to your Yumi thumb drive has been attached to the VM. One of the items on the CD is Ophcrack. There are other tools also that you can choose to use if you like. To use the CD read the screen when the VM first boots up. You should be able discover how to boot from the CD instead of the HD. Hint – look for the key to hit to change the boot sequence.   
      
When you run Ophcrack, it may not load the rainbow tables. If it does not, install the tables located at /media/hdc/tables. You may use other means for retrieving the passwords and flags.   
      
       
      
The following are questions/actions for the Win7 machine (Answers go in the spreadsheet): 

- What is the IP Address for this VM? 
- What are the three user accounts? 
	- user1
	- user1_2
	- User2
	- Hackerbaby
	- scooby
- What is the hash for each account? 
![[Pasted image 20241213165342.png]]
- What is the password for each account? 
	- Scooby: jumper
	- Hackerbaby: flowers
- What is the name of the flag for each account? 
	- I logged in, but both of them said "Activate windows now". Couldn't find anything. 
- Save the flags for upload.   
![[Pasted image 20241213180540.png]]
![[Pasted image 20241213174843.png]]
      
# **Part C - Mystery VM**   
      
There is a vulnerable machine on the network. You will need to find it. Once you find it, you will need to identify the OS, find a vulnerability and exploit it. Take a screenshot of the successful exploit.   
      
       
      
   The following are questions/actions for the “Mystery machine” (Answers go in the spreadsheet): 

- What is the IP Address of the VM? 
	- IP: 192.168.100.202
- What is the OS of the VM?
	- Linux
- List at least 4 ports that are open. 
	- Port 21: FTP
	- Port 22: SSH
	- Port 3306: mysql
	- Port 5432: postgresql
- List at least one vulnerability that this VM has.
	- vsftpd 2.3.4
- What exploit can you use against this VM? 
	- exploit/unix/ftp/vsftpd_234_backdoor
- Run the exploit.  
- Take a screen shot of the successful exploit and save for upload later.   
![[Pasted image 20241213172015.png]]
      
        
      
# **Part D - De-ICE**   
      
You are pentesting the "No Security Corp's" server. You are tasked with finding the open ports on their server, and see if you can gain access to the machine via their SSH server. You can use any tool you like to scan the machine and ports. Open the web page for the server. Find names of the three **IT** staff and their positions. To hack the SSH Server you may want to use hydra. If you use hydra take the following into consideration: 

- Create a list of usernames using different naming conventions such as first initial, last name and last name first initial. 
- When cracking the passwords use the rockyou2.txt wordlist in the /usr/share/wordlists/ folder. 
- Check for null passwords, try the userid as the password, and try reverse login as pass. 
- Add the option that has hydra loop around users (otherwise it will go through the userid completely one at a time). 
- Limit the number of concurrent tasks to 4 or hydra may not work. 
- Set hydra to verbose. 
- Below is a hint on how to format the command to run:   
      
     

hydra -L FILE -P FILE [-e nsr] [-t TASKS] [-u] [-v] [IP Address] [service] 

The following are questions/actions for the “De-ICE” machine (Answers go in the spreadsheet): 

- What is the IP address of the machine? 
	- 192.168.1.100
- What operating system is it? 
- List 4 open ports. 
- List one vulnerability that exists on the machine. 
- Copy the command you used for hydra to pentest the SSH server. (at the bottom of spreadsheet) 
- What are the three IT user accounts? 
- What are each of their positions? 
- What is their hash? (hint: if you get the senior admin pw, then shadow may be possible) 
- What are their passwords?