# Task 2 – Network Security & Scanning
**Internship:** ApexPlanet Software Pvt. Ltd.  
**Timeline:** Days 13–24  
**Student:** Adithya K R  
**Status:** Work in progress – update after completing each practical

## 1. Objective
Learn reconnaissance, scanning and network traffic analysis in an authorized, isolated lab.

## 2. Lab environment
- Hypervisor: Oracle VirtualBox
- Attacker/analysis VM: Kali Linux
- Target VM: Metasploitable2
- Network mode: Host-Only
- Kali IP: `[actual IP]`
- Target IP: `[actual IP]`
- Subnet: `[actual subnet]`
- Date of testing: `[date]`

Keep Metasploitable2 isolated. Do not bridge it to a public or institutional network.

## 3. Reconnaissance
### Passive reconnaissance
Document WHOIS, DNS lookup, search-engine research and Shodan observations only for domains/assets you own or are authorized to assess. Use example.com or a lab-owned domain for demonstrations.
- WHOIS command/result: `[command and sanitized result]`
- Nslookup command/result: `[command and sanitized result]`
- Google Dorking: `[query used against authorized/publicly indexed material; no sensitive data collection]`
- Shodan: `[asset/query and observation; do not probe unauthorized systems]`

### Active reconnaissance
- Ping sweep target range: `[authorized lab subnet]`
- Host(s) discovered: `[actual output]`
- Banner grabbing: `[authorized lab service, command and observed banner]`

## 4. Nmap port and service scanning
Record the exact target and commands. Example commands are in `../Nmap-Scanning/Nmap_Practical_Guide.md`.
- TCP SYN scan: `[command/output summary]`
- UDP scan: `[command/output summary]`
- Service/version detection: `[command/output summary]`
- OS detection: `[command/output summary]`
- Important open ports/services: `[actual results]`
- Interpretation and limitations: `[analysis]`

## 5. Vulnerability scanning
Scanner: `[OpenVAS/GVM or Nessus Essentials]`  
Target: `[Metasploitable2 actual IP]`  
Scan profile: `[profile]`  
Scan date: `[date]`  
Report filename: `[filename]`

| Severity | Count from actual report |
|---|---:|
| Critical | `[count]` |
| High | `[count]` |
| Medium | `[count]` |
| Low | `[count]` |
| Info | `[count, if shown]` |

Discuss the most important findings using the scanner's exact title, affected port/service, evidence, impact and remediation. Do not treat scanner output as proof of exploitability; validate carefully and only in the lab.

## 6. Wireshark packet analysis
Interface: `[interface]`  
Capture date: `[date]`  
Capture file: `[sanitized filename]`

| Traffic | Display filter | What to record |
|---|---|---|
| HTTP | `http` or `tcp.port == 80` | Request/response metadata; avoid publishing session data |
| FTP | `ftp` or `tcp.port == 21` | Control-channel commands; redact any USER/PASS values |
| DNS | `dns` | Query name, type, response and addresses |
| ICMP | `icmp` | Echo request/reply if useful for reachability |
| TCP SYN | `tcp.flags.syn == 1 && tcp.flags.ack == 0` | SYN packet pattern and source/destination |

Explain that traditional FTP sends authentication data without encryption. Never publish recovered usernames/passwords. Use dummy credentials in the isolated lab and redact them in screenshots and reports.

### Controlled SYN-flood analysis
Only perform a low-rate, short, controlled demonstration against your own isolated Metasploitable2 VM, with permission. Do not target public IPs, shared networks or production systems. Record the lab setup, observation in Wireshark, and cleanup. If you cannot safely perform the simulation, document packet-flag analysis from a provided sample capture instead; do not claim to have launched an attack.

## 7. Firewall basics
Platform: `[Linux VM]`  
Firewall tool: `iptables`  
Rules tested: `[describe exact rules]`  
Before/after scan evidence: `[screenshots or sanitized output]`

Example safe starting point is in `../Firewall/iptables_Basics.md`. Apply rules only to the isolated test VM and ensure you understand the SSH/console access implications before changing INPUT policy.

## 8. Findings and conclusion
Summarize only observed results:
- Hosts identified: `[actual]`
- Open ports/services: `[actual]`
- Vulnerability severity totals: `[actual]`
- Packet-analysis observations: `[actual]`
- Firewall verification: `[actual]`
- Limitations/false positives: `[actual]`
- Recommended remediation: `[actual]`

## 9. Evidence index
List screenshot filenames and what each proves in `Submission_Evidence_Checklist.md`.

## 10. Demo video
Video link: `[insert accessible link]`  
Duration: approximately 5 minutes  
Outline: lab scope and topology → Nmap scan → vulnerability report → Wireshark observation → firewall verification → key findings.

## 11. Ethics
All active testing was limited to systems owned by the student or explicitly authorized for testing. Vulnerable lab machines remained isolated.
