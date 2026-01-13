# Evil-Twin-Detection-Writeup
A technical write-up on detecting and mitigating an Evil Twin attack using Nmap and WPA3 hardening
# 🛡️ Evil Twin Attack Simulation: Detection & Incident Response

## 👤 Cybersecurity Profile
* **Professional:** Abdraouf Sendid
* **Certification:** Cybersecurity Fundamentals by IBM SkillsBuild
* **Affiliation:** ISC2 Candidate 

* **Credential Issued:** Jan 09, 2026[IBMDesign20260112-33-vbpr6p.pdf](https://github.com/user-attachments/files/24597725/IBMDesign20260112-33-vbpr6p.pdf)

 **ISC2 Candidate:** https://www.credly.com/badges/20f257e0-af1c-4ff4-8cb4-f2443229b77d/public_url
---


## 🚨 Incident Scenario
This report documents my response to a live **Evil Twin attack** targeting a local network environment.

### 🔍 Detection & Strategy
1. **The Attack:** Identified unauthorized **Deauthentication frames** used to capture WPA handshakes.
2. **The Evil Twin:** Detected a rogue Access Point mimicking the network SSID using `airgeddon`.
3. **Active Defense:** Implemented a **Honeytrap** strategy, intentionally connecting to the rogue AP to analyze and identify the attacker.

### 🛠️ Forensic Investigation (Nmap)
Used **Nmap** on Kali Linux to identify the intruder's hardware footprint:
```bash
# Identification of the attacker's IP and MAC
sudo nmap -sn 192.168.1.0/24

# OS Fingerprinting to confirm the attack platform
sudo nmap -A -T4 [Attacker_IP]
