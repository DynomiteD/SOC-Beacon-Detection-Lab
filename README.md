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

### APT Update

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

The custom Scapy script generated periodic outbound TCP SYN packets to 8.8.8.8 over port 443 to simulate C2 beaconing behavior.

![Beacon Script Executed](screenshots/06-beacon-script-executed.png)

---

## Packet Capture Analysis

Traffic was captured into a PCAP file using tcpdump and analyzed offline to identify beaconing indicators.

![Beacon PCAP Analysis](screenshots/09-beacon-pcap-analysis.png)

### Detection Indicators Observed

- Repeated outbound TCP SYN packets
- Consistent destination IP (8.8.8.8)
- Traffic over TCP port 443 (HTTPS)
- Regular, periodic timing intervals
- Incomplete TCP handshakes (no full 3-way completion)

These characteristics are consistent with basic C2 beaconing behavior where an infected host periodically attempts outbound communication.

---

## SYN Flag Detection

Filtering only SYN packets using tcpdump:

![Beacon SYN Filter](screenshots/10-beacon-syn-filter.png)

## Skills Demonstrated

- Packet capture and analysis using tcpdump
- SYN flag filtering for anomaly detection
- Identification of periodic outbound beaconing behavior
- PCAP investigation and traffic pattern analysis
- Simulation of C2 traffic using Scapy

## Conclusion

This lab demonstrated how periodic outbound SYN traffic can simulate basic command-and-control (C2) beaconing behavior.

Using tcpdump filtering and packet-level analysis, indicators such as regular timing intervals, incomplete TCP handshakes, and consistent destination targeting were identified.

This process reflects real-world SOC investigation techniques, where analysts inspect network telemetry to detect suspicious beaconing patterns indicative of potential malware activity.
