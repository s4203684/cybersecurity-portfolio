# SOC Quick Reference
*Ports, protocols, attack types — fill this in as you learn*

---

## Common Ports to Know
| Port | Protocol | Service |
|---|---|---|
| 21 | TCP | FTP |
| 22 | TCP | SSH |
| 23 | TCP | Telnet (insecure) |
| 25 | TCP | SMTP (email) |
| 53 | UDP/TCP | DNS |
| 80 | TCP | HTTP |
| 110 | TCP | POP3 (email) |
| 143 | TCP | IMAP (email) |
| 443 | TCP | HTTPS |
| 445 | TCP | SMB (Windows file sharing) |
| 3306 | TCP | MySQL |
| 3389 | TCP | RDP (Remote Desktop) |
| 8080 | TCP | HTTP alternate |

---

## Attack Types — Quick Reference
| Attack | What It Is | How to Spot It |
|---|---|---|
| Phishing | Fake email to steal credentials | Suspicious sender, urgent language, dodgy link |
| Brute Force | Guessing passwords repeatedly | Many failed logins from same IP |
| SQL Injection | Injecting SQL into web forms | `' OR 1=1` patterns in web logs |
| XSS | Injecting scripts into web pages | `<script>` in user input fields |
| MITM | Intercepting traffic between two parties | ARP spoofing, unusual traffic routes |
| DDoS | Flooding a service with traffic | Massive spike in requests from many IPs |
| Ransomware | Encrypting files for ransom | Mass file modifications, unusual processes |
| Privilege Escalation | Gaining higher permissions | User running admin commands they shouldn't |

---

## Alert Severity Levels
| Level | Meaning |
|---|---|
| Critical | Immediate action required |
| High | Investigate within 1 hour |
| Medium | Investigate within 24 hours |
| Low | Review when time permits |
| Informational | No action needed, just logged |

---

## IOC Types (Indicators of Compromise)
- **IP address** — suspicious source connecting to your network
- **Domain name** — malicious domain being queried
- **File hash** — MD5/SHA1/SHA256 of a known malicious file
- **URL** — specific malicious web address
- **Email address** — sender of phishing emails
- **Registry key** — Windows registry changes by malware

---

## Windows Event Log IDs to Know
| Event ID | What It Means |
|---|---|
| 4624 | Successful login |
| 4625 | Failed login |
| 4648 | Login using explicit credentials |
| 4672 | Admin privileges assigned |
| 4688 | New process created |
| 4698 | Scheduled task created |
| 4720 | User account created |
| 4726 | User account deleted |
| 7045 | New service installed |

---

## Splunk SPL Basics
```
index=main                           # search all logs
index=main "failed password"         # search for keyword
index=main src_ip="1.2.3.4"         # filter by source IP
index=main | stats count by src_ip  # count events per IP
index=main | sort -count            # sort by count descending
index=main earliest=-24h            # last 24 hours only
```
*(Add more as you learn in SOC Level 1)*

---
