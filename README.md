# Wazuh SIEM Home Lab

This project demonstrates a home lab setup using the Wazuh SIEM to detect and respond to various cyberattacks in a simulated enterprise network. The environment includes a domain controller, Windows clients, a Kali Linux attacker machine, and a centralized Wazuh manager running on Ubuntu Server.

## Purpose

To gain real-world experience with Security Information and Event Management (SIEM) systems, Windows Event Log analysis, Active Directory monitoring, and incident response using open-source tools.

---

## Lab Architecture

- **Wazuh Manager**: Ubuntu Server VM (Wazuh, Filebeat, and Kibana)
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

- [`setup/ubuntu-wazuh-setup.md`](setup/ubuntu-wazuh-setup.md): Install and configure Wazuh Manager
- [`setup/windows-agent-setup.md`](setup/windows-agent-setup.md): Configure agents on Windows machines
- [`setup/ad-domain-setup.md`](setup/ad-domain-setup.md): Domain controller and GPO setup
- [`setup/kali-attack-scripts`](setup/kali-attack-scripts): Sample commands/scripts used for attacks

---

## Wazuh Dashboards

Screenshots of alerts and dashboards from the Wazuh interface.

![SSH Brute Force Alert](dashboard-screenshots/alert-example-ssh.png)

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
