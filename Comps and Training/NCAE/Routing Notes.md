## Mikrotik Router notes

![[Pasted image 20250219152149.png]]
Changes will be applied to the blue router

##### Default credentials
Login: admin
Password: {Blank}

*It should prompt you to create your own password*

### How to do initial configuration
``` mikrotik
[admin@MikroTik]`  > /ip address print
```
- Tells you what IP addresses are assigned to your device
- Expect nothing to output during first installation


``` mikrotik
>  /interface print
```
- Should display ethernet ports
- Name examples: ether3, ether4, lo

###### Assigning ip addresses
``` MikroTik
> ip address add address=172.20.213.1/16 interface=ether3
```
- Assigns an external IP to ether3
- Confirm success with > ip address print

##### Ping
``` Mikrotik
/ping 172.20.0.2
```
- Expect it to ping continuousl 
- Probably ctrl + c to close
- If there's a problem, you'll see a status of timeout on the far right
 ![[Pasted image 20250219160554.png]]
#### Confirming netplan from Ubuntu machine
``` bash
~/ sudo nano /etc/netplan/01-network-manager-all.yaml
```
- Add a static IP
- He typed out everything underneath *renderer*
![[Pasted image 20250219162405.png]]
- Afterwards we need to apply these setting changes

``` bash
~/ sudo netplan apply
```

*This brings up the internal connection to the router*
- We're still on ubuntu

``` bash
~/ systemctl status apache2
# Checks the status of apache2, it'll be inactive

~/ sudo systemctl restart apache2
# Status should change to active
```

*We've successfully gotten the server up and running on the workstation. It's now time to configure the routing*

**You can do the routing from the command line with this particular router.**
- It comes with a  web interface (Still on Ubuntu)

``` browser
http: {gateway}:8080
- Logs us into the web interface of MikroTik
```

![[Pasted image 20250219164321.png]]

- Note that your static routes are already configured, however, we haven't configured the gateway

![[Pasted image 20250219164408.png]]
- *On the day of the competition, we'll be given a router that will route us to the internet. This is where we enter it. They'll also provide us with some external DNS servers*

**Underneath the Local Network section, we want to Bridge all LAN ports and enable NAT**

![[Pasted image 20250219164618.png]]
- This allows traffic to flow from 172.20 (External router) - 192.168.213.1 (GW)
- Save configurations

#### Now we need to focus on Port Mapping
Port mapping interface
![[Pasted image 20250219164816.png]]

Hit the new button:
- Add description
- Add port (80)
- Add address of Ubuntu web server
- Add listening port (80)

You can add TCP and UDP support for port 80 by adding a new port mapping
![[Pasted image 20250219164957.png]]
- Save

This should give us points for the scoreboard.

#### Moving back to Ubuntu machine....
###### We need to update our HTTP data
```Bash
~/ sudo vim /var/www/html/index.html
```
- You're gonna see the web page displaying team 0, you need to update it with the correct team #

**We've successfully configured routing, ports, services, and html data**

#### Moving back to the MikroTik router

This shows the routing from the internal to the external
``` MikroTik
> ip route print
```
![[Pasted image 20250219165537.png]]
- You can quickly see if somebody added a route

*You can add multiple addresses to the same interface*
- Sometimes by mistake, or by mal intent

*You can fix this with remove*
``` Mikrotik
> /ip address remove 2
# 2 Represents the entry number, notice the number on the far left
```
![[Pasted image 20250219165746.png]]

*This prints what services are currently running in terms of access*
- IT WOULD BE A GREAT IDEA TO TAKE SNAPSHOTS OF THIS AS WE'RE SETTING THINGS UP TO GET A BASSLINE OF NORMAL SERVICES
``` MikroTik
> /ip service print
# Shows you the service name, and port it's running on
```
![[Pasted image 20250219165913.png]]

- Notice how some services like api-ssl shows no certificate. This is what happens if we test it
![[Pasted image 20250219170119.png]]
**Keep in mind not to log into things using regular port 80**
- I think if it has a certificate it uses https by default? Confirm.
- *He called this a spoiler from red team* 

**Learn how to ssh into a router**

#### winbox
- Utility tool
- Has nothing to do with Windows
- Allows you to log into a MikroTik router

*He suggests to look into the advanced tab for ways to secure and/or break your router*

He also suggests to contact black team leader

**Remember that we'll have to router other services like FTP**