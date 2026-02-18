**Partitioning and Formatting a Disk Drive in Windows**
**Module 4 — Filesystem Types**
**📝Overview****
In this lab, I practiced how to partition and format a disk drive in Windows using both the Control Panel and Disk Management tools. 
Partitioning is essential because a file system cannot function without at least one partition. 
I worked with an offline disk, brought it online, created multiple partitions, and formatted them using different file systems.
**🎯 Objectives**
• 	Partition a disk using Windows GUI tools
• 	Shrink an existing volume to create new partitions
• 	Create a new simple volume
• 	Format a partition using a different file system
• 	Understand the impact of formatting and partitioning on data
**🛠️ Tools & Commands Used**
- Control Panel
- Computer Management
- Disk Management (diskmgmt.msc)
- Windows VM environment
**🧩 Objective 1 — Partitioning a Disk Using Control Panel
🚀 Steps I Completed**
• 	I opened Control Panel from the Start menu.
• 	Navigated to System and Security → Administrative Tools.
• 	Launched Computer Management.
• 	Selected Disk Management under the Storage section.
• 	Identified the second disk, which appeared as Offline with unallocated space.
• 	Right‑clicked the disk and selected Online to mount it.
• 	The disk was automatically assigned the letter D:.
• 	Since the entire disk was allocated to D:, I needed to shrink it before creating a new partition.
• 	Right‑clicked the D: volume and selected Shrink Volume.
• 	Entered 20,480 MB to shrink the disk, creating two partitions:
• 	D: — 30 GB
• 	Unallocated — 20 GB
• 	Right‑clicked the unallocated 20 GB and selected New Simple Volume.
• 	Accepted the default size to use all remaining space.
• 	Set the drive letter to E:.
• 	Chose the default file system and label.
• 	Completed the wizard and created the new partition.
• 	Verified the final layout:
• 	D: — 30 GB
• 	E: — 20 GB
• 	Confirmed the objective as Success: Drive split.
**🧩 Objective 2 — Formatting a Partition
⚙️ Steps I Completed**
• 	I selected the E: partition created in Objective 1.
• 	Right‑clicked the partition and chose Format.
• 	In the formatting dialog, selected FAT32 from the file system dropdown.
• 	A warning appeared explaining that formatting erases all data.
• 	Clicked OK to confirm and proceed.
• 	Windows formatted the E: partition to FAT32 and refreshed the disk layout.
• 	Verified the final configuration:
• 	D: — 30 GB (NTFS)
• 	E: — 20 GB (FAT32)
• 	Confirmed the objective as Success: Partition formatted.
**🐞 Problems & Fixes**
• 	Windows VM loading delay
• 	I waited a few minutes until the environment fully initialized.
• 	Disk not appearing immediately
• 	Refreshed Disk Management and confirmed disk status after bringing it online.
**📚 What I Learned**
• 	How to manage disks using Windows GUI tools
• 	How to bring an offline disk online
• 	How to shrink an existing volume to create new partitions
• 	How to create a new simple volume
• 	How to format a partition using different file systems
• 	Why formatting is destructive and requires caution
• 	How Windows updates disk configuration in real time
**📎 Related Files**
No external files generated for this lab.
**➡️ Next Steps**
• 	Complete Lab 02: Partitioning and Formatting a Disk Drive in Linux
• 	After both labs, prepare the Daily-IT-practice documentation for today
