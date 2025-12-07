# Project 11 – Brute Force Attack Detection (Windows Event Logs)

## Overview
This project shows how I detected a simulated brute-force attack using Windows Security Logs. By intentionally entering the wrong password multiple times on my Windows VM, I generated Event ID 4625 failures and analyzed them in Event Viewer—similar to how SOC analysts investigate authentication attacks.

---

## What I Did
- Opened **Event Viewer → Windows Logs → Security**
- Triggered 9 failed logins by entering the wrong password repeatedly
- Filtered the log by **Event ID 4625** (Failed Logon)
- Viewed the **XML details** to analyze the attack
- Saved screenshots and wrote a summary of the findings

---

## Key Findings (Event ID 4625)
From the XML view of the event:

- **TargetUserName:** staceynaylor  
- **FailureReason:** Unknown user name or bad password  
- **LogonType:** 2 (local/interactive login)  
- **IpAddress:** 127.0.0.1 (local machine)  

Multiple failed logins in a short time period match the pattern of a brute-force attack.

---

## Why This Matters
Event ID **4625** is one of the most important log types for detecting:
- Password brute forcing  
- Credential stuffing attempts  
- Lateral movement  
- Unauthorized access attempts  

SOC analysts rely heavily on these logs to identify attackers and protect accounts.

---

## Files Included
- **Project11-BruteforceDetection.md** – Full write-up  
- **/screenshots** – Evidence screenshots:
  - 4625-Failed-Logons.png  
  - 4625-XML-Details.png  

---

## Summary
This project improved my ability to recognize authentication attacks, analyze Windows logs, and understand how brute-force patterns appear in real environments. These are core skills for SOC analysts and threat detection work.
