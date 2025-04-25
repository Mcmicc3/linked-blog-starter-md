
# Configuring SSSD
0. Preconditions (check these first)
	1. Firewall ports: Outbound UDP/TCP 88 (Kerberos), TCP 389 (LDAP/GC 3268), TCP 445 (SMB), TCP 135 (RPC), plus high RPC dynamic ports 49152‑65535, must be open to DCs.
	2. chronyc sources *Make sure time is within 5 minutes of DC*
	3. dig +short ldap.tcp.dc.msdcs.NAVSEA.mil     (**Only works if it returns a DC SRV Record**)
1. Join the domain with **realmd**
2. Harden & tune **/etc/sssd/sssd.conf**
``` ini
[sssd]
services = nss, pam, sudo
domains  = corp.example.com
# Cache credentials for 7 days so laptops survive VPN drops
cache_credentials = True
offline_credentials_expiration = 7

[domain/corp.example.com]
id_provider          = ad
override_homedir     = /home/%u@%d
# map AD “Domain Users” → Linux 10000‑... range
ldap_id_mapping      = True  
fallback_homedir     = /home/%u
access_provider      = ad
#ad_gpo_access_control = enforcing      # Optional: obey AD Logon Rights GPOs
#ad_gpo_ignore_unreadable = True
# OR use simple allow/deny lists:
simple_allow_groups  = linux-login
# Pull sudo rules from AD (if you publish them):
sudo_provider        = ad

```

	1. Then 
sudo chmod 600 /etc/sssd/sssd.conf
sudo systemctl enable --now sssd


4. PAM / NSS glue (one‑liner)
	1. sudo systemctl reload sssd

5. Restrict who can log on
	1. Add AD groups to `simple_allow_groups` (as above) and reload: sudo systemctl reload sssd
	2. Or, If your SSSD is ≥ 2.0 (RHEL 8+), uncomment:
``` init
access_provider = ad
ad_gpo_access_control = enforcing

```

7. Test
	1. ssh someuser@corp.example.com@localhost
	2. id someuser@corp.example.com
8. Template for the rest of the fleet


## Next steps
1. Publish **sudo** rules in AD (`CN=SUDOers,OU=Linux,DC=corp,DC=example,DC=com`) so SSSD delivers least‑privilege elevation.
2. Automate host firewalls (`firewalld –‑permanent --add-rich-rule`) to accept only AD ports.
3. Use **Ansible** or **Foreman** to roll identical configs and monitor SSSD health.


# Prompts
Thank you so much for this very detailed checklist of what I need to get this done. I tried running dig +short _ldap._tcp.dc._msdcs.NAVSEA.mil, but the command didn't produce any output. What do I need to do to receive a DC SRV record? and why do I need one? 
- Running a local version of this worked
- dig @192.168.1.18 +short _ldap._tcp.dc._msdcs.NAVSEA.mil SRV

Excellent, running dig @10.25.30.11 +short _ldap._tcp.dc._msdcs.NAVSEA.mil SRV worked just fine for me and produced the expected output. I will assume at this point that my preconditions are good. I forgot to mention, I'm doing a student project that is inspired by a network topology given by Representatives of NAVSEA. Right now, I'm only working local with no interest of connecting SSSD to any real and external NAVSEA servers. This is simply a student project.

Moving onto step 2: joining the domain with realmd.
I was able to discover the AD environment, but I'm curious to know in detail what the steps mean in part 2, where you're suggesting to join the domain. Can you explain to me what's happening so that I may make edits to the command in a way that reflects the environment I'm working in?