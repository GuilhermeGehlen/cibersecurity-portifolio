# [Lab Title] - Incident Response/Forensics Report

## 1. Overview
- Lab Name: [TryHackMe SOC Level 1 - Phishing Investigation]
- Date Completed: [2025-08-17]
- Skills Practiced: [Log analysis, phishing detection, SIEM queries]
- Tools Used: [Splunk, Wireshark]

## 2. Objective
Investigate suspicious email activity in a corporate environment and determine if it is malicious.

## 3. Steps Taken
1. Accessed SIEM logs and filtered for emails with attachments.
2. Found an email with `invoice.pdf` attachment sent from `attacker@evil.com`.
3. Extracted the attachment and analyzed in a sandbox (VirusTotal).
4. Confirmed it drops a trojan that connects to `hxxp://maliciousdomain[.]com`.

## 4. Findings
- Compromised user: john.doe@company.com
- Malicious domain: maliciousdomain.com
- IOC (Indicator of Compromise): 
  - File hash: `d41d8cd98f00b204e9800998ecf8427e`
  - IP Address: 192.168.50.10

## 5. Conclusion
The phishing email successfully bypassed initial defenses. Recommended blocklist updates and user awareness training.

## 6. Screenshots
![Splunk query screenshot](screenshot1.png)
![VirusTotal result](screenshot2.png)
