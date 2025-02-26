question: SHould we get a baseline of everything running fine and then run netstat  
question: Can we poke around and find compromise with rbash?  
  
How to secure a machine taht's already compromised  
- Think about if it's the machine that is compromised or  
- Establsihed persistence Check Cron tabs...  
- CHeck Backdoors -   netstat -tulpn  
-  Checks all outgoing connections  
  
Do we have to log into our user accounts?  
- We could create our own accounts  
  
Audit our users  
cat /etc/passwd | grep -v nologin | grep -v false  
  
## If we suspect one of our users are compromised  
*If the competition allows us*  
  
Set to RBASH, create a new user  
  
chsh -s  
- Changes shell  
  
 #### He's creating an account  
He created a user.  
  
chsh -s /usr/bin/rbash <user>  
  
### It's bad if too many people have bash shells  
  
Change passwords to users already on the system  
= passwd  
  
**We don't want to set the password from command**  
  
sudo passwd MrRobot  
- This allows us to create a password without the password showing up in cleartext,. think history  
- We're fucked if they're using a key logger.  
  
If a user is compromised..  
  
Add our own account and set it to rbash  
  
If the scoring engine needs to log into a user, we can't do that.  
  
Check processes under that specific user.  
- We have to allow the account ot be open  
  
Cerate a user add them to suders.  
- As admins we need full persmission  
  
### Checking who's currently logged in  
Run 'who'  
  
if you see pts, think remote connection  
  
## Interacting with remote user  
echo "hello" {who-user} /dev/pts/3  
cat /dev/urandom > /dev/pts/3  
wall "whattup babygirl"  
- Sends a message to everyone on the system  
  
### why use rbash  
who  
- Fuck, we're compromised  
ps aux | grep pts  
- Identify the remote session  
- look for sshd and a remote user  
- find the process and kill it  
- sudo kill -9 {processID}  
  
## Problem  
It only works with ssh  
WEBSHELLS  
people can still popshells on your machine  
  
## Can we monitor what they're doing?  
Lock them out first  
Read their history  
  
## IF THERES NO ORANGE TEAM  
rbash everybody and create your own user.  
  
ssh_config is client side  
sshd_config is server side  
  
**We want to change sshd_config**  
change it so that we don't allow for root login  
We can change the maximum amount of login attempts  
Change the maximum amount of sessions  
  
ssh has a thing where we can do key authentication login  
  
starting local machine  
ssh-keygen -f test  
- -f is to name it  
(You can assign a password to using a private key)  
  
From local machine, the one ending in .pub is the public key  
  
the remote user has to have save that public key in /.ssh/authorized_keys  
- In the home directory of whatever account we want to use the keys.  
  
Go back to local machine  
`- ssh -i {private} {username)&(IP)`  
  
(remote user)  
  
/etc/ssh/sshd_config  
- He uncommented pubkey authentication  
- Passsword authentication changed to no  
- permitrootlogon changed to no  
- CHange maxauthtries  
- maxSessions  
  
---  
We don't know what dns service they're using  
- If we need to change something, it's probably in /etc  
- **Unless it's in a docker container**  
  
## How to check if a container is running  
docker container ls  
  
docker exec -it containerID /bin/sh  
docker exec -it {id} ps aux  
  
  
## Reverse shells using web exploits are typically initiated in /var/www  
  
  
### Think about how we're gonna prevent privilege escalation  
- Make it as hard as you can for them to get in  
- They're professionals, they're gonna get in  
- Make it hard for them to priv esc  
  
suid bit, a special to add onto a file or an execuable that allows it to run as a different user  
- Hackers set this to root  
  
He wrwite a script, it makes a list of every installed package on a machine. It checks GTO bins, checks every application with a suid  
  
