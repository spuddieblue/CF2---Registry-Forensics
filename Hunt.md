# Digital Forensics Lab: The Case of the Compromised Influencer

## Background

You are a digital forensics investigator working with local law enforcement. A popular social media influencer, Alex Chen, reported that someone has been accessing their social media accounts and personal files without authorization. The suspect appears to be using Alex's own computer to gain access. You've been provided with a forensic image of Alex's Windows computer and must analyze the Windows Registry to uncover evidence of unauthorized access and potential data theft.

## Learning Objectives

- Understand Windows Registry structure and key forensic artifacts
- Use Registry analysis tools to extract digital evidence
- Practice timeline analysis and evidence correlation
- Document findings in a forensically sound manner

## Required Tools

- Registry Explorer/RECmd
- Timeline Explorer
- Notepad++ or similar text editor
- Access to provided forensic image

## Case Details

Alex reports:
- Strange posts appearing on their social media from their device
- Files being accessed at unusual hours
- New applications installed without their knowledge
- Suspicious USB devices may have been connected
- Unusual remote access attempts

## Lab Tasks

### Part 1: Initial Analysis (30 minutes)

1. Load the provided registry hives using Registry Explorer
2. Document the following information:
   - Computer name
   - Windows version
   - Time zone settings
   - Last shutdown time

### Part 2: User Activity Analysis (45 minutes)

1. Examine the following registry locations:
   ```
   NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\RecentDocs
   NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Explorer\TypedPaths
   ```
2. Create a timeline of file access activity
3. Note any suspicious file names or patterns
4. Document any evidence of social media-related activity

### Part 3: USB Device Investigation (30 minutes)

1. Analyze USB device history:
   ```
   SYSTEM\CurrentControlSet\Enum\USBSTOR
   SYSTEM\CurrentControlSet\Enum\USB
   ```
2. Create a list of all USB devices connected
3. Record first/last connection times
4. Identify any devices connected during suspicious timeframes

### Part 4: Software Evidence (45 minutes)

1. Examine installed software:
   ```
   SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall
   NTUSER.DAT\Software\Microsoft\Windows\CurrentVersion\Run
   ```
2. Look for:
   - Remote access tools
   - File transfer applications
   - Keyloggers or monitoring software
   - Recently installed programs

### Part 5: Remote Access Analysis (30 minutes)

1. Check Remote Desktop Protocol (RDP) evidence:
   ```
   SYSTEM\CurrentControlSet\Control\Terminal Server
   NTUSER.DAT\Software\Microsoft\Terminal Server Client\Servers
   ```
2. Document:
   - RDP connection history
   - Authentication attempts
   - Client usernames
   - Remote IP addresses

## Evidence Collection Requirements

For each piece of evidence found, document:
1. Registry key path
2. Key last write time
3. Value name and data
4. Relevance to the investigation
5. Screenshot of the evidence (when applicable)

## Questions to Answer

1. What evidence suggests unauthorized access to Alex's computer?
2. Can you establish a timeline of suspicious activities?
3. Were any unauthorized USB devices connected?
4. What software may have been used to compromise the system?
5. Is there evidence of remote access attempts?

## Bonus Challenge

Find evidence of potential data exfiltration through:
- Cloud storage applications
- Email clients
- File transfer programs

## Lab Report Requirements

Submit a professional forensics report including:
1. Executive summary
2. Methodology
3. Findings
   - Timeline of events
   - Evidence list
   - Registry artifacts discovered
4. Analysis and conclusions
5. Supporting screenshots
6. Recommendations for securing the system

## Scoring Rubric

- Evidence Discovery (40%)
  - Complete documentation of registry artifacts
  - Accurate timeline creation
  - Thorough USB device analysis
  
- Analysis & Correlation (30%)
  - Logical connections between evidence
  - Supported conclusions
  - Identification of attack methods
  
- Documentation (20%)
  - Professional report format
  - Clear screenshots
  - Proper evidence handling
  
- Bonus Findings (10%)
  - Additional relevant evidence
  - Creative investigation methods
  - Extra insights discovered

## Tips for Success

- Take detailed notes during your investigation
- Create a timeline as you discover evidence
- Look for correlations between different registry artifacts
- Consider the context of each piece of evidence
- Document your methodology carefully
- Take clear screenshots of important findings

Good luck, investigator! Remember to follow proper forensic procedures and maintain a clear chain of custody in your documentation.
