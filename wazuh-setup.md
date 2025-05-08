# Wazuh Installation Guide

## Quickstart Overview

### System Requirements

For this installation, I used:

- 4 CPU cores  
- 8 GB RAM  
- 2 TB storage (I needed more storage than the default 25 GB size because I kept running into install errors)
- Ubuntu 22.04 LTS

This setup offers a good balance of performance and resource usage for a small lab environment.

![System Display](https://github.com/user-attachments/assets/78ee48b4-0cc4-46d4-ab0f-3e230e6a4a8f)

---

### Step 1: Install Prerequisites

- Since this was a fresh Ubuntu install, I first installed `curl`:
  ``` bash
  sudo apt update && sudo apt install curl -y
---


### Step 2: Download and Run the Wazuh Install Script
I used the official all-in-one Wazuh install script:
  ![siem3 install](https://github.com/user-attachments/assets/a8c6e8f2-45c8-429c-9af2-8f2fe10e866d)

---

### Step 3: Dashboard Access

- After the install completes, it will output the username and password for the dashboard.
![siem4 userpass](https://github.com/user-attachments/assets/e35c98b8-6b24-47e3-b0ad-ef94f80972f2)
- To access the Wazuh Dashboard, open your browser and go to:
  ``` cpp
  https://<Wazuh Dashboard IP>
  
- Because the certificate is self-signed, your browser will warn you about it, just click "Advanced" and continue anyway.

---

### To Recover Wazuh Dashboard Credentials
- If you forget your credentials, they are located in wazuh-install-files/wazuh-passwords.txt

---

### Recommended Setting

- To avoid accidental updates that might break the environment, disable Wazuh auto updates.
