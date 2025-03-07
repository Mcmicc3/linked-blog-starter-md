
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

# Analyzer.sh

``` Bash
#!/bin/bash

# Set default log file and allow command line override

LOG_FILE="${1:-/var/log/auth.log}"

REPORT_FILE="auth_report.txt"

  

# Check if the log file exists

if [ ! -f "$LOG_FILE" ]; then

    echo "Error: Log file $LOG_FILE not found!"

    echo "Usage: $0 [path-to-log-file]"

    exit 1

fi

  

# Create a report file

echo "=================================================================" > $REPORT_FILE

echo "                  LINUX AUTH LOG ANALYSIS                        " >> $REPORT_FILE

echo "=================================================================" >> $REPORT_FILE

echo "Log file analyzed: $LOG_FILE" >> $REPORT_FILE

echo "Generated on: $(date)" >> $REPORT_FILE

echo "=================================================================" >> $REPORT_FILE

  

# 1. Count and show failed password attempts

echo "" >> $REPORT_FILE

echo "******************** FAILED PASSWORD ATTEMPTS ********************" >> $REPORT_FILE

echo "" >> $REPORT_FILE

grep "Failed password" $LOG_FILE >> $REPORT_FILE

FAIL_COUNT=$(grep "Failed password" $LOG_FILE | wc -l)

echo "" >> $REPORT_FILE

echo "Total failed attempts: $FAIL_COUNT" >> $REPORT_FILE

  

# 2. Count and show successful logins

echo "" >> $REPORT_FILE

echo "******************** SUCCESSFUL LOGINS ********************" >> $REPORT_FILE

echo "" >> $REPORT_FILE

grep "Accepted" $LOG_FILE >> $REPORT_FILE

SUCCESS_COUNT=$(grep "Accepted" $LOG_FILE | wc -l)

echo "" >> $REPORT_FILE

echo "Total successful logins: $SUCCESS_COUNT" >> $REPORT_FILE

  

# 3. Find sudo commands

echo "" >> $REPORT_FILE

echo "******************** SUDO COMMANDS EXECUTED ********************" >> $REPORT_FILE

echo "" >> $REPORT_FILE

grep "sudo.*COMMAND" $LOG_FILE >> $REPORT_FILE

  

# 4. List top IP addresses with failed logins

echo "" >> $REPORT_FILE

echo "******************** TOP IPs WITH FAILED LOGINS ********************" >> $REPORT_FILE

echo "" >> $REPORT_FILE

grep "Failed password" $LOG_FILE | awk '{print $(NF-3)}' | sort | uniq -c | sort -nr | head -5 >> $REPORT_FILE

  

# 5. Show activity during night hours (11PM-6AM)

echo "" >> $REPORT_FILE

echo "******************** NIGHTTIME ACTIVITY (11PM-6AM) ********************" >> $REPORT_FILE

echo "" >> $REPORT_FILE

grep -E "^... [0-9]+ (23|0[0-6])" $LOG_FILE >> $REPORT_FILE

  

echo "" >> $REPORT_FILE

echo "=================================================================" >> $REPORT_FILE

echo "                 END OF SECURITY LOG ANALYSIS                    " >> $REPORT_FILE

echo "=================================================================" >> $REPORT_FILE

  

echo "Analysis complete! Check $REPORT_FILE for results."
```

