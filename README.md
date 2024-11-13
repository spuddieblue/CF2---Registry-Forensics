# Introduction to Windows Registry Forensics
## Lab Guide for Computer Forensics 2 Students

### Overview
The Windows Registry is a hierarchical database that stores crucial system and application configuration data. In computer forensics, the Registry often contains valuable evidence about user activities, installed programs, and system changes.

### Learning Objectives
By completing this lab, you will:
- Understand the basic structure of the Windows Registry
- Learn to navigate Registry hives and keys
- Identify common forensic artifacts in the Registry
- Practice basic Registry analysis techniques

### Prerequisites
- Windows computer with administrative access
- Registry Editor (regedit.exe)
- Note-taking materials

### Safety Notice
⚠️ **IMPORTANT**: The Registry is critical to Windows operation. Never modify Registry values unless specifically instructed. Only view and analyze entries.

### Lab Activities

#### Part 1: Registry Basics (20 minutes)

1. Open Registry Editor:
   - Press `Windows + R`
   - Type `regedit` and press Enter
   - Note the UAC (User Account Control) prompt - why is this important?

2. Identify the five main Registry hives:
   - HKEY_CLASSES_ROOT (HKCR)
   - HKEY_CURRENT_USER (HKCU)
   - HKEY_LOCAL_MACHINE (HKLM)
   - HKEY_USERS (HKU)
   - HKEY_CURRENT_CONFIG (HKCC)

**Task 1:** Create a table listing each hive and its primary purpose in your notes.

#### Part 2: User Activity Analysis (30 minutes)

1. Recently Used Programs:
   Navigate to:
   ```
   HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU
   ```
   
**Task 2:** 
- List the most recently executed commands
- Note the timestamp when available
- What might this information tell an investigator?

2. USB Device History:
   Navigate to:
   ```
   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR
   ```

**Task 3:**
- Document any USB devices found
- Record their first/last connection times
- Note the device serial numbers

#### Part 3: System Configuration Analysis (30 minutes)

1. Startup Programs:
   Navigate to:
   ```
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
   HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
   ```

**Task 4:**
- List all startup programs
- Research one unknown program online
- Explain why these keys are important in malware investigation

2. Network Interfaces:
   Navigate to:
   ```
   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\Tcpip\Parameters\Interfaces
   ```

**Task 5:**
- Document IP configurations
- Note any static IP assignments
- Explain how this might be useful in network forensics

#### Part 4: User Account Analysis (20 minutes)

1. User Profile List:
   Navigate to:
   ```
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList
   ```

**Task 6:**
- List all user profiles found
- Record their SIDs (Security Identifiers)
- Note profile paths and last write times

#### Part 5: Investigation Scenario (30 minutes)

**Scenario:** You're investigating potential data exfiltration. The suspect may have used USB devices and accessed unusual network locations.

**Task 7:** Using your knowledge from previous tasks:
1. Document all USB devices connected to the system
2. Check for recently run commands that might indicate file copying
3. Look for network locations in:
   ```
   HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\RunMRU
   HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths
   ```
4. Write a brief (200-word) investigator's note about your findings

### Lab Report Requirements

Submit a report including:
1. Completed tasks 1-7
2. Screenshots of key findings
3. Explanation of the forensic significance of each discovery
4. Reflection on what other types of evidence might complement Registry findings

### Bonus Challenge

Research and document three additional Registry locations that might contain valuable forensic evidence. Explain their significance and what type of investigation they would be useful for.

### References
- Windows Registry Forensics by Harlan Carvey
- SANS Windows Forensic Analysis poster
- Microsoft Windows Registry Guide

---

*Note to instructors: Consider having students work in pairs for this lab, with one student performing the analysis while the other documents findings. This can help prevent accidental Registry modifications while encouraging discussion and peer learning.*
