# Creating, Modifying, and Removing File and Folder Permissions in Linux

## 🔍 Overview
This lab focused on understanding and managing Linux file and folder permissions using Bash. I practiced viewing permissions, modifying them using symbolic and numeric modes, changing ownership, and validating changes. The tasks simulated real IT Support responsibilities involving securing files, adjusting access, and troubleshooting permission issues.

## 🎯 Objectives
- Understand Linux permission structure (user, group, other)
- Modify permissions using `chmod` (symbolic and numeric)
- Change file and folder ownership using `chown`
- Verify permissions using `ls -l` and `ls -ld`
- Apply correct permissions to secure files and directories

## 🛠️ Tools & Commands Used
- `ls -l` — View file permissions  
- `ls -ld` — View folder permissions  
- `chmod` — Modify permissions (symbolic and numeric)  
- `chown` — Change file or folder owner  
- `sudo` — Run commands with elevated privileges  

## 🧪 Steps I Completed

### **Important Document**
1. Navigated to the documents directory  
2. Viewed permissions of `important_document`  
3. Applied strict permissions using `chmod 700`  
4. Verified updated permissions  

### **Secret Folder**
5. Viewed folder permissions  
6. Added execute permission for the owner  
7. Added write permission for the group  
8. Removed read permission from group and others  
9. Applied numeric permissions (`chmod 720`)  

### **Taco Folder**
10. Viewed folder permissions  
11. Changed ownership of the folder to user `cook`  
12. Verified updated ownership  

### **Not So Important Document**
13. Viewed permissions  
14. Added execute permission for the owner  
15. Added write permission for the group  
16. Added read permission for all users  
17. Applied numeric permissions (`chmod 764`)  

### **Public Document**
18. Viewed permissions  
19. Granted full permissions using symbolic mode (`a+rwx`)  
20. Applied numeric permissions (`chmod 777`)  

## 🧩 Problems I Faced & How I Solved Them

### ❌ Permission denied errors  
**Cause:** Attempting to modify files owned by root  
**Fix:** Used `sudo` to run commands with elevated privileges  

### ❌ Incorrect numeric permissions  
**Cause:** Misunderstanding rwx → numeric mapping  
**Fix:** Reviewed permission values and reapplied correct numeric mode  

### ❌ Ownership not updating  
**Cause:** Missing group specification  
**Fix:** Used full syntax:  
`sudo chown user:group filename`  

## 📘 What I Learned
- How Linux permissions work at the user, group, and other levels  
- How to use symbolic and numeric modes with `chmod`  
- How to change ownership and group membership using `chown`  
- How to verify permissions using `ls -l` and `ls -ld`  
- How to troubleshoot permission issues like a real Linux administrator  

## 📄 Related Files
- **commands.md** — Full list of actual Linux commands executed in this lab  

## 🚀 Next Steps
- Practice advanced permission flags (sticky bit, setuid, setgid)  
- Explore ACLs using `getfacl` and `setfacl`  
- Continue documenting Linux permission labs for my IT portfolio  
