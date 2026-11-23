# ApexPlanet Cybersecurity Internship – Task 2
## Network Security & Scanning (Days 13–24)

This repository contains the documentation, practical procedures, report templates and evidence for Task 2.

### Objectives
Learn reconnaissance, port/service scanning, vulnerability scanning, packet analysis and firewall basics.

### Lab scope and safety
- Perform active scans only against systems you own or have explicit permission to test.
- Use the isolated VirtualBox Host-Only lab containing Kali Linux and Metasploitable2.
- Do not use bridged networking or expose Metasploitable2 to the public internet.
- Use fictional/example domains for demonstrations unless you have authorization.
- Do not publish real credentials, private IP details beyond what your mentor permits, or unredacted packet captures.

### Task sections
1. Reconnaissance: WHOIS, Nslookup, Google Dorking, Shodan, ping sweep and banner grabbing.
2. Nmap: TCP SYN (`-sS`), UDP (`-sU`), version (`-sV`) and OS (`-O`) detection; prepare a scan report.
3. Vulnerability scanning: OpenVAS or Nessus Essentials against Metasploitable2; classify findings.
4. Wireshark: HTTP, FTP and DNS capture; understand why unencrypted FTP can expose credentials; analyze a controlled SYN-flood demonstration.
5. Firewall: configure basic `iptables` allow/deny rules and verify the effect with an authorized scan.

### Lab topology
| System | Role | Address |
|---|---|---|
| Kali Linux | Scanner / analyst | `[record actual IP]` |
| Metasploitable2 | Authorized test target | `[record actual IP]` |
| Network | VirtualBox Host-Only | `[record subnet]` |

### Repository structure
- `Documentation/` – consolidated report and evidence checklist
- `Reconnaissance/` – notes and results template
- `Nmap-Scanning/` – commands and scan report template
- `OpenVAS-Vulnerability-Scanning/` – setup notes and vulnerability report template
- `Wireshark-Analysis/` – capture procedures and analysis template
- `Firewall/` – firewall rules and verification notes
- `Screenshots/` – add genuine screenshots
- `Video/` – add demo video link and outline
- `Evidence/` – add sanitized exports and supporting evidence

### Completion status
Mark each activity complete only after performing it and saving evidence. Replace every `[placeholder]` with your actual result. Do not claim a scan, capture, vulnerability, or firewall test that you did not perform.

### Suggested commit
`Add ApexPlanet Task 2 network security and scanning documentation`
