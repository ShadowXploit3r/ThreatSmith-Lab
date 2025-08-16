# Detecting the EICAR Test File with Wazuh SIEM

## 📌 Project Overview
This project demonstrates how to detect the **EICAR test file** using **Wazuh SIEM**.  
The goal is to showcase Wazuh’s ability to capture **malware events** and **file integrity changes** from Windows endpoints.  

---

## 🎯 Objective
- Generate the **EICAR test file** on a Windows endpoint.  
- Ensure the **Wazuh agent** collects Windows Defender and FIM logs.  
- Detect and analyze the alerts in the **Wazuh Dashboard**.  
- Map the detection to the **MITRE ATT&CK framework**.  

---

## 🔎 What is the EICAR Test File?
The **EICAR test file** is a harmless string of characters designed to trigger antivirus software.  
It is **not real malware**, but a safe way to test detection pipelines.  

**EICAR string: X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H***


⚠️ Important: Do not rename it to `.exe` — the `.com` extension is enough for AV to detect it.

---

## 🛠 Step 1: Generate the EICAR Test File

### PowerShell
```powershell
Set-Content -Path "$env:USERPROFILE\Desktop\eicar.com" -Value 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*'



