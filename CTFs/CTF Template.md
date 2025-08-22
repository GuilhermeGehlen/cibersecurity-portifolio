# [CTF Platform] - [Challenge Name]

## 1. Challenge Info
- Platform: CyberDefenders
- Challenge: "Suspicious Memory Dump"
- Category: DFIR / Memory Forensics
- Date: 2025-08-17

## 2. Challenge Description
Given a memory dump from a suspected compromised workstation, identify the malicious process and find the persistence mechanism.

## 3. Approach
1. Loaded memory dump into Volatility.
2. Ran `pslist` to enumerate processes.
   - Found suspicious process `svch0st.exe` running under SYSTEM.
3. Checked network connections with `netscan`.
   - `svch0st.exe` connected to `45.32.120.50:4444`
4. Dumped process for analysis → found encoded PowerShell persistence script.

## 4. Solution
- Malicious process: svch0st.exe
- Persistence: Run key `HKCU\Software\Microsoft\Windows\CurrentVersion\Run`
- Flag: `flag{malware_persistence_detected}`

## 5. Lessons Learned
- Memory analysis can reveal hidden processes.
- Network analysis + registry inspection confirm persistence.
- This challenge improved my Volatility workflow.

## 6. Screenshots
![Volatility output](volatility.png)