# Analyzer.ps1
``` Powershell
param(
    [string]$LogPath
)

# Create output file
"BASIC WINDOWS SECURITY LOG ANALYSIS" | Out-File -FilePath "report.txt"
"Generated on: $(Get-Date)" | Out-File -FilePath "report.txt" -Append
"----------------------------" | Out-File -FilePath "report.txt" -Append

# Display status messages
Write-Host "Starting Windows log analysis..."

# 1. Show failed logins (Event ID 4625)
"" | Out-File -FilePath "report.txt" -Append
"FAILED LOGINS (Event ID 4625):" | Out-File -FilePath "report.txt" -Append

# Use either specified log file or system security log
if ($LogPath) {
    $failedLogins = Get-WinEvent -FilterHashtable @{Path=$LogPath; ID=4625} -MaxEvents 20 -ErrorAction SilentlyContinue
} else {
    $failedLogins = Get-WinEvent -FilterHashtable @{LogName='Security'; ID=4625} -MaxEvents 20 -ErrorAction SilentlyContinue
}

# Process results
if ($failedLogins) {
    foreach ($event in $failedLogins) {
        # Extract basic info without complex XML parsing for beginners
        "Time: $($event.TimeCreated) | Event ID: $($event.Id) | User: $($event.Properties[5].Value)" | 
            Out-File -FilePath "report.txt" -Append
    }
    "Total failed logins found: $($failedLogins.Count)" | Out-File -FilePath "report.txt" -Append
} else {
    "No failed logins found." | Out-File -FilePath "report.txt" -Append
}

# 2. Show successful logins (Event ID 4624)
"" | Out-File -FilePath "report.txt" -Append
"SUCCESSFUL LOGINS (Event ID 4624):" | Out-File -FilePath "report.txt" -Append

# Use either specified log file or system security log
if ($LogPath) {
    $successLogins = Get-WinEvent -FilterHashtable @{Path=$LogPath; ID=4624} -MaxEvents 20 -ErrorAction SilentlyContinue
} else {
    $successLogins = Get-WinEvent -FilterHashtable @{LogName='Security'; ID=4624} -MaxEvents 20 -ErrorAction SilentlyContinue
}

# Process results
if ($successLogins) {
    foreach ($event in $successLogins) {
        # Extract basic info without complex XML parsing for beginners
        "Time: $($event.TimeCreated) | Event ID: $($event.Id) | User: $($event.Properties[5].Value)" | 
            Out-File -FilePath "report.txt" -Append
    }
    "Total successful logins found: $($successLogins.Count)" | Out-File -FilePath "report.txt" -Append
} else {
    "No successful logins found." | Out-File -FilePath "report.txt" -Append
}

# 3. Show account changes (Event ID 4720 - account creation)
"" | Out-File -FilePath "report.txt" -Append
"ACCOUNT CREATIONS (Event ID 4720):" | Out-File -FilePath "report.txt" -Append

# Use either specified log file or system security log
if ($LogPath) {
    $accountCreations = Get-WinEvent -FilterHashtable @{Path=$LogPath; ID=4720} -MaxEvents 10 -ErrorAction SilentlyContinue
} else {
    $accountCreations = Get-WinEvent -FilterHashtable @{LogName='Security'; ID=4720} -MaxEvents 10 -ErrorAction SilentlyContinue
}

# Process results
if ($accountCreations) {
    foreach ($event in $accountCreations) {
        "Time: $($event.TimeCreated) | New account: $($event.Properties[0].Value)" | 
            Out-File -FilePath "report.txt" -Append
    }
} else {
    "No account creations found." | Out-File -FilePath "report.txt" -Append
}

# 4. Count total events by ID
"" | Out-File -FilePath "report.txt" -Append
"EVENT SUMMARY COUNTS:" | Out-File -FilePath "report.txt" -Append

if ($LogPath) {
    Write-Host "Counting events in file $LogPath..."
    "Failed logins (4625): $($failedLogins.Count)" | Out-File -FilePath "report.txt" -Append
    "Successful logins (4624): $($successLogins.Count)" | Out-File -FilePath "report.txt" -Append
    "Account creations (4720): $($accountCreations.Count)" | Out-File -FilePath "report.txt" -Append
} else {
    Write-Host "Counting events in system Security log..."
    "Failed logins (4625): $($failedLogins.Count)" | Out-File -FilePath "report.txt" -Append
    "Successful logins (4624): $($successLogins.Count)" | Out-File -FilePath "report.txt" -Append
    "Account creations (4720): $($accountCreations.Count)" | Out-File -FilePath "report.txt" -Append
}

Write-Host "Analysis complete! Results saved to report.txt"

```