# Nmap Practical Guide

**Scope:** Kali Linux scanning the student's own Metasploitable2 VM on VirtualBox Host-Only networking only.

Set a shell variable to avoid mistyping the target:
```bash
TARGET=192.168.56.101
```
Replace this example with your actual Metasploitable2 IP.

## 1. Confirm reachability
```bash
ping -c 4 "$TARGET"
```

## 2. Host discovery
```bash
nmap -sn "$TARGET"
```

## 3. TCP SYN scan
```bash
sudo nmap -sS "$TARGET"
```

## 4. UDP scan
UDP scans can be slow and often return `open|filtered`. Start with a limited lab scan:
```bash
sudo nmap -sU --top-ports 20 "$TARGET"
```
Only expand the port range if required and safe.

## 5. Service/version detection
```bash
nmap -sV "$TARGET"
```

## 6. OS detection
```bash
sudo nmap -O "$TARGET"
```
OS detection is probabilistic and may require at least one open and one closed port. Results can be inconclusive.

## 7. Save output
```bash
mkdir -p ~/task2-evidence/nmap
nmap -sV "$TARGET" -oN ~/task2-evidence/nmap/service-version.txt
sudo nmap -sS "$TARGET" -oN ~/task2-evidence/nmap/tcp-syn.txt
sudo nmap -sU --top-ports 20 "$TARGET" -oN ~/task2-evidence/nmap/udp-top20.txt
```

## 8. Report template
- Target IP and role:
- Lab network:
- Date/time:
- Nmap version:
- Exact command:
- Host status:
- Open ports:
- Service/version:
- OS guess and confidence:
- UDP limitations:
- Interpretation:
- Screenshot/output filenames:
- Recommended defensive action:

Do not scan targets outside your authorized lab. Do not run aggressive scripts or exploitation scripts unless separately authorized.
