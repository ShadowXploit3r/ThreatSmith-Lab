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

Create a **Windows 10 VM**.  

**Resources used:**  
- CPU: **2 vCPUs**  
- RAM: **2.5 GB**  
- Disk: **50 GB**  
- Network: **Bridged**  

### 🔹 Install Sysmon  
- Download **Sysmon** from [Sysinternals](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon).  
- Use **Sysmon Modular config** → [olafhartong/sysmon-modular](https://github.com/olafhartong/sysmon-modular).  
- Install with:  
  ```powershell
  sysmon.exe -accepteula -i sysmonconfig.xml
- Reference video: [Sysmon Tutorial – YouTube](https://www.youtube.com/watch?v=uJ7pv6blyog)  

---

### 🔹 Install Wazuh Agent  
1. Download the agent from the **Wazuh server Web UI**.  
2. During setup, enter your **Wazuh server IP**.  
3. Start the **Wazuh Agent service**.  
4. Verify in the **Wazuh Dashboard** → Windows should appear as an **active agent**.  

---

## 4. Metasploitable2 (Vulnerable Target)  

1. Download **Metasploitable2 VM** → [SourceForge](https://sourceforge.net/projects/metasploitable/).  
2. Import into **VMware Workstation**.  

**Resources used:**  
- CPU: **1 vCPU**  
- RAM: **512 MB – 1 GB**  
- Disk: **8 GB**  
- Network: **Bridged**  

**Default credentials:**  
```bash
Username: msfadmin
Password: msfadmin
Verify connectivity with: ping <Wazuh-IP>

---

## 6. Networking  

- All VMs are on **Bridged Network**.  
- Each VM gets an IP from the same LAN as the host.  
- Verified connectivity with `ping` between machines.  

---

## 7. Verification  

- On **Windows**: open **Notepad** → Sysmon generates logs.  
- In **Wazuh Dashboard**: confirm logs from Windows agent.  
- On **Windows**: download **EICAR test file** → Wazuh triggers an alert.  
- From **Kali**: run an **Nmap scan** on **Metasploitable2** → alerts/logs visible in Wazuh.  

---

## ✅ Final Lab Overview  

- **Wazuh SIEM** collects and correlates logs.  
- **Windows Victim** sends Sysmon + Wazuh Agent logs.  
- **Metasploitable2** provides a vulnerable target.  
- **Kali Linux** launches attacks and tests detections.  

---

## 📌 References  

- [Wazuh Official Docs](https://documentation.wazuh.com/)  
- [Sysmon Download](https://learn.microsoft.com/en-us/sysinternals/downloads/sysmon)  
- [Sysmon Modular Config](https://github.com/olafhartong/sysmon-modular)  
- [Sysmon Tutorial – YouTube](https://www.youtube.com/watch?v=uJ7pv6blyog)  
- [Metasploitable2](https://sourceforge.net/projects/metasploitable/)  
- [Kali Linux](https://www.kali.org/get-kali/#kali-virtual-machines)  


