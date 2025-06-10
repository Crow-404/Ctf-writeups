# Operation Blackout 2025: Smoke & Mirrors

**Challenge Type:** Windows Registry Forensics / DFIR

## Overview

This challenge explores how attackers can use PowerShell and Windows Registry modifications to weaken or disable built-in Windows security features. As part of the analysis, we examined how registry keys are manipulated, how PowerShell is abused, and how attackers avoid detection using common evasion techniques.

## Objectives

- Understand how PowerShell cmdlets can be used for malicious purposes.
- Analyze attacker behavior by examining Windows Registry changes.
- Identify methods used to disable or tamper with Windows security protections.

### Lessons Learned

- The Windows Registry often contains the evidence needed to detect advanced attacks.
- PowerShell is a powerful administrative tool that, when logging is disabled, becomes a significant attack vector.
- Attacks can bypass AMSI (Antimalware Scan Interface) by patching key functions in memory.
- Restarting a system in Safe Mode can be used to disable certain security services and allow further compromise.

## Tasks & Solutions

### Task 1

**Question:** The attacker disabled LSA protection on the compromised host by modifying a registry key. What is the full path of that registry key?

**Answer:**  
`HKLM\SYSTEM\CurrentControlSet\Control\LSA`

---

### Task 2

**Question:** Which PowerShell command did the attacker first execute to disable Windows Defender?
 
**Answer:**
Set-MpPreference -DisableIOAVProtection $true -DisableEmailScanning $true -DisableBlockAtFirstSeen $true

---

Task 3
Question: The attacker loaded an AMSI patch written in PowerShell. Which function in the DLL is being patched by the script to effectively disable AMSI?

**Answer:**
AmsiScanBuffer

---

Task 4
Question: Which command did the attacker use to restart the machine in Safe Mode?

**Answer:**
bcdedit.exe /set safeboot network

---

Task 5
Question: Which PowerShell command did the attacker use to disable PowerShell command history logging?

Answer:
Set-PSReadlineOption -HistorySaveStyle SaveNothing

---
