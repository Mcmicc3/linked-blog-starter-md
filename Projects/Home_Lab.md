## Pi 4 Environment

1. Wireguard / Tailscale
2. DDNS
3. WARP
4. Vault Warden
5. Book/Audiobook server
6. Casa OS
7. Pi-Hole
8. Reverse-Proxy?
9. Jellyfin?  (Book server)
10. Plex. radarr, sonarr, seerr, nextcloud, kuma?


###### Pi 4 Specs
![[Pi_4_Specs.jpg]]

## Mini PC Environment

1. Proxmox
2. Kasm
3. File server? / NAS Services?


#### Proxmox Environment
Proxmox host  
|  
+-- Management network  
| - Proxmox web UI  
| - admin SSH  
|  
+-- Lab network  
| - Kali attacker VM  
| - vulnerable Linux VM  
| - vulnerable Windows VM  
|  
+-- Monitoring network  
- Wazuh / Security Onion / Zeek / Suricata




Let's say a few months from now, I decided to buy a Pi 3 and use it as my 24/7 network server. How easy would it be for me to transfer all of the data to the new PI?


# Challenges
* Getting WOL to work for the mini PC
* Remote access? Cloudflare? cloud provider?
* Figuring out how to connect to the old PC as a file server
* Figuring out how to SSH into the Pi from across the network 