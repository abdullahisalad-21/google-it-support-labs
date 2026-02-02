# Creating, Modifying, and Removing File and Folder Permissions in Windows

## 🔍 Overview
This lab introduced the fundamentals of managing file and folder permissions on a Windows system. Using PowerShell and the GUI, I practiced viewing, modifying, granting, and removing permissions for users and groups. The lab focused on understanding how Windows Access Control Lists (ACLs) work and how to apply permissions using ICACLS.

## 🎯 Objectives
- Access administrative privileges in Windows PowerShell.
- View file and folder permissions using both the GUI and PowerShell.
- Modify permissions for files and directories using ICACLS.
- Grant and remove permissions for users and groups.
- Manage group permissions using the Windows GUI and PowerShell.

## 🛠️ Tools & Commands Used
### PowerShell
- `Get-Acl` — View ACL permissions.
- `Set-Acl` — Apply modified ACLs.
- `icacls` — Grant, remove, and modify permissions.
- `whoami /groups` — View group membership.
- `Start-Process powershell -Verb runAs` — Run PowerShell as Administrator.

### GUI
- File Explorer → Properties → Security tab  
- Advanced Security Settings  
- Group permission management  

## 🧪 Steps I Completed
1. Opened PowerShell with administrative privileges.
2. Viewed file and folder permissions using both GUI and CLI.
3. Granted Modify and Full Control permissions to specific users.
4. Removed permissions from users and groups.
5. Enabled and disabled inheritance on folders.
6. Verified all changes using ICACLS and Get-Acl.

## 🧩 Problems I Faced & How I Solved Them
- **Access denied errors**  
  *Solution:* Relaunched PowerShell as Administrator.

- **Permission changes not applying**  
  *Solution:* Disabled inheritance before modifying ACLs.

- **Incorrect permission levels**  
  *Solution:* Re-applied correct permissions using ICACLS.

## 📘 What I Learned
- How Windows ACLs work (DACLs, ACEs, inheritance).
- How to manage permissions using ICACLS.
- How to troubleshoot permission errors.
- How GUI and CLI tools complement each other in Windows administration.

## 🚀 Next Steps
- Practice advanced ICACLS flags.
- Explore SACLs and auditing.
- Document additional Windows permission labs for my IT portfolio.
