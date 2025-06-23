Incident Response Report – Azure Honeypot Login

Overview

This document outlines my personal incident response process after detecting a suspicious login event to my Azure-based honeypot virtual machine (VM). The VM was intentionally exposed to simulate unauthorized access and practice response techniques.

Incident Summary

- **Date of detection**: June 21, 2025
- **Threat observed**: Successful RDP login from an unfamiliar IP address located in **India**
- **Initial access point**: Microsoft Azure VM (Windows 10 Pro)
- **Risk to local machine**: Unknown at the time of login detection

 Detection Process

1. **Monitoring Setup**
   - Regularly checked **Event Viewer** within the VM
   - Focused on **Event ID 4624 (Logon success)** and **4625 (Logon failed)**

2. **Suspicious Activity Found**
   - Detected Event ID 4624 showing a successful login with:
     - **Logon Type**: 10 (RemoteInteractive)
     - **Source IP Address**: 103.92.17.241
     - I had not initiated this login.

3. **Logon Time**
   - The logon occurred shortly before my own access, meaning an attacker was inside the VM briefly before I logged in.

Immediate Response Actions

1. **Disconnected from VM**
   - Ensured no further interaction with the possibly compromised system.

2. **Reviewed RDP Configuration**
   - Verified that **clipboard sharing was enabled** at the time of login
   - **Clipboard history** was disabled on my local PC, reducing risk of sensitive data exposure

3. **Checked for File Transfers**
   - Inspected `Downloads`, `Temp`, and `OneDrive` folders on local PC
   - Verified no unexpected files were saved or opened
   - No suspicious activity found

4. **Scanned Local System**
   - Ran **Microsoft Defender Antivirus (Offline Scan)**
     - Scan reached 91%, then returned to login screen without a completion message
     - No log appeared in Protection History
   - Re-ran scan with **Microsoft Safety Scanner** and/or **Malwarebytes**
     - No threats detected

Resolution

- Deleted the entire **Azure VM**, public IP, and associated network resources
- Verified that no sensitive information was shared via RDP clipboard
- Confirmed local PC integrity through:
  - Manual file inspection
  - Antivirus scan results
  - System behavior monitoring

Lessons Learned

- **Public RDP exposure** leads to fast, real-world brute-force attempts — even on low-profile VMs
- **Clipboard sharing** should be disabled by default in honeypot setups
- **Offline scans may silently fail** — fallback tools like Safety Scanner or Malwarebytes are critical
- It’s important to log your response process even when no clear damage occurred

Final Status

- No evidence of compromise found on local system
- No files were transferred to or from the VM
- Project was used successfully as a learning opportunity in real-world threat monitoring and response

