**🪵 Lab 1 — Using Logs to Track Down an Issue in Windows
🎯 Overview**
This lab focused on using Windows Event Viewer to identify and resolve five system issues by following log entries, correlating timestamps, and applying targeted fixes. 
Each issue required hands‑on troubleshooting using skills from earlier modules: file management, permissions, software updates, and process control.
**🧠 Objectives**
Interpret Windows application logs to identify system issues.
Resolve low disk space caused by a large file.
Remove a corrupted file from the Users directory.
Update outdated software (VLC Media Player).
Terminate a malicious process using PowerShell.
Fix incorrect NTFS permissions on a sensitive file.
**🛠️ Tools & Commands Used**
Event Viewer (eventvwr.msc)
File Explorer (search, delete, permissions)
VLC Media Player (Help → Check for Updates)
PowerShell
Get-Process -Name <process>
taskkill /f /PID <id>
NTFS Permissions GUI (Properties → Security)
**📝 Steps Completed
1️⃣ Low Disk Space (Event ID 5)**
Opened Event Viewer → Windows Logs → Application.
Located the log entry: Source: Qwiklab, Event ID: 5.
Log indicated a large file consuming disk space.
Used File Explorer → searched C:\ for Size → Gigantic (>4 GB).
Identified an almost 10 GB file.
Deleted the file permanently (too large for Recycle Bin).
**2️⃣ Corrupted File in Users Directory**
Found the Qwiklab log referencing a corrupted file.
Navigated to C:\Users.
Located the file named corrupted file.
Deleted it to resolve the issue.
**3️⃣ Outdated VLC Media Player**
Opened VLC Media Player.
Navigated to Help → Check for Updates.
Installed the latest version using the built‑in updater.
Relaunched VLC and confirmed the updated version.
**4️⃣ Malicious Process Running**
Used PowerShell to search for the process:
Get-Process -Name "totally_not_malicious"
Identified PID 7792.
Terminated it using:
taskkill /f /PID 7792
Verified the process no longer existed.
**5️⃣ Incorrect File Permissions**
Navigated to C:\Users\Temp.
Located super_secret_file.txt.
Opened Properties → Security → Edit.
Added Everyone and granted Write permission.
Verified the permission change.
**📚 What I Learned**
How to use Event Viewer as a primary troubleshooting tool.
How to correlate log entries with real system behavior.
How to identify and remove large files causing disk issues.
How to update software using built‑in application tools.
How to terminate malicious or stuck processes using PowerShell.
How to modify NTFS permissions to restore proper access control.
**📎 Related Files**
No external files generated; all work performed inside the Windows VM.
**🚀 Next Steps**
Practice creating custom Event Viewer filters for faster troubleshooting.
Build a reference list of common Windows Event IDs.
Repeat similar log‑analysis workflows on Linux for cross‑platform mastery
