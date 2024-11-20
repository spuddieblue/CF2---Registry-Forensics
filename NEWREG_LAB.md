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