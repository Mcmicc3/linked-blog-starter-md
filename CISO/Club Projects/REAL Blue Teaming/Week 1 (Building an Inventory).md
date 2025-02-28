# Meeting Notes
## Fingerprint Network
ss -tuln
- A more modern version of netstat 
- Shows connections, listening ports, outgoing and ingoing connections


On Linux, the *who* command shows you who's logged into the system
- **THERE IS NO WINDOWS EQUIVILENT**

## Fingerprint Services
Services and processes are different. Serve similar purpose
- A service is persistent between runs and hosts a daemon, or a recurring service
- Run this at the start, see what's normal
- Run it again if you think something's wrong
## How to check for differences
diff command
- Compares two files and will show you the differences

md5sum
- Run a checksum on your backups when they're set and good
- Run it again if you think it's been tampered with
- If you see an issue, run diff

## Make an inventory
He copied all of the Linux commands on each slide and saved them into a script named "inventory.sh"
- vim inventory.sh
- chmod +x inventory.sh
He then separated each line and labeled them so that the output looks pretty. 

# Code (Inventory script)

## Bash
``` Bash

#!/bin/bash

# Function to print section headers with consistent formatting
print_header() {
    echo ""
    echo "===== $1 ====="
}

# Function to print subsection headers
print_subheader() {
    echo "== $1 =="
}

# Function to print a separator line
print_separator() {
    echo "----------------------------------------"
}

# Main script starts here
print_header "System Inventory"

print_subheader "Hostname and Time"
echo "Hostname: $(hostname)"
echo "Date and Time: $(date)"
echo "Operating System: $(cat /etc/os-release | grep PRETTY_NAME | cut -d'"' -f2)"
echo "Kernel Version: $(uname -r)"
print_separator

print_subheader "Network Information"
echo "IP Addresses:"
ip addr | grep "inet " | awk '{print $2}' | cut -d/ -f1
echo ""
echo "Network Connections:"
ss -tuln
print_separator

print_subheader "User Information"
who
echo ""
echo "Human users (UID >= 1000):"
awk -F: '($3 >= 1000 && $3 != 65534) {print "Username: " $1 ", UID: " $3 ", Home: " $6}' /etc/passwd
print_separator

print_subheader "Service Information"
if command -v systemctl &> /dev/null; then
    systemctl list-units --type=service --state=running | grep ".service"
else
    service --status-all | grep "+"
fi
print_separator

print_subheader "Process Information"
ps aux
print_separator

echo ""
echo "System inventory completed at $(date)"
```

## Powershell (PS1)
``` powershell
# Windows System Inventory Script 

# Function to print section headers with consistent formatting 
function Print-Header { 
	param ([string]$title) 
	Write-Host "`n===== $title =====" -ForegroundColor Cyan 
} 

# Function to print subsection headers 
function Print-SubHeader { 
	param ([string]$title) 
	Write-Host "`n== $title ==" -ForegroundColor Green 
} 

# Function to print a separator line 
function Print-Separator { 
	Write-Host "----------------------------------------" -ForegroundColor DarkGray 
} 

# Main script starts here 
Print-Header "System Inventory" 

# Get system information 
$computerSystem = Get-CimInstance -ClassName Win32_ComputerSystem $operatingSystem = Get-CimInstance -ClassName Win32_OperatingSystem 

Print-SubHeader "System Information" 
Write-Host "Hostname: $($env:COMPUTERNAME)" 
Write-Host "Date and Time: $(Get-Date)" 
Write-Host "Operating System: $($operatingSystem.Caption) $($operatingSystem.Version)" 
Write-Host "Manufacturer: $($computerSystem.Manufacturer)" 
Write-Host "Model: $($computerSystem.Model)" 
Print-Separator 

Print-SubHeader "Network Information" 
Write-Host "IP Addresses:" 
Get-NetIPAddress | Where-Object {$_.AddressFamily -eq "IPv4"} | 
	ForEach-Object { Write-Host " $($_.IPAddress) - $($_.InterfaceAlias)" } 
Print-Separator 

Print-SubHeader "Network Connections" 
$connections = Get-NetTCPConnection -State Listen 
foreach ($conn in $connections) { 
	$process = Get-Process -Id $conn.OwningProcess -ErrorAction SilentlyContinue
	Write-Host "Port $($conn.LocalPort) - Process: $($process.Name)" 
} 
Print-Separator 

Print-SubHeader "User Information" 
Write-Host "Local users:" 
Get-LocalUser | ForEach-Object { 
	Write-Host " Username: $($_.Name)" 
	Write-Host " Enabled: $($_.Enabled)" 
	Write-Host " Last Logon: $($_.LastLogon)" 
	Write-Host "" 
} 
Print-Separator 

Print-SubHeader "Running Services (Top 20)" 
Get-Service | Where-Object {$_.Status -eq "Running"} | 
	Select-Object -First 20 |
	ForEach-Object {
		Write-Host " $($_.DisplayName) - $($_.Name)" 
	} 
Print-Separator 
Write-Host "`nSystem inventory completed at $(Get-Date)" -ForegroundColor Yellow
```

