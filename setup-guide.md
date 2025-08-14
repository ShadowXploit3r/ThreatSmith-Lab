# ⚙️ SOC Home Lab Setup Guide  

This is a simple step-by-step guide for building a SOC home lab using:  
- **Ubuntu Host**  
- **Wazuh SIEM**  
- **Windows Victim (with Sysmon + Wazuh Agent)**  
- **Metasploitable2 (vulnerable target)**  
- **Kali Linux (attacker)**  

---

## 1. Host (Ubuntu)  
- **OS**: Ubuntu 22.04 LTS  
- **RAM**: 8 GB  
- **Hypervisor**: VMware Workstation  

---

## 2. Wazuh SIEM (OVA)  
1. Download the official **Wazuh OVA** → [Wazuh Downloads](https://wazuh.com/download/)  
2. Import into VMware Workstation.  
3. Resources used:  
   - CPU: **2 vCPUs**  
   - RAM: **3.5 GB**  
   - Disk: **50 GB**  
   - Network: **Bridged**  
4. Start the VM and log in.  
5. Access Wazuh Dashboard: http://<Wazuh-IP>

--- 

## 3. Windows Victim (with Sysmon + Wazuh Agent)
1. Create a Windows 10 VM.
2. Resources used:
   - CPU: **2 vCPUs**  
   - RAM: **2.5 GB**  
   - Disk: **50 GB**  
   - Network: **Bridged** 

🔹 Install Sysmon
Download Sysmon from Sysinternals.
Use Sysmon Modular config → olafhartong/sysmon-modular.
Install with: sysmon.exe -accepteula -i sysmonconfig.xml


   ```bash
   https://<Wazuh-IP>
