# Computer Forensics Lab: USB and Mobile Device Registry Analysis on Windows 11

## Scenario Overview
Your task is to investigate potential unauthorized data access involving both a USB pen drive and a mobile phone connected to a Windows 11 system. You will analyze traces left behind in the Windows Registry to uncover relevant artifacts.

## Step-by-Step Instructions

### 1. Connecting Devices (Initial Setup)
- **Instructor Setup:** Connect a USB pen drive and a mobile phone to a Windows 11 lab PC for a brief period. This will generate traces in the Windows Registry for students to analyze.
- **Student Task:** Students should use regedit to access the Registry Editor for the subsequent steps.

### 2. Identifying USB Pen Drive Details
1. **Open the Registry Editor:**
  - Press Win + R to open the Run dialog
  - Type regedit and press Enter

2. **Navigate to the following registry key:**
  `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR`

3. **Task:**
  - Explore the subkeys listed under USBSTOR
  - Identify and document the following details of the connected USB pen drive:
    - Manufacturer
    - Model
    - Serial Number
    - Device Class (if available)

4. **Record your findings** in a lab report with screenshots of relevant keys and values.

### 3. Discovering Mobile Device Connection Information
1. **Navigate to the following registry key:**
  `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USB`

2. **Task:**
  - Locate entries related to the connected mobile phone
  - Document the following information:
    - Device name (e.g., phone model)
    - Manufacturer details
    - Unique identifiers or serial numbers

3. **Expected Outcome:**
  - Extract key details that show when the mobile device was connected

### 4. Viewing Recently Accessed Files on Connected Devices
1. **Navigate to the following registry key:**
  `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs`

2. **Task:**
  - Review the list of recently accessed files
  - Check for file paths that may point to the USB pen drive or mobile device

3. **Deliverable:**
  - List at least 5 recently accessed files and their corresponding paths
  - Take note of any files that were accessed from the USB or mobile device

### 5. Examining Drive Letter Assignments
1. **Navigate to the following registry key:**
  `HKEY_LOCAL_MACHINE\SYSTEM\MountedDevices`

2. **Task:**
  - Identify the drive letters assigned to the USB pen drive and mobile device (if applicable)
  - Record these assignments for future reference

3. **Expected Outcome:**
  - Correlate the drive letters with any accessed files or user activity

### 6. Investigating USB History Using Setupapi.dev.log
1. **Navigate to the Setupapi.dev.log file:**
  - Path: `C:\Windows\INF\setupapi.dev.log`

2. **Task:**
  - Open the file with a text editor (e.g., Notepad)
  - Search for entries related to the USB pen drive and mobile phone

3. **Expected Outcome:**
  - Find timestamped entries showing when the devices were connected
  - Correlate these timestamps with other activities on the system

### 7. Checking User Activity Associated with the Devices
1. **Navigate to the following registry key:**
  `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RunMRU`

2. **Task:**
  - Review the list of recently executed commands or programs
  - Identify any commands that may be related to the USB pen drive or mobile device

3. **Deliverable:**
  - Document any commands that indicate user interaction with files or data on connected devices

### 8. Investigating AutoRun and Potential Malware Entry Points
1. **Navigate to the following registry keys:**
  `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Run`
  `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`

2. **Task:**
  - Identify any programs or scripts that may have been triggered by connecting the USB pen drive or mobile device

3. **Deliverable:**
  - Determine if any entries are related to potentially malicious scripts
  - Report any suspicious entries

## Deliverables for Students
### Report:
- Document all findings, including screenshots, paths, and relevant details from each registry key
- Create a timeline of the device connections and any associated user activities
- Provide a summary of your analysis and recommendations for securing USB and mobile device access
