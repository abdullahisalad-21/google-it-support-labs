# Commands and Actions Used in This Lab

## 🔧 Linux Commands Executed

### 1. Navigate to the documents directory
cd ../qwiklab/documents

### 2. View permissions of `important_document`
ls -l important_document

### 3. Apply strict permissions (700) to `important_document`
sudo chmod 700 important_document

### 4. Verify updated permissions
ls -l important_document

---

## Managing Permissions on `secret_folder`

### 5. Move to parent directory
cd ..

### 6. View current permissions of the folder
ls -ld secret_folder/

### 7. Add execute permission for the owner
sudo chmod u+x secret_folder/

### 8. Add write permission for the group
sudo chmod g+w secret_folder/

### 9. Remove read permission from the group
sudo chmod g-r secret_folder/

### 10. Remove read permission from others
sudo chmod o-r secret_folder/

### 11. Apply numeric permissions (720)
sudo chmod 720 secret_folder/

---

## Changing Ownership of `taco` Folder

### 12. View current permissions
ls -ld taco/

### 13. Change owner of the folder to user `cook`
sudo chown cook /home/qwiklab/taco

### 14. Verify updated ownership
ls -ld taco/

---

## Modifying Permissions on `not_so_important_document`

### 15. Navigate back to documents
cd documents/

### 16. View current permissions
ls -l not_so_important_document

### 17. Add execute permission for the owner
sudo chmod u+x not_so_important_document

### 18. Add write permission for the group
sudo chmod g+w not_so_important_document

### 19. Add read permission for all users
sudo chmod a+r not_so_important_document

### 20. Apply numeric permissions (764)
sudo chmod 764 not_so_important_document

---

## Updating Permissions on `public_document`

### 21. View current permissions
ls -l public_document

### 22. Grant full permissions to all users (symbolic)
sudo chmod a+rwx public_document

### 23. Apply numeric permissions (777)
sudo chmod 777 public_document

---

## 🧠 Key Takeaways From the Commands
- Linux permissions follow the **user–group–other** model.
- `chmod` supports both **symbolic** (u+x, g-w) and **numeric** (700, 764, 777) modes.
- `chown` is used to change file or folder ownership.
- `ls -l` and `ls -ld` are essential for verifying permissions and ownership.
- Using `sudo` is required when modifying files owned by root or other users.
