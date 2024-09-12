# Pre Assessment Quiz
## Download Global Protect if needed
global protect VPN client
- https://secure.csusb.edu/global-protect/portal/portal.esp
- Only needed if you're not connected to eduroam

## Cyberlab
Then go to cyberlab.csusb.edu
- Select HTML5 at the top
- Coyote ID and Password

### Questions to the quiz are on canvas

# Answers

## Step 1
~ ifconfig
	- 10.0.0.34

The Ubuntu server is on 172.16.1.5
We need to change networks

~ sudo ifconfig eth0 172.16.1.3

ping the ubuntu server to confirm we're on the same network
~ ping 172.16.1.5

## Step 2
Go to the web address and take the flag
* *Open browser and go to 172.16.1.5*
* Get the flag

## Step 3
We need to use FTP
~ FTP 172.16.1.5
~ Name: anonymous
~ Password: *Blank*
ftp> whoami
ftp> pwd
ftp> ls
ftp> get wpcIDg4s.jpg
**From here we should find it on our machine**

## Step 4
SSH into server     Ubunutu machine
~ ssh user1@172.16.1.5
**User name and password**
~ ls
~ cd images/
~ pwd    

**Opens another terminal**  Kali machine
~ cd Desktop/
~ scp user1@172.16.1.5:/home/user1/images/* .  **Period saves it in the working directory**

## Step 5
Upload pictures to canvas
Windows + shift + s
*Or*   (Harder way)
router is 192.168.1.1
Go back to Kali machine
~ sudo ifconfig eth0 192.168.1.3
~ **Credentials**
Now we're going to add a router
~ sudo route add default gw 192.168.1.1
~ nano /etc/resolv/conf
- Get rid of everything above nameserver
![[Pasted image 20240910140941.png]]
* And instead, change nameserver to 8.8.8.8
* ctrl x + ctrl y + enter

Now go to my.csusb.edu
- boom




