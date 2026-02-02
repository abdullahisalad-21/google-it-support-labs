# Commands and Actions Used in This Lab

## 🔧 PowerShell Commands Executed

### 1. Open PowerShell as Administrator
Used to gain elevated privileges required for modifying ACLs.
Start-Process powershell -Verb runAs

### 2. Navigate to the target directory
cd C:\Users\Student\Documents

### 3. View permissions on a file or folder
icacls .\Reports icacls .\Reports\summary.txt Get-Acl .\Reports | Format-List

### 4. Grant permissions to a user
Example: Give Modify permissions to user `student1` on a folder.
icacls .\Reports /grant student1:M

### 5. Grant Full Control
icacls .\Reports /grant student1:F

### 6. Remove permissions
icacls .\Reports /remove student1

### 7. Disable inheritance
icacls .\Reports /inheritance:d

### 8. Enable inheritance
icacls .\Reports /inheritance:e

### 9. Reset permissions to inherited defaults
icacls .\Reports /reset

### 10. View group membership
whoami /groups



---

## 🖥️ GUI Actions Performed

### File Explorer → Properties → Security Tab
- Viewed existing permissions  
- Checked which users and groups had access  
- Opened “Advanced Security Settings”  
- Modified group permissions  
- Enabled/disabled inheritance  
- Verified changes after using ICACLS  

---

## 🧩 Errors Encountered & Fixes

### ❌ “Access is denied”
**Cause:** PowerShell not running as Administrator  
**Fix:** Relaunched using  
Start-Process powershell -Verb runAs


### ❌ Permission changes not applying
**Cause:** Inheritance overriding manual ACL changes  
**Fix:**  
icacls <folder> /inheritance:d


### ❌ Incorrect permission level applied
**Cause:** Confusion between `M` (Modify) and `F` (Full Control)  
**Fix:** Re-applied correct permission using  
icacls <folder> /grant user:F

---

## 🧠 Key Takeaways From the Commands
- ICACLS is the primary tool for managing ACLs in Windows via CLI.  
- Permissions can be controlled per user or group.  
- Inheritance can override manual changes if not disabled.  
- GUI and CLI should be used together to verify accuracy.
