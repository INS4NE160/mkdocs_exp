# What is Networking?

> Networking is simply things connected. Just like a friend circle, where everyone is connected because they share similar interests or hobbies. A network can range from two devices to tens or thousands of devices.

**Platform:** TryHackMe  
**Path:** Pre-Security → Network Fundamentals  
**Difficulty:** Easy  
**Status:** ✅ Completed

---

## What This Room Covers

Covers what a network is, what the internet is, how devices are identified using IP and MAC addresses, and how to use the `ping` command.

---

## Key Concepts

### What is a Network?
Networking is simply things connected. Just like a friend circle, where everyone is connected because they share similar interests or hobbies. A network can range from two devices to tens or thousands of devices.

### What is the Internet?
The Internet is a vast network made up of  numerous smaller groups of interconnected devices.


There are two types of networks:
- **Private networks** — restricted, e.g. your home or office network
- **Public networks** — the internet

### IP Addresses
An IP (Internet Protocol) address is how a device is identified on a network. It's made up of **4 sections (octets)**, each being 8 bits, giving a range of `0–255` per section.

```
192.168.1.1
```

| Type | Description |
|------|-------------|
| **Public IP** | Identifies your device on the internet — assigned by your ISP |
| **Private IP** | Identifies your device on a local network — not routable on the internet |

Common private IP ranges:
```
10.0.0.0    – 10.255.255.255
172.16.0.0  – 172.31.255.255
192.168.0.0 – 192.168.255.255
```

### MAC Addresses
A MAC (Media Access Control) address is a physical identifier burned into a device's network interface card (NIC) at the factory. Unlike IP addresses, MAC addresses are hardware-level. So it can’t be changed.

```
a4:c3:f0:85:ac:2d
```

- First 6 characters = manufacturer identifier
- Last 6 characters = unique device identifier
- Can be **spoofed** in software despite being "physical"

!!! warning "MAC Spoofing"
    The interactive lab in this room shows exactly why MAC addresses aren't a reliable security measure — Bob spoofs Alice's MAC address to bypass a router that uses MAC filtering to control internet access. This is a real attack technique.

### Ping
Ping is a basic network diagnostic tool that uses **ICMP (Internet Control Message Protocol)** packets to test whether a connection between two devices exists and how reliable it is.

```bash
ping 10.10.10.10        # ping an IP address
ping google.com         # ping a domain
ping -c 4 10.10.10.10   # send only 4 packets (Linux)
```

The output shows the **round-trip time (RTT)** in milliseconds — how long a packet took to travel to the target and back.

---

## Commands & Syntax

```bash
# Basic ping
ping <IP or domain>

# Limit number of packets (Linux/Mac)
ping -c 4 10.10.10.10

# Limit number of packets (Windows)
ping -n 4 10.10.10.10
```

---

## Notes & Things I Learned

- A network is just devices connected together. Either it could be just two devices or thousands, if not millions.
- The internet was technically created in the 1960s (ARPANET) but the WWW wasn't invented until 1989 by Tim Berners-Lee
- IP addresses identify devices logically — they can change
- MAC addresses identify devices physically — they're tied to the hardware but can still be spoofed
- Ping uses ICMP — not TCP or UDP
- MAC filtering is a weak security control because MAC addresses can be spoofed

---



## Questions & Answers

??? question "What is the key term for devices that are connected together?"
    **Network**

??? question "Who invented the World Wide Web?"
    **Tim Berners-Lee**

??? question "What does the term 'IP' stand for?"
    **Internet Protocol**

??? question "What is each section of an IP address called?"
    **Octet**

??? question "How many sections does an IP address have?"
    **4**

??? question "What does the term 'MAC' stand for?"
    **Media Access Control**

??? question "What tool uses ICMP packets to test connectivity between devices?"
    **Ping**

??? question "[Interactive Lab] Deploy the interactive lab and spoof your MAC address to access the site. What is the flag?"
    **THM{YOU_GOT_ON_TRYHACKME}**

---

## Resources & Further Reading

- [TryHackMe — What is Networking? room](https://tryhackme.com/room/whatisnetworking)
- [TryHackMe — Pre-Security Path](https://tryhackme.com/path/outline/presecurity)
- [Wikipedia — ARPANET](https://en.wikipedia.org/wiki/ARPANET)

---

## Summary

Networks are connected devices. The internet is a massive public network made up of smaller networks. Devices are identified by IP addresses (logical, can change) and MAC addresses (physical, tied to hardware but can be spoofed). Ping uses ICMP to test connectivity between devices.