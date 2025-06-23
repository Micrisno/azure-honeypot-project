Azure Honeypot Security Project

Overview Deployed a Windows Server virtual machine (VM) on Microsoft
Azure as a honeypot to attract real-world intrusion attempts and
practice incident response techniques.

Objectives - Gain hands-on experience with cloud infrastructure and
threat detection - Simulate and analyze unauthorized login behavior -
Practice securing remote access protocols (RDP)

Tools & Technologies - Microsoft Azure (VM deployment) - Windows Event
Viewer (log inspection) - RDP (Remote Desktop Protocol) - Microsoft
Defender Antivirus (Offline Scan) - OneDrive, Clipboard Sharing Settings

Key Events - Set up public RDP access as part of honeypot - Detected a
successful login attempt from an IP in India - Investigated logs and
clipboard settings for potential exposure - Ran a full security analysis
including Defender Offline Scan - Found no signs of compromise on local
machine; deleted VM to contain risk

Lessons Learned - Importance of RDP hardening (e.g., IP whitelisting,
disabling clipboard sharing) - How real-world attacks can occur quickly
after exposure - How to respond to incidents with calm investigation and
verification - Cloud resources should always have logging and access
control by default

Outcome Successfully simulated a real-world unauthorized access attempt,
practiced live incident response, and learned key cloud security
concepts.
