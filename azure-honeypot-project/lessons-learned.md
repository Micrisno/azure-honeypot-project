Lessons Learned – Azure Honeypot Project

1. Public RDP Is Risky
- Leaving RDP open to the internet results in **brute-force attempts within hours**
- Even low-cost VMs are scanned by bots and threat actors

2. Disable Clipboard Sharing by Default
- Clipboard redirection can create a potential data leakage vector
- Always disable it when setting up honeypots or exposed VMs

3. Offline Scans Can Fail Silently
- Microsoft Defender Offline Scan may not always complete or log results
- Use fallback tools like **Microsoft Safety Scanner** or **Malwarebytes**

4. Logging and Monitoring Are Critical
- **Event Viewer** helped detect the unauthorized login (Event ID 4624)
- Next time, I would enable **Azure Monitor** or **email alerts** for suspicious logins

5. Incident Response Doesn’t Require Panic
- Calmly investigating logs, checking clipboard history, and running scans helped avoid overreaction
- Deleting the VM and running a deep scan ensured the threat was contained

6. Always Document the Process
- Writing out steps and reflections builds stronger cybersecurity habits
- It also makes the experience shareable as a portfolio project

Conclusion

This project provided valuable hands-on experience with cloud infrastructure security, remote access risks, and incident response workflows. 
By simulating a real-world unauthorized login, I learned how quickly exposed services like RDP are targeted, and how important it is to monitor, 
contain, and respond without panic. The exercise also reinforced the need for proper documentation, layered security practices, and a methodical 
approach to potential breaches — all of which are essential skills for any role in cybersecurity or IT operations. Moving forward, I plan to apply 
these lessons to future cloud projects by incorporating stronger access controls, more proactive monitoring, and secure defaults in all configurations.
