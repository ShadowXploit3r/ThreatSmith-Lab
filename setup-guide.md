# ⚙️ Setup Guide – SOC Home Lab

This guide explains how I built my SOC home lab with **Ubuntu (host)**, **Wazuh SIEM**, **Windows Victim (with Sysmon)**, and **Kali Linux (attacker)**.

---

## 1. Host (Ubuntu)
- OS: Ubuntu 22.04 LTS  
- Total RAM: 8 GB  
- Hypervisor: VMware Workstation  

---

## 2. Wazuh SIEM (OVA)
1. Download the official Wazuh OVA.  
2. Import into VMware Workstation.  
3. Resources I used:  
   - CPU: 2 vCPUs  
   - RAM: **3.5 GB**  
   - Disk: 50 GB  
   - Network: **Bridged**  
4. Start the VM and log in.  
5. Access Wazuh dashboard:
6. https://<Wazuh-IP>

---

## 3. Windows Victim (with Sysmon + Wazuh Agent)
1. Create a Windows 10 VM.  
2. Resources I used:  
- CPU: 2 vCPUs  
- RAM: **2.5 GB**  
- Disk: 50 GB  
- Network: **Bridged**  
3. Install **Sysmon**:  
- Download Sysmon from Microsoft Sysinternals.  
- Use SwiftOnSecurity Sysmon config.  
- Install with:  
  ```
  sysmon.exe -accepteula -i sysmonconfig-export.xml
  ```
4. Install **Wazuh Agent**:  
- Download from Wazuh server web UI.  
- Enter Wazuh server IP during setup.  
- Start the Wazuh Agent service.  
5. Verify in Wazuh dashboard → Windows shows as active agent.

---

## 4. Kali Linux (Attacker)
1. Download Kali Linux VM image.  
2. Import into VMware Workstation.  
3. Resources I used:  
- CPU: 1 vCPU  
- RAM: **2 GB** (paused when not in use to save resources)  
- Disk: 30 GB  
- Network: **Bridged**  
4. Update Kali:  
sudo apt update && sudo apt upgrade -y

---

## 5. Networking
- All VMs are on **Bridged Network**.  
- Each VM gets an IP from the same LAN as the host.  
- Verified connectivity with `ping` between machines.  

---

## 6. Verification
1. On Windows, open Notepad → Sysmon logs generated.  
2. In Wazuh dashboard, check logs from Windows agent.  
3. Download **EICAR test file** on Windows → Wazuh alert triggered.  

---

✅ Lab is ready:  
- Wazuh collects logs and shows alerts.  
- Windows sends Sysmon + agent logs.  
- Kali is available to simulate attacks (paused when not needed).


