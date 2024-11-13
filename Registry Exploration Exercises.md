# Fun Registry Exploration Exercises
## Getting Comfortable with the Windows Registry

### Exercise 1: "What's Your Windows Story?"
**Objective:** Discover when Windows was installed on your computer.

1. Open Registry Editor (Windows + R, type "regedit")
2. Navigate to:
   ```
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion
   ```
3. Find the `InstallDate` value
4. Convert this UNIX timestamp to a readable date:
   - Open Command Prompt
   - Type: `date /d @YourTimestampHere`
   
**Discussion:** How long has this version of Windows been installed? Is this what you expected?

### Exercise 2: "Digital Time Capsule"
**Objective:** Find recently opened files and programs.

1. Navigate to:
   ```
   HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs
   ```
2. Look at the `.txt` subfolder
3. Right-click any value → Modify
4. Notice how Windows stores these names (in hexadecimal with ASCII text visible)
   
**Fun Task:** Can you find evidence of the last time you worked on a homework assignment?

### Exercise 3: "The Colorful Windows"
**Objective:** Discover hidden Windows color customization options.

1. Navigate to:
   ```
   HKEY_CURRENT_USER\Control Panel\Colors
   ```
2. Look at the different color values
3. Find "Window" and "WindowText"
4. *Optional observer task:* Note these values down for later restoration
5. **DO NOT MODIFY VALUES** - but discuss: What might happen if these were changed?

**Discussion:** Why would forensics investigators be interested in personalization settings?

### Exercise 4: "The Time Machine"
**Objective:** Find out about previously connected USB devices.

1. Navigate to:
   ```
   HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR
   ```
2. Expand the folders to find USB devices
3. Look for familiar device names (like your phone or USB drive brand)
4. Try to find the oldest USB device in the list

**Challenge:** Can you find evidence of the last time you connected your phone?

### Exercise 5: "The Software Historian"
**Objective:** Discover the history of installed programs.

1. Navigate to:
   ```
   HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
   ```
2. Look through the different GUIDs (those weird-looking folders)
3. Find:
   - The oldest installed program
   - The newest installed program
   - Any surprising programs you forgot were installed

**Fun Challenge:** Try to find evidence of a game you used to play but uninstalled!

### Exercise 6: "The Windows Time Capsule"
**Objective:** Find your Windows experience level.

1. Navigate to:
   ```
   HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths
   ```
2. Look for folders you've manually typed into Explorer
3. Think back - when did you access these locations?

**Discussion:** What could this tell an investigator about user behavior?

### Tips for Students
- Think of the Registry like a detective's notebook - everything leaves a trace
- Make connections between what you find and real-world actions
- Consider what each piece of information might tell an investigator
- Remember: Registry entries can tell us WHEN and WHAT, helping establish timelines

### Safety Notes
- 🚫 Never modify Registry values during these exercises
- ✔️ Only view and observe
- 📝 Take notes of anything interesting you find
- ❓ If in doubt, ask your instructor

### Wrap-up Questions
1. What was the most surprising thing you found?
2. What patterns did you notice about how Windows stores information?
3. How might these simple pieces of information be useful in a real investigation?
4. If you were investigating a computer, which of these locations would you check first and why?

---
*Remember: The goal is to get comfortable navigating the Registry while discovering how much information it actually stores about our computer usage. This builds foundation for more advanced forensic analysis later!*
