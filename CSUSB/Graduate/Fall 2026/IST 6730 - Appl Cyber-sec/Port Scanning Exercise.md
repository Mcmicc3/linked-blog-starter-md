![[Pasted image 20260923192320.png]]

![[Pasted image 20260923192349.png]]

#### Screenshots to capture
**Setup (Activity 5.1, Part 1)**

1. `ifconfig` on Metasploitable showing its IP — this is your target address, referenced by every later step.
2. `ip a` on Kali showing its lab-network address (the 10.10.10.x interface), to establish both machines are on the same isolated network.

**Port scan (Activity 5.1, Part 2)**  
3. Basic `nmap <target>` output — the default scan of the top 1000 ports.  
4. `nmap -O -p 1-65535 <target>` output — the full-range scan with OS detection. This is your most important evidence shot; it answers "which additional ports showed up" and "which OS/version." If it scrolls past one screen, take two overlapping screenshots or pipe to a file and screenshot that.

**Fingerprinting (Activity 5.2)**  
5. `nmap -O <target>` with the OS-detection result visible — the fingerprint guess, "Running," and "OS details" lines.  
6. A scan of a _second_ device (your router, or Kali scanning itself) — needed for step 3, which asks you to repeat against another target.

**Metasploit wmap (Activity 5.3)**  
7. `msfconsole` started with the `load wmap` confirmation.  
8. The `wmap_sites -a` and `wmap_targets -t` commands showing the target added.  
9. `wmap_run -e` in progress or completed.  
10. `wmap_vulns -l` output — the findings table.

**Optional but strong**  
11. A Wireshark capture during the scan (the exercise's third objective mentions "capture packets"), showing the SYN packets fanning out across ports. This directly demonstrates the scan mechanism rather than just its result.


#### Memo Structure
PORT SCANNING ANALYSIS — Activity 5.1–5.3
Name | Course/Section | Date

1. Objective
   One or two sentences: what the exercise set out to do
   (scan a vulnerable host, fingerprint its OS, run a
   Metasploit vuln scan).

2. Lab Environment
   - Scanner: Kali Linux, IP ___
   - Target: Metasploitable 2, IP ___
   - Network: isolated host-only (10.10.10.0/24)
   [Screenshots 1, 2]

3. Port Scan Findings (5.1)
   - Default scan: summarize open ports/services
   - Full scan (-p 1-65535): which ports appeared that the
     default scan missed, and why that matters
   - Answer the posed question: "Did you identify all open
     ports?" — explain why the default top-1000 scan does not.
   [Screenshots 3, 4]

4. OS Fingerprinting (5.2)
   - Reported OS and version
   - Does it match the actual target? (Metasploitable = very
     old Ubuntu / Linux 2.6 kernel)
   - Second-device result
   - Analysis question: what defeats fingerprinting?
     (firewalls dropping probes, limited open ports, TTL/stack
     obfuscation, patched or uniform stacks)
   [Screenshots 5, 6]

5. Metasploit wmap Scan (5.3)
   - Steps run and target configured
   - Vulnerabilities reported by wmap_vulns
   [Screenshots 7–10]

6. Analysis & Conclusion
   - What the three tools revealed in combination
   - Defensive takeaway: how each finding would be detected
     or prevented on a hardened host