He checked for what has a suid  
- find / -type f -perm -4000 2>/dev/null  
- This displays everything with suid  
- He showed us GTFObins  
- It compares the data from find, and looks for articles with known exploits on how to abuse it  
- If something pops up  
- Best chance, take off the suid  
- Take it off with  
- Chmod -s {name of service}  
- use -s to run as a different user with privileges, doesn't have to be root.  
  
## Creating a baseline  
  
  
  
  
## Router  
  
MAKE A BACKUP OF YOUR ROUTES  
make it sticky (stickybit)  
- If anyone tries to delete that file, and if they're not the owner, it won't delete  
- ASK ABOUT STICKY BIT  
- Check documentation, find where backups are stored  
- Assign a sticky bit  
- Copy those backups, save them on the backup server, and somewhere in the router  
  
  
  
## DNS  
  
You can make DHCP talk to DNS so that even if an IP changes, DNS updates to prevent problems  
- An attacker will take down DNS  
  
Take all DNS entries and add them to /etc/hosts  
- That has to be done manually on each machine  
- It's like making a local DNS cache  
- This can be automated.....sshpass  
- ssh () <echo "text" >> /etc/hosts  
  
If the people attacking us are the same people who are hosting this, this is a whitebox environment, they can quickly find anomalies.  
  
  
## What to do at the start  
**NMAP OURSELVES**  
- Find out what you're running  
- nmap 192.168.t.0/24 -T5  
- This shows what everyones running  
- **Then do an aggressive scan on yourselves**  
- nmap -A -p- -sV -oN scan.txt  
- oN sends it to a text file  
  
bg  
fg  
jobs - to see everything  
  
Use /var/log to find attempted ssh connections  
- Every service has some sort of logging, we need to figure out how to get it.  
Logs to think about  
- A successful login is different from a login attempt  
- Authentication success log (depends on service)  
- Attempted login (think bruteforce)  
- Configuration changes  
  
  
sudo systemctl status ssh  
- We'll see active sessions  
- Logs  
  
We can use this with other services too



---

question: SHould we get a baseline of everything running fine and then run netstat  
question: Can we poke around and find compromise with rbash?  
  
How to secure a machine taht's already compromised  
- Think about if it's the machine that is compromised or  
- Establsihed persistence Check Cron tabs...  
- CHeck Backdoors -   netstat -tulpn  
-  Checks all outgoing connections  
  
Do we have to log into our user accounts?  
- We could create our own accounts  
  
Audit our users  
cat /etc/passwd | grep -v nologin | grep -v false  
  
## If we suspect one of our users are compromised  
*If the competition allows us*  
  
Set to RBASH, create a new user  
  
chsh -s  
- Changes shell  
  
 #### He's creating an account  
He created a user.  
  
chsh -s /usr/bin/rbash <user>  
  
### It's bad if too many people have bash shells  
  
Change passwords to users already on the system  
= passwd  
  
**We don't want to set the password from command**  
  
sudo passwd MrRobot  
- This allows us to create a password without the password showing up in cleartext,. think history  
- We're fucked if they're using a key logger.  
  
If a user is compromised..  
  
Add our own account and set it to rbash  
  
If the scoring engine needs to log into a user, we can't do that.  
  
Check processes under that specific user.  
- We have to allow the account ot be open  
  
Cerate a user add them to suders.  
- As admins we need full persmission  
  
### Checking who's currently logged in  
Run 'who'  
  
if you see pts, think remote connection  
  
## Interacting with remote user  
echo "hello" {who-user} /dev/pts/3  
cat /dev/urandom > /dev/pts/3  
wall "whattup babygirl"  
- Sends a message to everyone on the system  
  
### why use rbash  
who  
- Fuck, we're compromised  
ps aux | grep pts  
- Identify the remote session  
- look for sshd and a remote user  
- find the process and kill it  
- sudo kill -9 {processID}  
  
## Problem  
It only works with ssh  
WEBSHELLS  
people can still popshells on your machine  
  
## Can we monitor what they're doing?  
Lock them out first  
Read their history  
  
