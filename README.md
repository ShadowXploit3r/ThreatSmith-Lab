# 🛡️ ThreatSmith Lab – Wazuh SIEM + Windows Sysmon Endpoint + Kali Attacker  

## 📌 Overview  
This repository documents my **home Security Operations Center (SOC) lab**.  
The lab simulates a real SOC environment using a SIEM, a victim endpoint, and an attacker machine.  
It allows me to **practice SOC analyst workflows** such as log collection, threat detection, and incident investigation.  

---

## 🖥️ Lab Components  
- **Ubuntu (Host OS)** – Runs VMware Workstation  
- **Wazuh OVA** – SIEM server (log collection, correlation, and dashboards)  
- **Windows VM (Victim)** – Endpoint with:
  - Wazuh agent (log forwarding)
  - Sysmon (detailed process, file, and network event logging)  
- **Kali Linux VM (Attacker)** – Used to simulate attacks (brute force, malware tests, PowerShell abuse)  

---

## 🎯 Objectives  
- Centralize endpoint logs in **Wazuh SIEM**  
- Capture detailed Windows activity with **Sysmon**  
- Simulate common attacks using **Kali Linux**  
- Detect and analyze alerts in Wazuh  
- Map detections to the **MITRE ATT&CK framework**  

---

## 🛠 Tools & Technologies  
- **Wazuh OVA** – Open-source SIEM platform  
- **Windows 10 VM** – Victim endpoint with Wazuh agent  
- **Sysmon (System Monitor)** – Advanced Windows event logging  
- **SwiftOnSecurity Sysmon Config** – Optimized Sysmon configuration  
- **Kali Linux** – Attacker for red team simulations  
- **VMware Workstation** – Virtualization with Bridged networking  

---

## 🗺️ Architecture  

![Architecture](images/soc-architecture.png)  

---

## 📊 Features  
- Sysmon logs collected and forwarded to Wazuh  
- Security dashboards for monitoring endpoint activity  
- Alerts mapped to **MITRE ATT&CK** techniques  
- Detection of:
  - Brute force login attempts  
  - Suspicious PowerShell execution  
  - EICAR malware test file events  

---

## 📂 Documentation  
- [Setup Guide](setup-guide.md) – How I built the lab  
- [Attack Scenarios](attack-scenarios.md) – Example detections from Kali simulations  
- [Sysmon Config](configs/sysmonconfig.xml) – Sysmon configuration file  

---

## 📷 Screenshots  
- Wazuh dashboard with alerts  
- Sysmon logs in Wazuh  
- MITRE ATT&CK mapping  
- Connected agents overview  

Example placeholders (replace with your own):  

![Wazuh Dashboard](images/dashboard.png)  
![Sysmon Logs](images/sysmon-logs.png)  

---

## 🚀 Future Improvements  
- Add Suricata IDS logs to Wazuh  
- Expand detections with Sigma rules  
- Automate attack simulations using **Atomic Red Team**  
- Add Linux endpoint with Wazuh agent  

---

## 📌 Learning Outcomes  
By building this lab, I learned how to:  
- Deploy and configure a SIEM (Wazuh)  
- Collect and forward endpoint telemetry with Sysmon + Wazuh agent  
- Simulate adversary activity with Kali Linux  
- Investigate alerts and correlate events in a SOC workflow  

---
