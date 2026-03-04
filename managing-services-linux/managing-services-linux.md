**🔧 Managing Services in Linux — C4 M2 L5**

**🔍 Overview**
In this lab, I practiced managing Linux system services using the service command and configuration files. 
I worked with two core services: rsyslog, which handles system logging, and CUPS, which manages printing. 
I stopped, started, restarted, and reloaded services, fixed a broken configuration, and modified log levels to understand how Linux services behave and how to troubleshoot them like a real system administrator.

**🎯 Objectives**
Stop and start the rsyslog service
Diagnose and fix a CUPS service failure
Change the CUPS log level from warn to debug
Revert the CUPS log level back to normal
Verify service behavior using logs and status checks

**🛠️ Tools & Commands Used**
service <name> status — Check service status
service <name> stop — Stop a service
service <name> start — Start a service
service <name> restart — Restart a service
service <name> reload — Reload configuration
logger <message> — Generate test log entries
tail /var/log/syslog — View system logs
nano /etc/cups/cupsd.conf — Edit CUPS configuration
ls -l /etc/cups — Inspect configuration directory
/var/log/cups/error_log — Verify CUPS log level

**🧪 Steps I Completed**
**1️⃣ Stopping and Starting the rsyslog Service**
Listed all services:
 sudo service --status-all


Verified rsyslog was running:
 sudo service rsyslog status


Generated a test log entry:
 logger This is a test log entry


Confirmed the log entry in /var/log/syslog.
Stopped the service:
 sudo service rsyslog stop


Verified it was not running.
Started rsyslog again:
 sudo service rsyslog start


Confirmed new log entries were being written.

**2️⃣ Fixing the CUPS Service**
Checked service status and saw CUPS was failing:
 cupsd is not running ... failed!


Inspected /etc/cups and found cupsd.conf missing but cupsd.conf.old present.
Restored the correct configuration:
 sudo mv /etc/cups/cupsd.conf.old /etc/cups/cupsd.conf


Started CUPS successfully:
 sudo service cups start


Verified:
 cupsd is running.



**3️⃣ Changing the Log Level for CUPS**
Checked the CUPS log directory:
 sudo ls -l /var/log/cups


Edited the configuration file:
 sudo nano /etc/cups/cupsd.conf


Changed:
 LogLevel warn
 to:
 LogLevel debug


Restarted the service to apply changes:
 sudo service cups restart


Verified debug-level logs in:
 sudo cat /var/log/cups/error_log
 Debug entries (D [...]) confirmed the change.

**4️⃣ Reverting the Log Level for CUPS**
Reopened the configuration file:
 sudo nano /etc/cups/cupsd.conf


Restored:
 LogLevel warn


Reloaded the service (no need to stop it):
 sudo service cups reload


Verified the service was running normally:
 cupsd is running.



**🧩 Problems I Faced & How I Solved Them**
❌ CUPS service failing to start
Cause: Missing or corrupted cupsd.conf file.
 Fix: Restored backup file cupsd.conf.old → service started successfully.
❌ rsyslog warnings in syslog
Cause: imklog module cannot access /proc/kmsg in restricted environments.
 Fix: No action required — informational only. Verified service functionality using logger.
❌ No debug logs appearing initially
Cause: CUPS needed a restart after modifying cupsd.conf.
 Fix: Used sudo service cups restart to reload configuration.

**📘 What I Learned**
How to manage Linux services using the service command
How to diagnose service failures by inspecting configuration directories
How CUPS logging works and how to adjust verbosity
The difference between restart and reload
How to validate service behavior using log files
How to troubleshoot system logging using logger and syslog

**📄 Related Files**
commands.md — Contains the full list of commands executed during this lab
/etc/cups/cupsd.conf — Modified configuration file
/var/log/cups/error_log — Verified debug-level logging

**🚀 Next Steps**
Practice managing services using systemctl (modern alternative to service)
Explore CUPS web interface on port 631
Experiment with additional log levels like debug2
Practice troubleshooting other services such as ssh, cron, and apache2
