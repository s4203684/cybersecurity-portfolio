# Linux CLI Cheatsheet
*Quick reference for SOC work — update as you learn more*

---

## Navigation
```bash
pwd                        # show current directory
ls -la                     # list all files with details
cd /path/to/folder         # change directory
cd ..                      # go up one level
```

---

## File Operations
```bash
cat filename               # read a file
less filename              # read large files (scroll with arrows, q to quit)
head -n 20 filename        # first 20 lines
tail -n 20 filename        # last 20 lines
tail -f filename           # watch file update live (great for logs)
```

---

## grep — Search Inside Files
```bash
grep "keyword" filename              # find lines with keyword
grep -i "keyword" filename           # case insensitive
grep -r "keyword" /path/             # search recursively in folder
grep -n "keyword" filename           # show line numbers
grep -v "keyword" filename           # show lines WITHOUT keyword
grep -E "pattern1|pattern2" file     # search for multiple patterns

# Real SOC examples
grep "Failed password" /var/log/auth.log      # find failed logins
grep "192.168.1.100" access.log               # find specific IP in logs
grep -i "error" /var/log/syslog | tail -50    # last 50 errors in syslog
```

---

## find — Find Files
```bash
find / -name "filename.txt"           # find file by name
find /var/log -name "*.log"           # find all .log files in /var/log
find / -name "*.conf" 2>/dev/null     # find config files, hide errors
find / -mtime -1                      # files modified in last 24 hours
find / -size +100M                    # files larger than 100MB
```

---

## systemctl — Manage Services
```bash
systemctl status servicename          # check if service is running
systemctl start servicename           # start a service
systemctl stop servicename            # stop a service
systemctl restart servicename         # restart a service
systemctl enable servicename          # start service on boot
systemctl list-units --type=service   # list all services
```

---

## Networking Commands
```bash
ip a                                  # show IP addresses
ip route                              # show routing table
netstat -tulnp                        # show open ports and services
ss -tulnp                             # modern version of netstat
ping 8.8.8.8                          # test connectivity
nslookup domain.com                   # DNS lookup
whois domain.com                      # domain info
```

---

## Log Locations (Linux)
| Log File | What's In It |
|---|---|
| `/var/log/auth.log` | Login attempts, sudo usage |
| `/var/log/syslog` | General system events |
| `/var/log/kern.log` | Kernel messages |
| `/var/log/apache2/access.log` | Web server requests |
| `/var/log/apache2/error.log` | Web server errors |
| `journalctl -xe` | Systemd logs, most recent errors |

---

## Useful Combinations (Piping)
```bash
cat auth.log | grep "Failed" | wc -l        # count failed logins
grep "error" syslog | sort | uniq -c        # count unique errors
cat access.log | awk '{print $1}' | sort | uniq -c | sort -rn
# above: count requests per IP, sorted highest first
```

---
