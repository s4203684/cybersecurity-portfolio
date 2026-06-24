# Room: [Introduction to EDR]
**Path:** SOC Level 1
**Date:** 24/06/2026
**Status:** Completed

---

## What This Room Was About
EDR is a security solution that monitors endpoints for suspicious activity, collects detailed telemetry, and presents it to a SOC analyst so they can investigate and respond to threats.

---

## Key Concepts Learned
1.EDR Agent — software installed on an endpoint that constantly observes and reports all activity back to the console

2.EDR Console — the brain of the EDR system; receives telemetry from agents, runs machine learning and complex logic to determine real threats vs false positives, and presents everything to the SOC analyst

3.Telemetry — the complete picture of everything that happened on an endpoint; all logs, all events, and the full chain of activity — not just what triggered the alert

4.AV vs EDR — AV checks files against known signatures only; EDR monitors behaviour continuously and catches suspicious activity even when no signature exists

5.Three Pillars — Visibility (full picture of what happened), Detection (identifies threats using multiple techniques), Response (take action from within the console)

6.Five Detection Techniques — Behavioral Detection, Anomaly Detection, IOC Matching, MITRE ATT&CK Mapping, Machine Learning

7.Response Actions — Isolate Host, Terminate Process, Quarantine File, Remote Access, Artefacts Collection

---

## Tools Used
| Tool | What I Used It For |
|CrowdStrike Falcon|Used as the example EDR to demonstrate console, process trees, detections, and RTR|
| | |

---

## Commands / Syntax to Remember
```bash
# No CLI commands in this room — EDR is console-based
```

---

## One Thing That Confused Me (and how I figured it out)
Telemetry felt like it only meant the events that triggered an alert. I figured out it's actually the complete picture  everything that happened on the endpoint before, during, and after the alert, including the full chain of events.

---

## One Thing I Want to Dig Deeper On
1. Fileless malware- how exactly does an attack happen entirely in memory without touching the disk, and how does ML detect it when there's no file to scan?

2. What ere those IOC

3. What is C2 server or this term actually is.

---
