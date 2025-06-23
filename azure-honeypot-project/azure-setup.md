Azure VM Honeypot – Setup Guide

Overview
This document outlines the steps I followed to set up a Windows Server Virtual Machine (VM) on Microsoft Azure as a honeypot, based on Josh Madakor's cybersecurity project.

1. Azure Account Setup
- Created a **Microsoft Azure account** (free tier)
- Verified identity using phone and credit card
- Activated free credits for resource deployment


2. Create a Virtual Machine

- **Service used**: Azure Virtual Machines
- **Operating System**: Windows 10 Pro Version 22H2 x64 Gen 2
- **Region**: East US 2
- **Size**: Standard_DS_2s_v3 - 2vcpus, 8 Gib Memory
- **Username**: Created secure admin login
- **Authentication**: Password-based (no SSH key)

3. Network Configuration

- **Public IP**: Enabled (static IP assigned)
- **Inbound port rules**:
  - Allowed all ports to be open
- **Outbound port rules**:
  - Default

4. Configure the VM After Deployment

- Connected via **Remote Desktop Connection (RDP)**
- Checked and adjusted:
  - **Clipboard sharing**: was on by default
  - **Printer redirection**: off
  - **Firewall rules**: off

5. Honeypot Simulation

- Left RDP open intentionally to simulate a honeypot
- Waited a couple hours to observe external login attempts
- Monitored logs using **Event Viewer** under:
  - Windows Logs → Security → Event ID 4624 / 4625
- Detected a **successful login from India**

6. Post-Incident Actions

- Disconnected from VM
- Ran **Microsoft Defender Antivirus** from my local PC
- Conducted **offline scan** to check for compromise
- Reviewed system files, clipboard settings, and logs
- Finally, **deleted the VM and all Azure resources**

Tools Used

- Microsoft Azure Portal
- Windows 10 Pro Version 22H2 x64 Gen 2
- Event Viewer
- Microsoft Defender Antivirus (Offline Scan)
- Remote Desktop Connection (RDP)

 Notes

- Next time, I would enable logging alerts or IP restrictions
- Learned the importance of securing clipboard sharing on RDP sessions

