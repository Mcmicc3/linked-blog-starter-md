
# Embedded Linux

CPU BSP -> SoC BSP -> Board BSP

SPL: Secondary Program Loader

LPDDR4 Porting: The black box calibrtion

U-Boot: The System Orchestrator

COntroller -> IOMUX

COTS vs SBC/SoM vs Chip Down

Distro's to look into:
1. Buildroot
2. Yocto
3. Binary (Ubuntu/Fedora)
4. Torizon OS

# Prometheus
Hardware:
1. IoT dev boards based on teh ESP32
	1. https://www.espressif.com/en/products/devkits
2. Off the shelf senros (Accelormeter)
3. Output devices
4. PC

SOftware:
1. Prometheus (Collects metrics, queries)
	1. https://prometheus.io/
2. MQTT(mosquito
	1. https://mosquitto.org/
3. Grafana
	1. https://grafana.com/
4. Python / C++


#### Prometheus
Database
Query Engine
Collector (Gets data from whatever it provides)
UI - Used for querying

### Pet Door Sensor
MSA301 Acceleromter -> purple snake chip?? (Microcontroller)
1. Connected the two together, placed it on the door lid to see when it opens
2. Prometheus connects to the controller to collect data
3. Python Code
4. Use Prometheus to query data

### Water Sensor
M5CFlap?? Arduino (C++)
*Why C++?*
- Python interrupter has a lot of overhead (Memory). 
- For Complex systems, we need every bit of ram we can get.
- Arduino has been around for 20 years. Vast libraries to use. 

Sensor is a scale. 
Using Prometheus again. 
Using Grafana too

A lot of M5 products are lego compatible lol

C++ code

### Alerting System
Output device -> Controller (Arduino)
- MQTT + Grafana

MQTT (Receivers + Subscribers)



# Launching Your First Server
Self hosting offers total control over data privacy, customization, and log term cost savings, though it requires managing security and maintenance.

Nextcloud
Wordpress
Vaultwarden
Immic
Jellyfin
Audiobookshelf
Navidrome
https://selfh.st/ (For a list of applications)

Old PCs, low resource compute is enough

##### Static IP Address
It's easier to connect to your home computer, office network, or surveillance camera from anywhere in the world

##### Docker
Make sure that the applciation you are installing has a supported version for your architecture on docker
``` bash
curl -sSL https://get.docker.com | sh
sudo usermod -aG docker $USER `To add your user to the docker group, to allow docker to run without root privilages`
```

Look into WatchTower for automatically updating docker containers

##### Domain Name
You will need a reverse proxy 

##### Reverse Proxy
Improves security, performanc , and reliabiliuty by interccepting traffic at the netwrok edge, handling load balancinb, cching content, and masking the identity of back-end servers.

Acts as a defensive layer, protecting back-end servers by hiding their IP addresses and shielding them form direct attacks like DDoS

Decrypts incoming HTTPS requests and encrypts responses

*nginx proxy manager is helpful*

##### Do we need a domain name?
NO, most applications can run and be accessed without a domain name

Some reuqire it because it may need a SSL certificate for security purposes

A domain name can also be used in place of the IP addresses so that you don't have to remember IP addresses

##### Tailscale
A modern identity based VPN that createss a secure, private mesh network connecting your devices across different locations, making them act as if they're on the same local network, even acrross clouds or on premise

Easy to setup and works with all OSs

You can share your devices with other tailscale users to share connectivity to your server

You can also have tailscale be used as a exit node, handle ssh keys , and use access lists to manage who can access your devices.

``` bash
curl -fsSL https://tailscale.com/install.sh | sh
sudo tailscale up
```

### Launching our first server

Duck DNS - https://www.duckdns.org/
- For a free dynamic DNS hosted on AWS


# GPU Attack Surface
https://www.gould.cx/ted/presentations/
- Multiple slides from gould
https://www.gould.cx/ted/presentations/scale23x/gpu-security.html#5
- GPU talk slides

# Secure Boot: Getting To Know Your Frenemy
*Valuable skill to know because everyone hates it*
##### Frenemy?
A lot of enterprise environments require Rocky Linux with Secure Boot

Cloud VMs

Differing opinions on whether it solves problems

##### What is Secure Boot?

History:
1970s - BIOS
- Bootloader stored in MBR
- Unable to validate trustworthiness
- *Folks figured out how to store programs in the bootloader. The BIOS would run these programs*

2000s - UEFI Specification
- Remote limitations
- Secure Boot added to spec 2006 

Goal:
- Only allow trusted software to be run during boot

**Bootloader diagram**
PK (Platform Key) ecomposes Key Enrollment Key (KEK)
KEK encomposes DB and DBX

![[Pasted image 20260307182624.png]]

DB (Keys allowed)
- Windows Bootloader
- Firmware Updater

DBX (Keys not allowed)

##### Shim
*Minimal bootloader that has been signed by microsoft*
What's inside the shim is the signers key. Because it's in the shim, it's considered trusted. *If it's signed by the shim it's considered trusted*
- Has some connection with Bootloader (GRUB2)

GRUB, Kernel, Kernel modules, fwupdate, all have their own keys.
- They've all been issued by a CA. 

**When does a vendor need to worry about having a shim?**
- When companies have their own kernels

##### How to get a signed SHIM?
- Join the Microsoft Hardware Program (Free)
	- Add EV code signing cert
- SHIM review
	- https://github.com/rhboot/shim-review
	- They're not tied to any communities, such as Microsoft
- Once SHIM is approved by the committee submit to Microsoft for signing
	- Takes about a week
	- CAB file that contains your unsigned SHIM
- Receive back a signed SHIM

##### June 27, 2026
- ***The Microsoft keys for KEK and UEFI from 2011 expire***
- What does that mean?
	- Your current SHIM will still work
		- As long as your firmware is not updated with the new keys from 2023
	- New install media that contains a SHIM signed with the 2023 keys will not work if firmware has not been updated.
- Microsoft has a site with more information and guidance from OEMs

##### Out of Tree Kernel Modules
- If not signed by a trusted CA in the database of keys, it will not be laoded
- Create your own signing key
- Enroll using MOK manager
	- Machine owner key.......
- Use this key for signing you kernerl drivers
**gotchas**
- Need to remember to manually re-sign module affter jern or driver signatures(updates?)

##### Out of Tree Modules
DKMS
- https://wiki.ubuntu.com/UEFI/SecureBoot/DKMS

##### How to see the keys from a VM
``` bash
sudo mokutil --sb-state
SecureBoot enabled
sudo mokutil --pk
sudo mokutil --kek
sudo mokutil --db
sudo mokutil --dbx
sudo mokutil --list-enrolled
``` 
##### Trends
- Requirements int he ENterprise to keep Secure Boot enabled
- Customers in highly regulated industries requiring Securee Boot be enabled
- Cloud compute instances are adding supporting for Secure Boot
- Confidential computing
	- Hardware based Trusted Execution Environment (TEE)

##### Takeaways
- Frenemy?
	- We may not like the current solution but we have to work with it
	- It is becoming a requirement for many environments, including the cloud.
- Is there a better way?
	- Probably
- What is it?
	- We don't know yet
	- Needs to simplify managemenet and not one management to control it all

Linkedin - /mlyoung
https://ciq.com/?st_homepage=var1


