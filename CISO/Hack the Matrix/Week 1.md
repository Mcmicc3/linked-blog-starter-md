Reconnaissance

- Collecting information

Learning what normal traffic looks like is vital for staying hidden

- Whatever apps and tools they’re using, use the same

### Suitable tools for reconnaissance

- Nmap
- Wireshark
- Nessus
- FFuF
- Gobuster
- CobaltStrike
    - C2 framework? applies beacons to machines and callback to the C2 or a centralized machine

### Using A1 for Reconnaissance

- Use A1 to help us figure out which flags are better to use with a tool/command
- Don’t fully trust AI
    - Cross-reference AI by RTFM (Read the Fucking Manual)
        - Take the time to learn what the flag does
    - Man pages are a godsend

### Using ChatGPT to Learn Functions of Flags

Cross-referencing by RTFM

man tool, —help command

### Another Reason flags are useful

We aren’t using the tool to its full potential when we use it without flags

- Flags allow you to see service versions
    - Helps you find vulnerabilities
- Make the job as pen tester easier
- -sB ??? -a ????

### nmap commands

nmap -a 10.10.10.1

sudo nmap -O 10.10.10.11

nmap -sV -sC 10.10.10.11