## Pi 4 Environment

1. Wireguard / Tailscale
2. DDNS
3. WARP
4. Vault Warden
	1. **For updating Vault Warden**: cd /opt/vaultwarden
			docker compose pull
			docker compose up -d
			docker image prune -f
5. Book/Audiobook server
6. Casa OS
7. [Pi-Hole](https://pi-hole.net/)
8. Reverse-Proxy?
9. Jellyfin?  (Book server)
10. Plex. radarr, sonarr, seerr, nextcloud, kuma?
11. Grafana? Home Assistant? Kasm?
12. 
13. syncthing 
	1. Continuous File Synchronization Program between two or more computers in real time. 
14. Remmina
	1. Remote Desktop Client software

###### Pi 4 Specs
![[Pi_4_Specs.jpg]]

##### **Security**
For Vaultwarden, I would be extra careful. It already has its own login, but since it is a password manager, I would still consider additional restrictions such as Cloudflare Access, country restrictions, device policies, or at least strong Cloudflare security rules. Some mobile/app clients may not like Access in front of Vaultwarden, so you would need to test that specific case.


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
	* A solution proposed, is to have a web server running with two buttons. They're web scripts. Since the pi is on the LAN, the script would execute and could power on or power off the mini PC from a button. Could be the safest option since there's no SSH access.
	* But would it be better to have shell access??
		* What happens when I need to update the software? Should that just be a script too?
		* What if it breaks while I'm not home?
	* It suggested to use WARP to connect to proxmox from the mini PC
* Consider using this method to make backups of my passwords from Vault Warden, encrypt them, then send a copy to my google drive
	* **Remote Backup**: rclone copy /opt/vaultwarden-backup-2026-07-02.tar.gz.gpg gdrive:Vaultwarden-Backups
	* **To encrypt**: gpg -c /opt/vaultwarden-backup-$(date +%F).tar.gz
	* **To decrypt:**: gpg -o vaultwarden-backup-2026-07-02.tar.gz -d vaultwarden-backup-2026-07-02.tar.gz.gpg
	* It should also delete old backups from the pi after uploading, and possible delete old backups on the google drive as well.