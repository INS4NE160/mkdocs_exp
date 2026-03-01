# Blue Team Roadmap

The defensive side — learning to detect, investigate, and respond to attacks.

!!! note "How to use this"
    Blue team work is less glamorous than red but arguably more important. Work through each phase in order. The later phases assume you understand how attacks work, so pair this with the red team roadmap.

---

## Phase 1 — Foundations
*You need to understand what normal looks like before you can spot abnormal.*

### Operating System Basics
- [ ] Windows fundamentals (registry, services, event logs, user accounts)
- [ ] Linux fundamentals (syslog, auth.log, cron, processes)
- [ ] File system structure on both OSes
- [ ] How processes and services work

### Networking Fundamentals
- [ ] TCP/IP, DNS, HTTP/S
- [ ] How to read a packet capture
- [ ] Common attack traffic patterns (port scans, brute force, beaconing)
- [ ] Firewalls, proxies, and how traffic is filtered

**Resources:**
- [TryHackMe — Pre-Security Path](https://tryhackme.com/path/outline/presecurity)
- [TryHackMe — SOC Level 1 Path](https://tryhackme.com/path/outline/soclevel1)

---

## Phase 2 — Log Analysis
*Logs are the blue teamer's best friend. Learn to read them.*

- [ ] Windows Event Logs — key Event IDs to know:

    | Event ID | Meaning |
    |----------|---------|
    | 4624 | Successful logon |
    | 4625 | Failed logon |
    | 4648 | Logon with explicit credentials |
    | 4672 | Special privileges assigned |
    | 4688 | New process created |
    | 4698 | Scheduled task created |
    | 7045 | New service installed |

- [ ] Linux logs (`/var/log/auth.log`, `/var/log/syslog`, `journalctl`)
- [ ] Web server logs (Apache/Nginx access logs)
- [ ] Firewall logs
- [ ] Identifying suspicious patterns in logs manually

**Resources:**
- [TryHackMe — Windows Event Logs room](https://tryhackme.com/room/windowseventlogs)
- [YouTube — John Hammond log analysis videos](https://www.youtube.com/johnhammond010)

---

## Phase 3 — Network Traffic Analysis
*Learn to read what's moving across the wire.*

- [ ] Wireshark basics (filters, following streams, exporting objects)
- [ ] Identifying normal vs suspicious traffic
- [ ] Detecting port scans in packet captures
- [ ] Detecting reverse shells in traffic
- [ ] DNS exfiltration basics
- [ ] HTTP vs HTTPS — what you can and can't see
- [ ] Zeek / Suricata basics (IDS/IPS)

**Resources:**
- [TryHackMe — Wireshark rooms](https://tryhackme.com/room/wireshark)
- [TryHackMe — Network Security module](https://tryhackme.com/module/network-security)

---

## Phase 4 — SIEM
*Centralizing logs so you can actually find things at scale.*

- [ ] What a SIEM is and why it exists
- [ ] Splunk basics:
    - [ ] Ingesting logs
    - [ ] Search Processing Language (SPL) basics
    - [ ] Building dashboards
    - [ ] Creating alerts
- [ ] Elastic Stack basics (alternative to Splunk):
    - [ ] Elasticsearch, Logstash, Kibana (ELK)
    - [ ] KQL (Kibana Query Language)
- [ ] Correlation rules — what they are and how to write them
- [ ] Alert fatigue — tuning out false positives

**Resources:**
- [TryHackMe — Splunk rooms](https://tryhackme.com/room/splunk101)
- [Splunk Free Training](https://www.splunk.com/en_us/training/free-courses.html)
- [YouTube — MyDFIR Splunk tutorials](https://www.youtube.com/myddfir)

---

## Phase 5 — Endpoint Detection
*What's happening on the machine itself.*

- [ ] What EDR (Endpoint Detection & Response) is
- [ ] Sysmon — what it logs and why it matters:
    - [ ] Process creation (Event ID 1)
    - [ ] Network connections (Event ID 3)
    - [ ] File creation (Event ID 11)
    - [ ] Registry changes (Event ID 13)
- [ ] Deploying Sysmon with a hardened config (SwiftOnSecurity config)
- [ ] Hunting with Sysmon logs in a SIEM
- [ ] AV evasion from a defender's perspective (what attackers do to bypass AV)

**Resources:**
- [TryHackMe — Sysmon room](https://tryhackme.com/room/sysmon)
- [GitHub — SwiftOnSecurity Sysmon config](https://github.com/SwiftOnSecurity/sysmon-config)

---

## Phase 6 — Threat Intelligence & MITRE ATT&CK
*Understanding adversary behavior at a higher level.*

- [ ] What threat intelligence is (strategic, tactical, operational)
- [ ] MITRE ATT&CK framework:
    - [ ] Tactics vs Techniques vs Sub-techniques
    - [ ] How to navigate the ATT&CK matrix
    - [ ] Mapping real attacks to ATT&CK
- [ ] IOCs (Indicators of Compromise) — hashes, IPs, domains
- [ ] Threat intel platforms (VirusTotal, AbuseIPDB, AlienVault OTX)
- [ ] OSINT for defenders

**Resources:**
- [MITRE ATT&CK](https://attack.mitre.org)
- [TryHackMe — Cyber Threat Intelligence module](https://tryhackme.com/module/cyber-threat-intelligence)

---

## Phase 7 — Incident Response
*Something got through. Now what?*

- [ ] The IR lifecycle (Preparation → Detection → Containment → Eradication → Recovery → Lessons Learned)
- [ ] Triage — determining scope and severity quickly
- [ ] Memory forensics basics (Volatility)
- [ ] Disk forensics basics (Autopsy, FTK Lite)
- [ ] Timeline analysis
- [ ] Writing an incident report

**Resources:**
- [TryHackMe — SOC Level 1 Path](https://tryhackme.com/path/outline/soclevel1)
- [YouTube — 13Cubed forensics channel](https://www.youtube.com/13cubed)

---

## Certifications (when ready)

| Cert | Level | Notes |
|------|-------|-------|
| CompTIA Security+ | Beginner | Solid blue team theory baseline |
| CompTIA CySA+ | Mid | Analyst-focused, highly relevant |
| Blue Team Labs Online | Beginner–Mid | Practical, free tier available |
| BTL1 (Blue Team Labs Level 1) | Mid | Hands-on, well respected |
| GCIH (GIAC) | Advanced | Incident handling, expensive but respected |