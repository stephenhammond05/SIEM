# Wazuh SIEM Home Lab

This project demonstrates a home lab setup using the Wazuh SIEM to detect and respond to various cyberattacks in a simulated enterprise network. The environment includes a domain controller, Windows clients, a Kali Linux attacker machine, and a centralized Wazuh manager running on Ubuntu Server.

## Purpose

To gain real-world experience with Security Information and Event Management (SIEM) systems, Windows Event Log analysis, Active Directory monitoring, and incident response using open-source tools.

---

## Lab Architecture

- **Wazuh Manager**: Ubuntu Server VM (Wazuh)
- **Windows Server 2019**: Domain Controller (Active Directory, DNS)
- **Windows 10 Clients**: Joined to domain, Wazuh agent installed
- **Kali Linux**: Attacker machine used to simulate threats
- **Network**: All systems on a VirtualBox Host-Only adapter (`10.0.2.x`)

![Architecture Diagram](architecture/network-diagram.png)

---

## Attack Scenario Tested

| Scenario | Tool Used | Detection Source | Wazuh Alert |
|----------|-----------|------------------|-------------|
| SSH brute-force attack | `hydra` from Kali | `/var/log/auth.log` | SSH authentication failure |

---

##  Setup Documentation

- [`Wazuh Setup`](wazuh-setup.md): Install and configure Wazuh Manager
- [`Agent Setup`](agent_setup.md): Configure agents on Windows machines

---

## Wazuh Dashboards

Screenshots of alerts and dashboards from the Wazuh interface.
- Kali Brute Force Attack.
![kalihydra](https://github.com/user-attachments/assets/e704f7f3-02ab-4a43-ab12-70ea3bff546f)
- High severity Dashboard.
![kalihighseverity](https://github.com/user-attachments/assets/0d64b3a1-5e1c-421e-bbf7-2a4c86226f57)
- Sample Alert View.
![flooded](https://github.com/user-attachments/assets/fc5649aa-3c51-492c-bd67-f5cb03b2c5ea)


---

## Rules and Configuration

- [`rules/custom-wazuh-rules.xml`](rules/custom-wazuh-rules.xml): Custom detection rules
- [`rules/ignored-events.conf`](rules/ignored-events.conf): Noise filtering for false positives


---

## Skills Demonstrated

- SIEM configuration and tuning
- Windows and Linux log analysis
- Network security monitoring
- Attack simulation using Kali Linux

---

## Future Plans

- Integrate TheHive for case management
- Add Suricata for IDS detection
- Simulate phishing scenarios and lateral movement
- Include TheHive for incident response
