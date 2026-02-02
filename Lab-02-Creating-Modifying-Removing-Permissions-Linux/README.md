# Creating, Modifying, and Removing File and Folder Permissions in Linux

## 🔍 Overview
This lab introduces the fundamentals of managing file and folder permissions on a Linux system. Using Bash commands, I practiced viewing, modifying, and fixing permissions and ownership for various files and directories.

## 🎯 Objectives
- Understand Linux permission structure (r, w, x)
- Modify permissions using `chmod`
- Change file and folder ownership using `chown` and `chgrp`
- Verify permissions using `ls -l`
- Apply correct permissions to secure files and directories

## 🛠️ Tools & Commands Used
- `ls -l` — View permissions
- `chmod` — Modify permissions
- `chown` — Change file owner
- `chgrp` — Change group ownership
- `sudo` — Run commands with elevated privileges

## 🧪 Steps I Completed
1. Viewed permissions of files and directories using `ls -l`.
2. Identified incorrect permissions and ownership.
3. Applied correct read, write, and execute permissions using `chmod`.
4. Changed ownership of files and folders using `chown`.
5. Updated group ownership using `chgrp`.
6. Verified all changes after applying modifications.

## 🧩 Problems I Faced & How I Solved Them
- **Permission denied errors**  
  *Solution:* Used `sudo` to run commands with elevated privileges.

- **Incorrect numeric permissions**  
  *Solution:* Reviewed rwx mapping and reapplied correct values.

- **Ownership not updating**  
  *Solution:* Used full syntax: `sudo chown user:group filename`

## 📘 What I Learned
- How Linux permissions work at the user, group, and other levels.
- How to use symbolic and numeric modes with `chmod`.
- How to change ownership and group membership of files.
- How to verify permissions and troubleshoot access issues.

## 🚀 Next Steps
- Practice advanced permission flags (sticky bit, setuid, setgid).
- Explore ACLs using `getfacl` and `setfacl`.
