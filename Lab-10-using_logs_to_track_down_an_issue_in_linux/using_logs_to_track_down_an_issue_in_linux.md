**🐧 Lab Using Logs to Track Down an Issue in Linux
🎯 Overview**
In this lab, I used Linux system logs to identify and resolve five issues. 
I relied on /var/log/syslog as my main source of truth, followed each error message, and applied Linux administration skills including file removal, package repair, 
process management, and permission modification.
**🧠 Objectives**
Interpret Linux log files to identify system issues.
Resolve low disk space caused by a massive file.
Remove a corrupted file from the home directory.
Repair broken packages and verify VLC installation.
Terminate a malicious process using Linux process tools.
Fix incorrect file permissions using chmod.
**🛠️ Tools & Commands Used**
cat /var/log/syslog
du -a | sort -n -r | head
rm
apt-get -f install
apt-cache policy <package>
ps -aux | grep <process>
kill <PID>
chmod
**📝 Steps Completed
1️⃣ Low Disk Space**
🔍 Log entry
Qwiklab Error: Disk space is super low, fix it!
🛠️ What I did
I searched for the largest files:
sudo du -a /home | sort -n -r | head -n 5
I found:
/home/lab/storage/ultra_mega_large.txt
I removed it:
sudo rm /home/lab/storage/ultra_mega_large.txt
**2️⃣ Corrupted File in /home/lab**
🔍 Log entry
Qwiklab Error: There is a corrupted file found in /home/lab/corrupted_file. Remove this file.
🛠️ What I did
I navigated to the directory:
cd /home/lab
ls
I removed the corrupted file:
sudo rm corrupted_file
**3️⃣ VLC Package Out of Date**
🔍 Log entry
Qwiklab Error: VLC - Package out of date, upgrade to the latest version.
🛠️ What I did
I returned to my home directory:
cd ~
I repaired missing dependencies:
sudo apt-get -f install
I checked VLC package status:
apt-cache policy vlc
**4️⃣ Malicious Process Running**
🔍 Log entry
Qwiklab Error: Process: [bash /home/totally_not_malicious] is malicious, terminate the process immediately!
🛠️ What I did
I located the process:
ps -aux | grep "totally_not_malicious"
I killed it using the PID:
sudo kill <PID>
I verified it was gone:
ps -aux | grep "totally_not_malicious"
**5️⃣ Incorrect Permissions on Secret File**
🔍 Log entry
Qwiklab Error: Permission Denied: /home/lab/super_secret_file.txt
🛠️ What I did
I navigated to the directory:
cd /home/lab
I granted full permissions (rwx for everyone):
sudo chmod 777 super_secret_file.txt
**📚 What I Learned**
How to use Linux logs to identify system issues.
How to locate large files using du and fix disk space problems.
How to remove corrupted files safely.
How to repair broken packages using apt-get -f install.
How to inspect and terminate malicious processes.
How to modify file permissions using chmod.
**📎 Related Files**
No external files generated; all work performed inside the Linux VM.
**🚀 Next Steps**
Practice using journalctl for deeper log analysis.
Explore advanced process management with top, htop, and nice.
Continue building cross‑platform troubleshooting workflows.
