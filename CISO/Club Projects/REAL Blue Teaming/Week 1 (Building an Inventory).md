
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