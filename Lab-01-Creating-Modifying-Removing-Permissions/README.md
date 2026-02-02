# Creating, Modifying, and Removing File and Folder Permissions in Windows

## 🔍 Overview
This lab focused on understanding and managing Windows file and folder permissions using both the GUI and PowerShell. I practiced viewing ACLs, granting and removing permissions, modifying inheritance, and validating changes using ICACLS. The exercises simulated real IT Support tasks involving user access control and troubleshooting permission issues.

## 🎯 Objectives
- Run PowerShell with administrative privileges  
- View file and folder permissions using GUI and CLI  
- Modify NTFS permissions using `icacls`  
- Grant and remove access for specific users and groups  
- Enable and disable inheritance on folders  
- Verify permission changes using `icacls` and `Get-Acl`  

## 🛠️ Tools & Commands Used

### PowerShell
- `icacls <path>` — View or modify permissions  
- `icacls <path> /grant user:perm` — Grant permissions  
- `icacls <path> /remove user` — Remove permissions  
- `icacls <path> /inheritance:e|d` — Enable/disable inheritance  
- `icacls <path> /reset` — Reset to inherited defaults  
- `Get-Acl` — View ACL details  
- `whoami /groups` — View group membership  
- `Start-Process powershell -Verb runAs` — Run PowerShell as Administrator  

### GUI
- File Explorer → Properties → Security tab  
- Advanced Security Settings  
- Group and user permission management  

## 🧪 Steps I Completed
1. Opened PowerShell with administrative privileges.  
2. Viewed file and folder permissions using `icacls` and `Get-Acl`.  
3. Removed permissions from specific users (e.g., Kara).  
4. Granted read, write, and full control permissions to users.  
5. Modified permissions on multiple folders (Secret, Music, Documents).  
6. Adjusted inheritance settings when permission changes didn’t apply.  
7. Verified all changes after each modification.  

## 🧩 Problems I Faced & How I Solved Them

### ❌ Access denied errors  
**Cause:** PowerShell was not running as Administrator  
**Fix:** Relaunched using:  
`Start-Process powershell -Verb runAs`

### ❌ Permission changes not applying  
**Cause:** Inheritance overriding manual ACL changes  
**Fix:** Disabled inheritance before modifying permissions

### ❌ Incorrect permission levels applied  
**Cause:** Confusion between R, W, M, and F  
**Fix:** Re-applied correct permissions using `icacls /grant`

## 📘 What I Learned
- How Windows ACLs work (DACLs, ACEs, inheritance)  
- How to manage permissions using ICACLS  
- How to troubleshoot permission errors  
- How GUI and CLI complement each other in Windows administration  
- How to verify and validate permission changes like a real IT Support technician  

## 📄 Related Files
- **commands.md** — Full list of actual PowerShell commands executed in this lab  

## 🚀 Next Steps
- Practice advanced ICACLS flags  
- Explore SACLs and auditing  
- Continue documenting Windows permission labs for my IT portfolio  
