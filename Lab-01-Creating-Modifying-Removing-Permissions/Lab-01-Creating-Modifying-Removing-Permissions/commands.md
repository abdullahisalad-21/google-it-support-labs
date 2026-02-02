# Commands and Actions Used in This Lab

## 🔧 PowerShell Commands Executed

### 1. View permissions on `important_document`
ICACLS C:\Users\Qwiklab\Documents\important_document

### 2. Remove Kara’s permissions
ICACLS C:\Users\Qwiklab\Documents\important_document /remove "Kara"

### 3. Verify removal
ICACLS C:\Users\Qwiklab\Documents\important_document

### 4. Grant Kara read-only access
ICACLS C:\Users\Qwiklab\Documents\important_document /grant "Kara:(R)"

### 5. Verify updated permissions
ICACLS C:\Users\Qwiklab\Documents\important_document

---

## Managing Permissions on the `Secret` Folder

### 6. View current ACLs
ICACLS C:\Users\Qwiklab\Secret\

### 7. Grant Phoebe read access
ICACLS C:\Users\Qwiklab\Secret\ /grant "Phoebe:(R)"

### 8. Verify updated ACLs
ICACLS C:\Users\Qwiklab\Secret\

### 9. Grant Kara write access
ICACLS C:\Users\Qwiklab\Secret\ /grant "Kara:(W)"

### 10. Verify updated ACLs
ICACLS C:\Users\Qwiklab\Secret\

---

## Modifying Permissions on the `Music` Folder

### 11. View current permissions
ICACLS C:\Users\Qwiklab\Music\

### 12. Remove Everyone’s permissions
ICACLS C:\Users\Qwiklab\Music\ /remove "Everyone"

### 13. Re‑grant Everyone read-only access
ICACLS C:\Users\Qwiklab\Music\ /grant "Everyone:(R)"

### 14. Verify updated ACLs
ICACLS C:\Users\Qwiklab\Music\

---

## Updating Permissions on `not_so_important_document`

### 15. View current ACLs
ICACLS C:\Users\Qwiklab\Documents\not_so_important_document

### 16. Grant Authenticated Users write access
ICACLS C:\Users\Qwiklab\Documents\not_so_important_document /grant "Authenticated Users:(W)"

### 17. Verify updated ACLs
ICACLS C:\Users\Qwiklab\Documents\not_so_important_document

---

## Updating Permissions on `public_document`

### 18. View ACLs
ICACLS C:\Users\Qwiklab\Documents\public_document

### 19. Grant Everyone read access
ICACLS C:\Users\Qwiklab\Documents\public_document /grant "Everyone:(R)"

### 20. Verify updated ACLs
ICACLS C:\Users\Qwiklab\Documents\public_document

---

## 🖥️ GUI Actions Performed

### File Explorer → Properties → Security Tab
- Viewed existing permissions  
- Checked which users and groups had access  
- Opened “Advanced Security Settings”  
- Verified permission changes after running ICACLS  

---

## 🧩 Errors Encountered & Fixes

### ❌ “Access is denied”
**Cause:** PowerShell not running as Administrator  
**Fix:** Relaunched PowerShell with elevated privileges.

### ❌ Permission changes not applying
**Cause:** Inheritance overriding manual ACL changes  
**Fix:** Disabled inheritance when needed.

### ❌ Confusion between permission levels
**Cause:** R (Read) vs W (Write) vs RX (Read & Execute)  
**Fix:** Re-applied correct permissions using ICACLS.

---

## 🧠 Key Takeaways From the Commands
- ICACLS is a powerful tool for managing NTFS permissions.  
- Permissions can be granted or removed for specific users and groups.  
- Verifying ACLs after each change ensures accuracy.  
- GUI and CLI complement each other in Windows administration.
- 
