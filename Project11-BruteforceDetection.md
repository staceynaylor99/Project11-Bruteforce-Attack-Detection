# Project 11 – Brute Force Attack Detection (Windows Event Logs)

## Overview
In this project, I simulated a brute-force attack on my Windows VM and analyzed the results using Windows Event Viewer. By intentionally entering the wrong password multiple times, I generated Event ID 4625 entries that SOC analysts use to detect authentication attacks.

---

## What I Did
- Opened Event Viewer and navigated to Windows Logs → Security
- Locked the system and entered the wrong password nine times
- Unlocked the system with the correct password
- Filtered the Security log by Event ID 4625 (failed logon attempts)
- Analyzed each event for brute-force indicators

---

## Key Evidence (Event ID 4625)
### From XML View:
- **TargetUserName:** staceynaylor  
- **FailureReason:** Unknown user name or bad password  
- **LogonType:** 2 (interactive/local login)  
- **IpAddress:** 127.0.0.1 (local machine)  

This cluster of failed logins in a short period of time matches a brute-force pattern.

---

## Why This Matters
SOC analysts rely on Event ID 4625 to detect:
- Password brute forcing  
- Credential stuffing  
- Lateral movement attempts  
- RDP or SMB attack activity  

Even when an attacker uses encryption or stealth, failed logon events give away their activity.

---

## What I Learned
- How to filter Security logs for suspicious authentication activity  
- How to read XML View to extract critical log fields  
- How brute-force attacks appear inside Windows logs  
- How analysts confirm attack patterns using timestamps and repetition  
- How to document and report findings clearly

---

## Files Included
- **Project11-BruteforceDetection.md** – This write-up
- **Screenshots** – Evidence of 4625 events and XML details

---

## Summary
This project improved my ability to detect authentication attacks using native Windows logs. I learned how to identify failed logon patterns and extract the key fields needed to investigate brute-force activity in a SOC environment.
