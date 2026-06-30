# Room: SIEM Fundamentals
**Path:** SOC Level 1
**Date:** 30/06/2026
**Status:** Completed

---

## What This Room Was About
This room covered the core fundamentals of SIEM — how logs are generated across different devices in a network, why working with isolated logs is a problem, and how a SIEM solves those problems by centralising, parsing, normalising, and correlating logs to detect threats.

---

## Key Concepts Learned

- **Two types of log sources:** Host-centric (Windows, Linux, servers — events happening on the machine itself) and Network-centric (firewalls, IDS/IPS, routers — events happening between machines or to/from the internet)
- **Five problems with isolated logs:** No centralisation, different formats, massive volume, limited context (individual logs can't show the chain of events), and format inconsistency making cross-source analysis nearly impossible
- **The SIEM processing pipeline in order:** Centralisation → Parsing → Normalisation → Correlation → Alerting → Dashboards
- **Parsing vs Normalisation:** Parsing breaks a raw log into individual fields. Normalisation converts all those differently-formatted logs into one consistent standard format across all sources
- **Why normalisation is a hard requirement for detection rules:** Rules rely on specific field-value pairs (e.g. NewProcessName = whoami). If logs aren't normalised, fields have different names across sources and rules miss events entirely
- **Three building blocks of a detection rule:** Log source + Event ID + Field-value pair
- **Alert investigation outcomes:** True Positive (real threat — investigate further) or False Positive (rule needs tuning)
- **Log ingestion methods:** Agent/Forwarder, Syslog, Manual Upload, Port-Forwarding

---

## Tools Used
| Tool | What I Used It For |
|---|---|
| SIEM (conceptual) | Understanding the full log processing and alerting pipeline |
| Windows Event Viewer | Understanding how Windows logs events with unique Event IDs |

---

## Commands / Syntax to Remember
```bash
# Linux log locations covered in this room
/var/log/httpd        # HTTP request/response and error logs
/var/log/cron         # Cron job events
/var/log/auth.log     # Authentication-related logs (Debian/Ubuntu)
/var/log/secure       # Authentication-related logs (CentOS/RHEL)
/var/log/kern         # Kernel-related events
/var/log/apache       # Apache web server logs (alternate location)
/var/log/httpd        # Apache web server logs (CentOS/RHEL)
```

---

## One Thing That Confused Me (and how I figured it out)
I forgot the term **normalisation** even though I understood the concept — I knew it meant converting different log formats into one consistent format, but the word itself didn't come to me immediately. I went back and re-read that section and it clicked. The fix: always learn the precise term alongside the concept, not just the idea.

---

## One Thing I Want to Dig Deeper On
How to install and configure a log forwarder agent (like Splunk Universal Forwarder) on my own machine and point it at a SIEM instance — seeing the pipeline work in practice, not just in theory. This will come up in the Splunk rooms ahead.

---
