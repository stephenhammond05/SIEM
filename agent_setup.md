# Deploying Agents on Clients

## Installing Agents on Windows computers
- The computers that I want to monitor are all windows based and use a domain controller to better simulate real-world scenarios.
- Each computer needs an agent deployed on them to push logs and notify my SIEM of any events and categorize them.
### Step 1: Download File
- Go to https://packages.wazuh.com/4.x/windows/wazuh-agent-4.11.2-1.msi to download the file.

---

### Step 2:  Configure Client

- On the Wazuh Dashboard, go to 'Agents Management'>'Summary'
- Once on the summary page, select 'Deploy New Agent'
![wazuhagent4deploy](https://github.com/user-attachments/assets/39765465-7520-49ec-ae8a-098f228fbfd3)
Fill out the required fields:
- Server address is the IP of the Wazuh Dashboard
- Agent Name is what the agent will be called on Wazuh Dashboard
Number 4 Will give you the command to run on the client machine to download and configure the agent.
![wazuhagent5script](https://github.com/user-attachments/assets/2cc18e64-46f6-44f7-820b-be31b09c2d7e)

---

### Step 3: Deploy and Run Client
- On the machine that we are deploying the agent, type in the line that we created on the dashboard.
- After it installs type this in powershell to enable it:
  ```powershell
  Net Start Wazuh
![wazuhagent6script](https://github.com/user-attachments/assets/282c9691-10df-4bc1-9fba-edfbfc6b4905)