## IF THERES NO ORANGE TEAM  
rbash everybody and create your own user.  
  
ssh_config is client side  
sshd_config is server side  
  
**We want to change sshd_config**  
change it so that we don't allow for root login  
We can change the maximum amount of login attempts  
Change the maximum amount of sessions  
  
ssh has a thing where we can do key authentication login  
  
starting local machine  
ssh-keygen -f test  
- -f is to name it  
(You can assign a password to using a private key)  
  
From local machine, the one ending in .pub is the public key  
  
the remote user has to have save that public key in /.ssh/authorized_keys  
- In the home directory of whatever account we want to use the keys.  
  
Go back to local machine  
`- ssh -i {private} {username)&(IP)`  
  
(remote user)  
  
/etc/ssh/sshd_config  
- He uncommented pubkey authentication  
- Passsword authentication changed to no  
- permitrootlogon changed to no  
- CHange maxauthtries  
- maxSessions  
  
---  
We don't know what dns service they're using  
- If we need to change something, it's probably in /etc  
- **Unless it's in a docker container**  
  
## How to check if a container is running  
docker container ls  
  
docker exec -it containerID /bin/sh  
docker exec -it {id} ps aux  
  
  
## Reverse shells using web exploits are typically initiated in /var/www  
  
  
### Think about how we're gonna prevent privilege escalation  
- Make it as hard as you can for them to get in  
- They're professionals, they're gonna get in  
- Make it hard for them to priv esc  
  
suid bit, a special to add onto a file or an execuable that allows it to run as a different user  
- Hackers set this to root  
  
He wrwite a script, it makes a list of every installed package on a machine. It checks GTO bins, checks every application with a suid  
  
He checked for what has a suid  
- find / -type f -perm -4000 2>/dev/null  
- This displays everything with suid  
- He showed us GTFObins  
- It compares the data from find, and looks for articles with known exploits on how to abuse it  
- If something pops up  
- Best chance, take off the suid  
- Take it off with  
- Chmod -s {name of service}  
- use -s to run as a different user with privileges, doesn't have to be root.  
  
## Creating a baseline  
  
  
  
  
## Router  
  
MAKE A BACKUP OF YOUR ROUTES  
make it sticky (stickybit)  
- If anyone tries to delete that file, and if they're not the owner, it won't delete  
- ASK ABOUT STICKY BIT  
- Check documentation, find where backups are stored  
- Assign a sticky bit  
- Copy those backups, save them on the backup server, and somewhere in the router  
  
  
  
## DNS  
  
You can make DHCP talk to DNS so that even if an IP changes, DNS updates to prevent problems  
- An attacker will take down DNS  
  
Take all DNS entries and add them to /etc/hosts  
- That has to be done manually on each machine  
- It's like making a local DNS cache  
- This can be automated.....sshpass  
- ssh () <echo "text" >> /etc/hosts  
  
If the people attacking us are the same people who are hosting this, this is a whitebox environment, they can quickly find anomalies.  
  
  
## What to do at the start  
**NMAP OURSELVES**  
- Find out what you're running  
- nmap 192.168.t.0/24 -T5  
- This shows what everyones running  
- **Then do an aggressive scan on yourselves**  
- nmap -A -p- -sV -oN scan.txt  
- oN sends it to a text file  
  
bg  
fg  
jobs - to see everything  
  
Use /var/log to find attempted ssh connections  
- Every service has some sort of logging, we need to figure out how to get it.  
Logs to think about  
- A successful login is different from a login attempt  
- Authentication success log (depends on service)  
- Attempted login (think bruteforce)  
- Configuration changes  
  
  
sudo systemctl status ssh  
- We'll see active sessions  
- Logs  
  
We can use this with other services too

---

You need to monitor the amount of resources that being used

  

You need to monitor all users currently logged into the router

  

You need to monitor active running interfaces