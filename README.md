# SOC-Beacon-Detection-Lab

## Objective
Simulate command-and-control (C2) beacon traffic and detect it using packet capture and packet-level analysis.

---

## Environment

- Ubuntu 24.04 LTS
- Python3
- Scapy
- tcpdump
- VirtualBox Lab Environment

---

## System Preparation

![APT Update](screenshots/04-apt-update-before-scapy-install.png)

---

## Python & Pip Installation

![Python3 Pip Installed](screenshots/05-python3-pip-installed.png)

---

## tcpdump Installation

![tcpdump Installed](screenshots/06-tcpdump-installed.png)

---

## Scapy Installation

![Scapy Installed](screenshots/07-python3-scapy-installed.png)

---

## Beacon Script Execution

A custom Python script generated repeated outbound TCP SYN packets to 8.8.8.8 over port 443 to simulate C2 beaconing.

![Beacon Script Executed](screenshots/08-beacon-script-executed.png)

---

## Packet Capture Analysis

Traffic was captured into a PCAP file and analyzed offline.

![Beacon PCAP Analysis](screenshots/09-beacon-pcap-analysis.png)

Observed:

- Repeated outbound SYN packets  
- Consistent destination IP  
- Port 443 (HTTPS)  
- Regular timing intervals  
- Incomplete TCP handshakes  

This behavior mimics basic C2 beacon traffic patterns.

---

## SYN Flag Detection

Filtering only SYN packets:
