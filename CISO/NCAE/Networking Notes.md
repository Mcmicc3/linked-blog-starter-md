What does this mean when people say how does this service effect downstream or upstream?

ifconfig is part of the nettools pacakage
- Be aware that different distros, different versions, don't all have the same commands installed
- ifconfig example

ens18 - showing a network port with no information given to it.

---

### Finding Network configurations on Linux

Kali - /etc/network/interfaces
- We can enter static IP addresses here
- auto eth0
- iface eth0 inet static  *You could also replace static with DHCP*
	- address 172.0.0.1
	- Netmask 255.255.0.0
	- *What is inet????*

**Changes will not apply until you restart the service**
- sudo systemctl restart networking 
	- networking = name of service


---
### Static Configuration in CentOS with ifcfg files

There is **no** /etc/network/interfaces **on CentOS**

We need: ls /etc/sysconfig/network-scripts/
- One file for every interface
![[Pasted image 20250210202651.png]]
- You need to be aware of which interface to configure

**CentOS doesn't have nano, we need vim or vi**
sudo vi /etc/sysconfig/network-scripts/ifcfg-eth0
- You shouldn't see a blank file
![[Pasted image 20250210202933.png]]

You want to delete DHCP under BOOTPROTO to BOOTPROTO=static

You also want to change ONBOOT=NO to ONBOOT=yes

Then we add a line, IPADDR=172.20.{TEAM#}.1
NETMASK=255.255.0.0
:wq
![[Pasted image 20250210203308.png]]

**Now we need to restart the service**: *sudo systemctl restart network*

eth0 = external
eth1 = internal

sudo vi /etc/sysconfig/network-scripts/ifcfg-eth1
**Changes to make**
BOOTPROTO=static
ONBOOT=yes
IPADDR=192.168.{TEAM#}.1
NETMASK=255.255.255.0

sudo systemctl restart network

ip a (**To confirm our work**)

---
### Static Configuration in Ubuntu with Netplan

**Newer versions of ubuntu don't have /etc/network/interfaces**

New versions are using netplan
ls /etc/netplan
- Used for network configuration files
- Looking for .yaml files
- You may or may not find more than one

sudo vim /etc/netplan/01-network-manager-all.yaml
![[Pasted image 20250210204355.png]]
- Be consistent with the spacing in this file

network:
	version: 2
	renderer: NetworkManager
	**ethernets:**
		ens18: 
		addresses:
			- 192.168.(**TEAM#**).2/24   (**Note the - and the space after**)

**This time we're gonna restart netplan**
- systemctl would also work

sudo netplan apply

**This is enough to bring a device online**

---
### Temporary Permanent and Flushing IPs
ip a

~$ ip addr add 192.168.118.3/24 dev ens18 
- **Hitting control A takes you to the front**
- **Hitting control E takes you to the end**

~$ sudo ip addr add 192.168.118.3/24 dev ens18

This command will allow you temporary obtain a second IP address on ens18 
*Note that /etc/netplan/01-network-manager-all.yaml did not change*
- Essentially, it won't survive a restart

*How do we flush temporary IPs if they were added maliciously, or by accident?* through flushing

~$ sudo ip addr flush dev ens18
**This removes both the permanent, and temporary IPs**
Confirm this with ip a
**Note that the netplan etc folder won't get touched**

**Good tech tip**: get things to a working state first, and then have a backup of your configuration settings. 

~$ sudo netplan apply

**Note in regards to Kali**: If you use the ip addr add command, you won't see the added ip if you use the ifconfig. Only *ip a* shows the full list of IPs.  

You can bring back the service with:
~$ sudo systemctl restart networking

---
### Using Networking Service with Netcat

Testing our internal networks

nc is a tool that allows us to collect data from a service

*He's setting up a listening port on a workstation to perform a connectivity test*

{Kali} ~$ nc -l -p 54321
- *Make sure not to pick a port that's commonly used*

{Server} ~$ nc 192.168.118.100 54321
- This is the IP of the workstation
- *Expect it to sit there*
~$ What's up
- *Kali machine will see this on the terminal*

**This idea if primitive**:  Once the service shuts, the port is closed and the service stops. It's time dependent. 

*Now we're exploring sending commands through NC*

{kali} ~$ nc -l -p 54321 -e /bin/bash 
- *listening*
{server} ~$ nc 192.168.118.100 54321
~$ hello
- you get an error, because there is no hello command
- *If you give a command like*: ls /
	- You will see everything in the directory
	- You essentially have a working prompt

**This is a tool often used by attackers to gain access to the filesystem**

#### python
{Kali} ~$ python
``` python
import os
while True:
	os.system("nc -l -p 54321 -e /bin/bash")
			# Hit enter again so it runs
```
- *Expect it to look like nothings happening*

{Server} ~$ nc 192.168.118.100 54321
- Enter any command
*Quits the session*
- ^c

On the code side {kali} we're still in a loop, so it's going to keep running

**Essentially**: You can keep running the same NC command without having to worry about the listening port closing on the workstation, since we're using a python loop

*On the workstation, you have to hit ^z to stop the loop*
