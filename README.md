# Network Reconnaissance & Network Scanning Lab

A comprehensive hands-on cybersecurity reconnaissance and network mapping exercise targeting a live web asset (`networkwalks.com`) and a local LAN environment using a terminal-first methodology.

---

## Tools & Technologies Used
* **Operating System:** Kali Linux
* **Footprinting & OSINT Tools:** 
  * `whois` (Domain registration & registrar analysis)
  * `whatweb` (Web technology fingerprinting)
  * `nslookup` & `dnsrecon` (DNS enumeration & IP resolution)
  * `curl` (HTTP response headers inspection)
  * `wafw00f` (Web Application Firewall detection)
* **Network Scanning:** Zenmap / Nmap (`-sn` Ping Scan)

---

## Project Structure
```text
WK2-Recon-Report/
├── README.md               # Project documentation
├── PT-Report.pdf           
└── screenshots/            # Visual evidence and scan graphs
```

## Key Findings Summary
```text
1. Passive & Semi-Passive Footprinting (networkwalks.com)
Infrastructure Stack: Hosted on HostGator (ns6135.hostgator.com) running an Apache web server.

Content Management System: WordPress (Version 7.1.4) with WordPress Download Manager (3.3.76).

Security & Defenses: Successfully identified active protection behind ModSecurity (SpiderLabs) WAF.

Information Disclosures: Public exposure of the WordPress REST API endpoint (/wp-json/) and exact version numbers, providing a foundational attack surface map.

2. Active Network Discovery (Zenmap Local LAN Scan)
Executed a stealth ping scan (-sn) across the local subnet to map active nodes, verify gateway responsiveness, and chart local device topology.
```
## Usage / Execution
To reproduce the footprinting workflow, run the following commands in your Kali Linux terminal:

```bash
# Domain Registration
whois networkwalks.com

# Web Tech Fingerprinting
whatweb -v networkwalks.com

# DNS Enumeration
dnsrecon -d networkwalks.com -t std

# HTTP Headers Inspection
curl -I [https://networkwalks.com](https://networkwalks.com)

# WAF Detection
wafw00f [https://networkwalks.com](https://networkwalks.com)
```
## Author
Samiullah
