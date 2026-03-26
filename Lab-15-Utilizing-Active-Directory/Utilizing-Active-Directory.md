1. Overview ⭐
In this lab, I installed and configured Active Directory on a Windows Server VM, then practiced core identity‑management tasks using Active Directory Administrative Center (ADAC) and Group Policy Management. I created users and groups, modified group memberships, nested groups, and created a Group Policy Object (GPO) to enforce a desktop wallpaper for the Developers OU.

2. Objectives 🎯
Install and configure Active Directory using provided PowerShell scripts
Create a new user (Alex) and enable the account
Create a new group (Python Developers) and nest it under Developers
Add Alex to Python Developers
Remove Alosha from Java Developers and add them to Python Developers
Create and link a new GPO (“New Wallpaper”) to the Developers OU
Configure the GPO to enforce a specific wallpaper path

3. Tools & Commands Used 🛠️
Windows Tools
Active Directory Administrative Center (ADAC)
Group Policy Management Console (GPMC)
Group Policy Management Editor
Server Manager (indirectly via scripts)
PowerShell Commands
C:\Qwiklabs\ADSetup\active_directory_install.ps1
C:\Qwiklabs\ADSetup\configure_active_directory.ps1

Active Directory Actions
New User
Reset Password
Enable Account
New Group
Add to another group
Edit group membership
Create GPO
Edit GPO

4. Steps Completed 🧩
A. Installing Active Directory
Opened PowerShell as Administrator
Ran the installation script:
 C:\Qwiklabs\ADSetup\active_directory_install.ps1


VM rebooted automatically
Reconnected through the lab page
Ran the configuration script:
 C:\Qwiklabs\ADSetup\configure_active_directory.ps1


AD installation completed successfully

B. Creating User “Alex”
Opened Active Directory Administrative Center
Navigated to example (local) → Users
Created new user Alex (username: alex)
Attempted to enable account → failed due to missing password
Reset password and kept “User must change password at next logon” checked
Enabled the account successfully

C. Creating Group “Python Developers”
In ADAC → Users → New → Group
Created Python Developers
Right‑clicked group → Add to another group
Added it to Developers (nested group)

D. Adding Alex to Python Developers
Opened Python Developers group
Went to Members
Added Alex
Saved changes

E. Editing Memberships for Alosha
Located Alosha in Users
Opened Member Of tab
Removed Java Developers
Added Python Developers
Saved changes

F. Creating the “New Wallpaper” GPO
Opened Group Policy Management
Navigated to example.com → Developers OU
Right‑clicked Developers →
 Create a GPO in this domain, and Link it here
Named it New Wallpaper
Right‑clicked GPO → Edit
Navigated to:
 User Configuration
  → Policies
    → Administrative Templates
      → Desktop
        → Desktop


Opened Desktop Wallpaper
Set to Enabled
Wallpaper path:
 C:\Qwiklabs\wallpaper.jpg


Saved the policy
Verified settings under the GPO’s Settings tab

5. Problems & Fixes 🐞
Problem:
Attempting to enable Alex’s account resulted in:
“The password does not meet the length, complexity, or history requirement.”
Fix:
Used Reset Password
Set a valid password
Enabled the account successfully
No other issues occurred.

6. What I Learned 📚
How to install and configure Active Directory using automated scripts
How ADAC organizes users, groups, and domain objects
How to create and manage users and groups
How nested groups work (Python Developers → Developers)
How to modify group memberships when job roles change
How to create, link, and configure Group Policy Objects
How GPOs enforce settings across OUs
How centralized management simplifies enterprise administration

7. Related Files 📎
Wallpaper path used: C:\Qwiklabs\wallpaper.jpg
(Screenshots would be added here if captured during the session)

