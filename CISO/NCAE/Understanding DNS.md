### What the hell is:
- DNS Caching
- Authoritative name serving
- Recursive Resolution
- Authoritative DNS
- Recursive Queries
- DNSSEC
- Split-horizon DNS
- DNS Forwarder
- Forward Lookup Zone
	- FQDN --> IP
- Reverse Lookup Zone
	- IP --> FQDN
	- Often used for email servers
- Unbound (DNS Software)
	- Secure, Privacy-Focused, high-performance recursive DNS.
	- Modern alternative to BIND
- DNS-over-TLS 
- DNS-over-HTTPS
- QNAME minimization
- PowerDNS (DNS Software)
	- Supports SQL Databases for managing DNS Records
	- Used by large scale cloud providers
- TLD Name Server
- NSD (DNS Software)
	- lightweight, no recursive resolution, optimized for authoritative DNS
- Zone Transfer

## **Why Are There So Many DNS Server Options?**

There isn't a **one-size-fits-all** DNS server because different **environments** have different **needs**:

- **Home users & small networks** → `dnsmasq`
- **Public authoritative DNS (ISPs, hosting providers)** → `BIND`, `PowerDNS`, `NSD`, `Knot`
- **Fast recursive resolution** → `Unbound`, `BIND`
- **Cloud & Kubernetes** → `CoreDNS`
- **Database-backed DNS management** → `PowerDNS`

## **1️⃣ Learning Curve for Common DNS Software**

|**DNS Software**|**Ease of Learning**|**Why?**|
|---|---|---|
|**dnsmasq**|⭐⭐ (Easy)|Simple config, lightweight, best for local caching & DHCP.|
|**Unbound**|⭐⭐⭐ (Medium)|Recursive-only, good documentation, secure by default.|
|**CoreDNS**|⭐⭐⭐ (Medium)|Modular plugin system, easy for Kubernetes users.|
|**PowerDNS**|⭐⭐⭐⭐ (Hard)|Uses SQL-based backends, good for large-scale DNS.|
|**NSD / Knot**|⭐⭐⭐⭐ (Hard)|Authoritative-only, optimized for speed and TLDs.|
|**BIND**|⭐⭐⭐⭐⭐ (Challenging)|Most powerful but has a steep learning curve due to its complexity.|

### **Estimated Time to Become Comfortable**

- **dnsmasq:** **1-3 days** (basic setup, caching, DHCP).
- **Unbound/CoreDNS:** **1-2 weeks** (recursive resolver, security, DNS-over-TLS).
- **BIND/PowerDNS:** **1-3 months** (complex authoritative setups, advanced security, views, DNSSEC).

## Reverse Lookup Zones
Network ID backwards 
1.56.168.192.in-addr.arpa
- pointer record (PTR)
- HOST= Server IP
- FQDN (Backwards)
*Required for mail servers*


