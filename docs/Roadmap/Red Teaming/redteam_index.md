# Red Team Roadmap

The offensive side — learning to think like an attacker.

!!! note "This is my Roadmap for Red Teaming "
    Work through each phase in order. Don't skip ahead — the later phases assume the earlier ones. Check off items as you go and link to your notes/writeups as you build them.

---

## Phase 1 — Absolute Basics
*Getting comfortable with the fundamentals before touching anything offensive.*

### Linux
- [ ] Navigating the file system (`cd`, `ls`, `pwd`, `find`)
- [ ] Reading and writing files (`cat`, `nano`, `echo`, `>`, `>>`)
- [ ] File permissions (`chmod`, `chown`, `ls -la`)
- [ ] Users and groups (`whoami`, `id`, `su`, `sudo`)
- [ ] Processes (`ps`, `kill`, `top`)
- [ ] Networking commands (`ip a`, `ping`, `curl`, `wget`)

**Resources:**
- [TryHackMe — Linux Fundamentals (Parts 1, 2, 3)](https://tryhackme.com/module/linux-fundamentals)
- [YouTube — NetworkChuck Linux for Hackers](https://www.youtube.com/networkchuck)

### Networking
- [ ] OSI model (what each layer does)
- [ ] TCP vs UDP
- [ ] IP addressing & subnetting basics
- [ ] Common ports and protocols (22, 80, 443, 445, 3389...)
- [ ] DNS, HTTP/S basics
- [ ] How a packet travels across a network

**Resources:**
- [TryHackMe — Pre-Security Path](https://tryhackme.com/path/outline/presecurity)
- [YouTube — Professor Messer CompTIA Network+](https://www.youtube.com/professormesser)

---

## Phase 2 — Recon & Enumeration
*You can't attack what you don't understand. Recon is everything.*

- [ ] Passive recon (OSINT, Shodan, Google dorking)
- [ ] Active recon (Nmap — host discovery, port scanning, service detection)
- [ ] Web enumeration (Gobuster, Nikto, directory busting)
- [ ] SMB enumeration (`enum4linux`, `smbclient`, `smbmap`)
- [ ] DNS enumeration (`dig`, `nslookup`, zone transfers)
- [ ] Subdomain discovery

**Resources:**
- [TryHackMe — Jr Penetration Tester Path](https://tryhackme.com/path/outline/jrpenetrationtester)
- [TryHackMe — Nmap room](https://tryhackme.com/room/furthernmap)

---

## Phase 3 — Exploitation Basics
*Finding vulnerabilities and getting that first shell.*

- [ ] Understanding CVEs and vulnerability databases (NVD, ExploitDB)
- [ ] Manual exploitation basics
- [ ] Metasploit framework (search, use, set options, run)
- [ ] Password attacks (Hydra, Medusa, brute forcing login panels)
- [ ] Web vulnerabilities:
    - [ ] SQL Injection (manual + sqlmap)
    - [ ] XSS (reflected, stored)
    - [ ] Command injection
    - [ ] File upload vulnerabilities
    - [ ] LFI / RFI
- [ ] Reverse shells & bind shells (Netcat, PHP, Python)

**Resources:**
- [TryHackMe — OWASP Top 10 room](https://tryhackme.com/room/owasptop10)
- [TryHackMe — Metasploit module](https://tryhackme.com/module/metasploit)
- [PortSwigger Web Security Academy](https://portswigger.net/web-security) *(free, excellent)*

---

## Phase 4 — Post-Exploitation
*You're in. Now what?*

- [ ] Situational awareness (who am I, what's on this machine, what network is this)
- [ ] Linux privilege escalation:
    - [ ] Sudo misconfigurations (`sudo -l`)
    - [ ] SUID binaries
    - [ ] Cron jobs
    - [ ] Writable `/etc/passwd`
    - [ ] Kernel exploits
- [ ] Windows privilege escalation:
    - [ ] Unquoted service paths
    - [ ] Weak service permissions
    - [ ] Token impersonation
    - [ ] AlwaysInstallElevated
- [ ] Persistence techniques
- [ ] Credential dumping (Mimikatz basics)
- [ ] Transferring files to/from target

**Resources:**
- [TryHackMe — Linux PrivEsc room](https://tryhackme.com/room/linuxprivesc)
- [TryHackMe — Windows PrivEsc room](https://tryhackme.com/room/windows10privesc)
- [GTFOBins](https://gtfobins.github.io) *(essential reference)*
- [YouTube — TCM Security PrivEsc courses](https://www.youtube.com/tcmsecurity)

---

## Phase 5 — Active Directory
*Most real-world environments run AD. This is where it gets serious.*

- [ ] What Active Directory is and how it works
- [ ] Enumeration (BloodHound, PowerView, `net` commands)
- [ ] Kerberoasting
- [ ] AS-REP Roasting
- [ ] Pass-the-Hash / Pass-the-Ticket
- [ ] DCSync attack
- [ ] Golden & Silver Tickets

**Resources:**
- [TryHackMe — Active Directory Basics](https://tryhackme.com/room/activedirectorybasics)
- [HackTheBox — Starting Point machines](https://app.hackthebox.com/starting-point)
- [YouTube — TCM Security Practical Ethical Hacking course](https://www.youtube.com/tcmsecurity)

---

## Phase 6 — Real Boxes & CTFs
*Stop learning, start doing.*

- [ ] Complete 25 TryHackMe rooms
- [ ] Complete 5 HackTheBox easy machines
- [ ] Complete 5 HackTheBox medium machines
- [ ] Participate in at least one CTF
- [ ] Write a walkthrough for every box you complete

---

## Certifications (when ready)

| Cert | Level | Notes |
|------|-------|-------|
| CompTIA Security+ | Beginner | Good baseline, mostly theory |
| eJPT | Beginner–Mid | Practical, great first offensive cert |
| PNPT | Mid | TCM Security, highly practical |
| OSCP | Advanced | The gold standard for pentesters |