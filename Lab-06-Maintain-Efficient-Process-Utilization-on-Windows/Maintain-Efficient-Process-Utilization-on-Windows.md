**Lab 01 — Maintain Efficient Process Utilization on Windows
(Qwiklabs Version — Windows VM with fake processes)**

**🟦 Overview**
This lab focused on maintaining efficient process utilization on a Windows virtual machine.
I practiced identifying running processes, terminating a specific process, and terminating multiple processes using PowerShell and Task Manager.
These tasks simulate real IT Support responsibilities where runaway or suspicious processes must be safely identified and stopped.
**🎯 Objectives**
• 	Collect process information using Task Manager
• 	Terminate a specific process using PowerShell
• 	Terminate multiple processes using PowerShell
• 	Verify process termination and ensure system stability
**🛠️ Tools & Commands Used**
**Windows GUI**
• 	Task Manager
• 	Process sorting (CPU, Memory, Disk, GPU)
**PowerShell Commands**
Get-Process
Get-Process -Name "<process>"
taskkill /F /PID <PID>
Get-Process -Name "*pattern*"
**📝 Steps Completed**
1. Collected Process Information Using Task Manager
- Opened Task Manager using Ctrl + Shift + Esc
- Sorted processes by CPU, Memory, Disk, and GPU
- Observed system activity and identified processes consuming high CPU time
- Captured screenshots for documentation
2. Terminated a Specific Process
Process Identified
Get-Process -Name "totally_not_malicious"
Output showed:
• 	PID: 2760
• 	CPU Time: 2053 seconds
• 	Session: 0
• 	Process Name: totally_not_malicious
Termination Attempt
Incorrect syntax:
taskkill /F /PID [PROCESS ID]
Returned:
ERROR: Invalid argument/option - 'ID]'
Correct Termination
taskkill /F /PID 2760
Result:
SUCCESS: The process with PID 2760 has been terminated.
Verification
Get-Process -Name "totally_not_malicious"
Output:
Cannot find a process with the name...
3. Terminated Multiple Processes
Process Discovery
Get-Process -Name "*razzle*"
Returned two processes:
**| Process Name      |   PID | CPU(s)    |
|-------------------|-------|-----------|
| my_cat_razzle     |  3496 | 2208.16   |
| razzle_dazzle     |   308 | 2309.92   |**

Terminated Each Process
taskkill /F /PID 3496
taskkill /F /PID 308
Both returned:
SUCCESS: The process with PID XXXX has been terminated.
Verification
Get-Process -Name "*razzle*"
No output — all matching processes successfully terminated.
**🧩 Problems & Fixes**
Problem:
Used placeholder brackets literally in the taskkill command.
Fix:
Removed brackets and used the actual PID:
taskkill /F /PID 2760
**📚 What I Learned**
- How to identify and analyze processes using Task Manager
- How to use PowerShell to query, filter, and terminate processes
- How wildcard patterns help target multiple related processes
- How to verify process termination to ensure system stability
- How to troubleshoot command syntax errors

**📎 Related Files**
- Task Manager screenshots
- PowerShell output screenshots


