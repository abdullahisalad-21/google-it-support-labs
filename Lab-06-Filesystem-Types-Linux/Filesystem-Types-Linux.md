**📝 Overview**
In this lab, I practiced how to partition and format a disk drive in Linux. 
I identified mounted and unmounted block devices, deleted existing partitions, created new partitions.  
I changed partition types, formatted a partition with a Linux file system, and mounted it to the filesystem. 
This reinforced my understanding of Linux disk utilities and low‑level storage management.

**🎯 Objectives**
• 	Identify mounted vs unmounted block devices
• 	Delete existing partitions on an unmounted disk
• 	Create new partitions using fdisk
• 	Change partition types (Linux swap)
• 	Format a partition using mkfs
• 	Mount a new Linux file system
• 	Verify disk structure and mount points

**🛠️ Tools & Commands Used**
- lsblk
- df -h
- sudo fdisk /dev/<device>
- mkfs -t ext4
- mount
- lsblk (verification)

**🧩 Objective 1 — Partition the Unmounted Drive
🔍 Steps I Completed**
- Ran lsblk to examine block devices.
- Identified that /etc/hosts was mounted on sda, meaning:
- Mounted drive = sda
- Unmounted drive = sdb
- Opened fdisk on the unmounted drive:
- sudo fdisk /dev/sdb
- Deleted all 12 default partitions by repeatedly using:
d
<Enter>
- Verified the disk was empty using:
p
- Created a 1GB partition (/dev/sdb1):
- n
<Enter>
<Enter>
2097200
- Created a 9GB partition (/dev/sdb2):
n
<Enter>
<Enter>
<Enter>
- Changed partition 1 to Linux swap:
t
1
L
19
- Verified and wrote changes:
 v
 w
**🧩 Objective 2 — Format the Second Partition
⚙️ Steps I Completed**
- Formatted the second partition (/dev/sdb2) as ext4:
- sudo mkfs -t ext4 /dev/sdb2
**🧩 Objective 3 — Mount the New ext4 Partition
📂 Steps I Completed**
- Mounted the new ext4 partition to /home/my_drive:
- sudo mount /dev/sdb2 /home/my_drive
-  Verified the mount using:
-  lsblk
- → /dev/sdb2 correctly mounted at /home/my_drive.

  **🐞 Problems & Fixes**
• 	Default partitions on sdb
• 	I removed all 12 using  before creating new ones.
• 	Ensuring correct device selection
• 	I used  and  to confirm mounted vs unmounted disks.

**📚 What I Learned**
• 	How to identify mounted and unmounted block devices
• 	How to delete, create, and modify partitions using 
• 	How to assign partition types (Linux swap)
• 	How to format partitions using Linux file systems
• 	How to mount new file systems and verify mount points
• 	How Linux represents storage devices and partitions



