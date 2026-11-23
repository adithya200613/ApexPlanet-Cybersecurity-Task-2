# Reconnaissance Guide

## Purpose
Reconnaissance gathers information about an authorized assessment target before scanning. Passive methods avoid directly probing the target; active methods interact with it.

## Passive reconnaissance
### WHOIS
```bash
whois example.com
```
Record registrar, registration dates and name servers where available. WHOIS privacy/proxy services may hide registrant details. Do not infer ownership from incomplete records.

### DNS lookup
```bash
nslookup example.com
nslookup -type=MX example.com
nslookup -type=NS example.com
```
Record query type, returned records and resolver. DNS results can vary by resolver and time.

### Search-engine research (Google Dorking)
Use search operators only to understand publicly indexed pages. Example safe query:
```text
site:example.com filetype:pdf
```
Do not search for or download exposed passwords, private records or sensitive documents. Report only high-level, non-sensitive observations.

### Shodan
Use Shodan's website/search only for assets you own or have written permission to assess. Record the query, date and high-level service metadata. Do not use results as permission to probe an asset.

## Active reconnaissance – isolated lab only
### Check connectivity
```bash
ping -c 4 <AUTHORIZED_TARGET_IP>
```
### Simple ping sweep
For a small, explicitly authorized Host-Only lab subnet:
```bash
nmap -sn 192.168.56.0/24
```
Replace the example subnet with the actual isolated lab subnet. Do not sweep campus, workplace, ISP or public networks without written authorization.

### Banner grabbing
Against a known open service on your lab target only:
```bash
nc -nv <AUTHORIZED_TARGET_IP> 21
```
Use the actual port appropriate to the service. Record the banner only; do not attempt authentication or exploitation.

## Results template
- Date/time:
- Scope and permission:
- Method:
- Command/query:
- Result:
- Screenshot filename:
- Interpretation:
- Limitations:
