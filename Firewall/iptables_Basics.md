# Linux Firewall Basics with iptables

**Warning:** Apply these rules only to your isolated lab VM. Incorrect INPUT policies can disconnect remote access. Keep VirtualBox console access available and understand each rule before applying it.

## Inspect current rules
```bash
sudo iptables -L -n -v
sudo iptables -S
```

## Example: allow loopback and established traffic
```bash
sudo iptables -A INPUT -i lo -j ACCEPT
sudo iptables -A INPUT -m conntrack --ctstate ESTABLISHED,RELATED -j ACCEPT
```

## Example: allow a specific service port
For a lab demonstration, allow HTTP:
```bash
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
```
Only add ports needed for your test. Add an explicit rule for any management access you need before changing the default policy.

## Example: deny a specific port
```bash
sudo iptables -A INPUT -p tcp --dport 23 -j DROP
```
This example blocks inbound Telnet on the machine where the rule is applied. Confirm the service and test target first.

## Demonstrate and verify
1. Record the initial rules with `sudo iptables -L -n -v`.
2. From Kali, scan only the authorized lab VM and record the relevant port state.
3. Add one rule to the target VM.
4. Repeat the same scan from Kali.
5. Compare results and explain the change. A filtered/closed result depends on the service and firewall response.
6. Record the rule counter and screenshot.

## Remove the demonstration rule
List numbered rules:
```bash
sudo iptables -L INPUT --line-numbers -n
```
Delete the correct rule by its number:
```bash
sudo iptables -D INPUT <RULE_NUMBER>
```
Do not flush all rules or set a default DROP policy unless you have a complete recovery plan and console access.

## Evidence
- Before rules:
- Exact rule added:
- Before scan output:
- After scan output:
- Rule counter:
- Cleanup performed:
