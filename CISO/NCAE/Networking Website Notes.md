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



-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-