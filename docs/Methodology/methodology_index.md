---
hide:
  - toc
---

# Methodology

My personal approach to each phase of a pentest or CTF — built from repetition and refined as I get better.

!!! note "Living document"
    This evolves as I learn. Early entries will be rough — that's fine.

---

<div class="grid cards" markdown>

-   :material-magnify-scan: **Recon & Enumeration**

    ---

    Information gathering before touching anything — passive and active recon, port scanning, and service enumeration.

    [:octicons-arrow-right-24: Recon methodology](recon.md)

-   :material-web: **Web App Testing**

    ---

    My approach to testing web applications — from spidering to exploiting common vulnerabilities.

    [:octicons-arrow-right-24: Web app methodology](webapp.md)

-   :material-network: **Network Pentesting**

    ---

    Attacking network services — SMB, FTP, SSH, and beyond.

    [:octicons-arrow-right-24: Network methodology](network.md)

-   :material-arrow-up-bold: **Privilege Escalation**

    ---

    Getting from low-privileged user to root or SYSTEM — Linux and Windows.

    [:octicons-arrow-right-24: PrivEsc methodology](privesc.md)

-   :material-microsoft-windows: **Active Directory**

    ---

    Attacking AD environments — enumeration, Kerberoasting, lateral movement, and domain dominance.

    [:octicons-arrow-right-24: AD methodology](active-directory.md)

-   :material-virus: **Malware Analysis**

    ---

    Static and dynamic analysis — understanding what malware does and how it does it.

    [:octicons-arrow-right-24: Malware analysis methodology](malware-analysis.md)

</div>

---

## The General Flow

```
Recon → Enumeration → Foothold → Post-Exploitation → Privilege Escalation → Persistence
```

Every engagement starts with recon and ends with documentation. The steps in between depend on what you find — but the mindset stays the same: understand before you act.