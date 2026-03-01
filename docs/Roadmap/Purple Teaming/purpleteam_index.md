# Purple Team Roadmap

Where offense meets defense — using both sides to make each other better.

!!! warning "Prerequisites"
    Don't start here. Complete at least **Phase 1–3 of the Red Team roadmap** and **Phase 1–4 of the Blue Team roadmap** first. Purple teaming only makes sense once you have context on both sides.

---

## What Purple Teaming Actually Is

Red teams attack. Blue teams defend. Purple teams **run the whole cycle deliberately**:

```
Plan attack → Execute attack → Observe what was detected → 
Tune detections → Re-run attack → Repeat
```

The goal isn't just to compromise a system — it's to **build better detections** by understanding exactly how attacks behave and what telemetry they leave behind.

---

## Phase 1 — MITRE ATT&CK Deep Dive
*The common language that red and blue both speak.*

- [ ] Understand the full ATT&CK matrix structure (14 tactics)
- [ ] Learn key techniques in each tactic:
    - [ ] Reconnaissance (T1595, T1596)
    - [ ] Initial Access (T1190, T1566 — phishing)
    - [ ] Execution (T1059 — command line, scripting)
    - [ ] Persistence (T1053 — scheduled tasks, T1547 — registry run keys)
    - [ ] Privilege Escalation (T1548, T1055)
    - [ ] Defense Evasion (T1070, T1027 — obfuscation)
    - [ ] Credential Access (T1003 — credential dumping, T1110 — brute force)
    - [ ] Lateral Movement (T1021 — remote services)
    - [ ] Exfiltration (T1041, T1048)
    - [ ] Command & Control (T1071 — standard protocols)
- [ ] Use ATT&CK Navigator to map and track techniques
- [ ] Map a real-world attack (e.g. a known APT) to ATT&CK techniques

**Resources:**
- [MITRE ATT&CK](https://attack.mitre.org)
- [ATT&CK Navigator](https://mitre-attack.github.io/attack-navigator)
- [TryHackMe — MITRE room](https://tryhackme.com/room/mitre)

---

## Phase 2 — Adversary Emulation
*Running controlled, documented attacks to test your defenses.*

- [ ] Understand what adversary emulation is vs a standard pentest
- [ ] Atomic Red Team:
    - [ ] What it is (pre-built attack simulations mapped to ATT&CK)
    - [ ] Installing and running Atomic tests
    - [ ] Running a test and checking if your SIEM caught it
- [ ] MITRE Caldera:
    - [ ] Setting up Caldera
    - [ ] Running an automated emulation plan
    - [ ] Reviewing what was and wasn't detected
- [ ] Manually emulating a technique and documenting the telemetry it produces

**Resources:**
- [Atomic Red Team](https://atomicredteam.io)
- [MITRE Caldera](https://caldera.mitre.org)
- [YouTube — John Hammond adversary emulation videos](https://www.youtube.com/johnhammond010)

---

## Phase 3 — Detection Engineering
*Writing rules that actually catch attacks.*

- [ ] What detection engineering is
- [ ] Sigma rules — the universal detection format:
    - [ ] Reading existing Sigma rules
    - [ ] Writing your own Sigma rule from scratch
    - [ ] Converting Sigma to Splunk SPL or KQL
- [ ] Writing Splunk detections based on Sysmon telemetry
- [ ] Understand the **Pyramid of Pain** (why IOCs are weak, behaviors are strong)
- [ ] Baselining — what does normal look like so anomalies stand out
- [ ] Reducing false positives through tuning

**Resources:**
- [Sigma Rules GitHub](https://github.com/SigmaHQ/sigma)
- [TryHackMe — Sigma room](https://tryhackme.com/room/sigma)
- [YouTube — MyDFIR detection engineering](https://www.youtube.com/myddfir)

---

## Phase 4 — Threat Hunting
*Proactively looking for attackers who got past your detections.*

- [ ] What threat hunting is (hypothesis-driven investigation)
- [ ] The threat hunting loop:
    1. Form a hypothesis (e.g. "there may be lateral movement via WMI")
    2. Collect relevant data
    3. Investigate and look for anomalies
    4. If found → escalate. If not → document and improve detections
- [ ] Hunting with Sysmon + Splunk/Elastic
- [ ] Common hunting hypotheses:
    - [ ] Unusual parent-child process relationships
    - [ ] PowerShell downloading files from the internet
    - [ ] Encoded commands in process arguments
    - [ ] Outbound connections on unusual ports
    - [ ] Accounts logging in at unusual hours
- [ ] Building a threat hunting playbook

**Resources:**
- [TryHackMe — Threat Hunting module](https://tryhackme.com/module/threat-hunting)
- [PEAK Threat Hunting Framework](https://www.splunk.com/en_us/blog/security/peak-threat-hunting-framework.html)

---

## Phase 5 — Running a Full Purple Team Exercise
*Putting it all together.*

- [ ] Plan a purple team exercise:
    - Pick an ATT&CK technique to emulate
    - Define what "detected" looks like
    - Define what telemetry you expect to see
- [ ] Execute the attack in your lab
- [ ] Check your SIEM — was it detected?
- [ ] If yes → document the detection, move to the next technique
- [ ] If no → write a new detection rule, re-run, verify it fires
- [ ] Document everything in a purple team report:
    - Technique tested
    - Attack executed
    - Detection result (caught / missed)
    - Rule written (if applicable)
    - Residual risk

---

## Home Lab for Purple Teaming

Minimum setup:

```
Attacker VM (Kali Linux)
    ↓ attacks
Target VM (Windows 10 with Sysmon)
    ↓ logs forwarded to
SIEM VM (Splunk or Elastic)
```

- [ ] Set up Kali Linux VM
- [ ] Set up Windows 10 VM with Sysmon (SwiftOnSecurity config)
- [ ] Install and configure Splunk or Elastic
- [ ] Forward Sysmon logs to your SIEM
- [ ] Run your first Atomic Red Team test and verify it shows up in the SIEM

**Resources:**
- [YouTube — MyDFIR home lab series](https://www.youtube.com/myddfir) *(best purple team lab guide out there)*
- [Splunk Free (500MB/day)](https://www.splunk.com/en_us/download/splunk-enterprise.html)

---

## Certifications (when ready)

| Cert | Level | Notes |
|------|-------|-------|
| eJPT | Beginner | Good red foundation before going purple |
| BTL1 | Mid | Blue team practical, pairs well |
| PNPT | Mid | Offensive practical by TCM Security |
| CPTIA | Mid | Purple team specific cert |
| OSCP | Advanced | Advanced offensive — long-term goal |