
# Why do they matter?
1. We can create timelines
2. They support real-time detection
	- SIEM, XDR (Security focused)
3. Post-incident forensics
4. Compliance
5. Establish a baseline

# What logs exist?

##### Linux Logs

Common places to check for logs: 
- /var/log/auth.log || /var/log/secure  
	- Logs pertaining to Authentication & Security
- /var/log/syslog || /var/log/messages
	- General collection of system logs
- /var/log/apache2 || /var/log/httpd
	- Webserver logs (apache)
- Journald 
	- Systemd logs

systemd = Software that controls most of hte software operating on your operating system. 

journalctl
- Binary used to interface with jouranld
- Only allows you to view logs

Systemctl
- Manages different running services

**Not all systems use systemd**
- Some use init.d or something else

##### Windows
Event viewer is your friend
Win + R -> eventvwe.msc
%SystemRoot&\System32\winevt\Logs\
IIIS logs in %SystemDrive%\inetpub\logs\LogFiles\
Application and service Logs in C:\Program Files\*

*There's advanced tools you can sue like **Chainsaw** to parse through Windows event logs*

# Finding Failed Login Attempts
<p>Linux: Find Failed login attempts </p>
grep "Failed password" /var/log/auth.log
	- We can also add "wc -l" at the end

<p>Windows: Find failed login attempts</p>
Get-WinEvent -FilterHashtable
@{LogName='Security' ; ID=4625} -MaxEvents 20
- **Alternative output**:
- Instead of:  -MaxEvents 20
- It's:  -ErrorAction SilentlyContinue).count 

# Finding Successful Logins
<p>Linux: Find successful logins</p>
grep "Accepted" /var/log/auth.log

<p>Windows: Find failed login attempts</p>
Get-WinEvent -FilterHashtable
@{LogName='Security" ; ID=4624} -MaxEvents 20

# Finding Privileged Execution
<p>Linux: Find privilege escalation</p>
`grep "sudo .*COMMAND" /var/log/auth.log`

<p>Windows: Find failed login attempts</p>
Get

# Source IP Analysis
<p>Linux: Find source IPs for failed logins</p>
grep "failed password" ./auth.log | awk '{print $(NF-3$}'


# Auditing Account Modification
Linux: Find user account modifications


Windows: Find user account modifications


# Auditing Brute Force Attempts
Linux: Look for brute force attempts


Windows: Look for brute force attempts