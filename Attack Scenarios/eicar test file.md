# 🧪 Detecting the EICAR Test File with Wazuh SIEM

## 🔎 What is the EICAR Test File?
The **EICAR test file** is a harmless string of characters designed to trigger antivirus software.  
It is **not real malware**, but allows you to safely test whether your AV and SIEM are detecting threats.  

EICAR string: X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*

⚠️ Important: Do not rename it to `.exe` — the `.com` extension is enough for AV to detect it.

---

## 🛠 Step 1: Generate the EICAR Test File

### PowerShell
```powershell
Set-Content -Path "$env:USERPROFILE\Desktop\eicar.com" -Value 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*'





