# Wireshark Packet Analysis

## Safety
Capture only your own isolated lab traffic. Use dummy FTP credentials. Never publish credentials or unredacted packet captures.

## Start a capture
1. Start Wireshark in Kali.
2. Select the Host-Only interface connected to the lab (verify with `ip -br addr`).
3. Start capture.
4. Generate only the intended lab traffic.
5. Stop capture and save as `task2-lab-capture.pcapng`.
6. Review and sanitize before sharing.

## HTTP
Display filters:
```text
http
tcp.port == 80
```
Record request method, host/path only if non-sensitive, response code and packet numbers. Do not publish cookies, authorization headers or session tokens.

## FTP
Display filters:
```text
ftp
tcp.port == 21
```
Traditional FTP is unencrypted. In an isolated lab, use dummy credentials only. Explain that USER/PASS commands may be visible in the control channel. Redact all credential values from screenshots and reports; never include recovered passwords in GitHub.

## DNS
Display filters:
```text
dns
dns.qry.name
```
Record query name, query type, response and resolved address. Avoid capturing unrelated personal browsing.

## SYN packet observation
Display filter:
```text
tcp.flags.syn == 1 && tcp.flags.ack == 0
```
A SYN packet without ACK is commonly the first step of a TCP connection. A single SYN is not evidence of a SYN flood. Look for a sustained abnormal pattern and compare with the controlled lab activity.

## Controlled SYN-flood analysis
Only if explicitly required and permitted, use a brief, low-rate simulation against the isolated Metasploitable2 VM, never a public/third-party target. Keep it isolated and stop immediately if the VM/network becomes unstable. If a traffic-generation command is required by the instructor, use their approved parameters; this repository intentionally does not prescribe a high-volume flood command. You can instead analyze a supplied sample PCAP and clearly state that no attack was launched.

## Analysis record
- Capture interface:
- Source/destination:
- Protocol:
- Display filter:
- Frame numbers:
- Observed fields:
- What the packets indicate:
- Sensitive data redacted?:
- Capture filename:
