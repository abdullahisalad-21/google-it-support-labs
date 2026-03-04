**🖥️ Managing Services in Windows — C4 M2 L5
(Windows Service Control, IIS setup, and website hosting)**

**🔍 Overview**
In this lab, I practiced managing Windows services using both the Services console (services.msc) and PowerShell. 
I stopped and started system services, enabled services through alternative configuration paths, installed and started IIS, and finally hosted my own website. 
This lab strengthened my understanding of Windows service dependencies, startup types, and how Windows Server components like IIS are configured and managed in real IT environments.

**🎯 Objectives**
Stop the Themes service
Start the Performance Logs & Alerts service
Enable Auto Time Zone Updater through Date & Time settings
Install and start IIS
Create and serve a new website in IIS

**🛠️ Tools & Commands Used**
Services.msc — GUI for managing Windows services
PowerShell
Get-Service — View service status
Start-Service <name> — Start a service
Stop-Service <name> — Stop a service
Set-Service <name> -StartupType <type> — Change startup type
Install-WindowsFeature Web-WebServer,Web-Mgmt-Tools -IncludeAllSubFeature — Install IIS
IIS Manager
Add Website
Configure bindings
Set physical path
Web Browser — Verify website availability

**🧪 Steps I Completed**
1️⃣ Stopping the Themes Service
Opened Services.msc from the Windows Start Menu.
Located Themes (responsible for graphical themes and UI styling).
Verified it was Running.
Right‑clicked → Stop.
Confirmed the service status changed to Stopped.

2️⃣ Starting the Performance Logs & Alerts Service
Located Performance Logs & Alerts (pla) in Services.
Status was Stopped.
Right‑clicked → Start.
Verified the service status changed to Running.

2️⃣ (Part 2) Enabling Auto Time Zone Updater
Located Auto Time Zone Updater (tzautoupdate) in Services.
Status: Stopped
Startup Type: Disabled
Opened Date & Time settings by clicking the clock → Date and Time settings.
Enabled Set time zone automatically.
Returned to Services → Refresh.
Verified the service was now enabled (Startup Type changed from Disabled).

3️⃣ Installing and Starting IIS
Used PowerShell to install IIS and all management tools:
 Install-WindowsFeature Web-WebServer,Web-Mgmt-Tools -IncludeAllSubFeature


Installation succeeded with no reboot required.
Verified IIS Admin Service:
 Get-Service IISADMIN
 Status: Running
Verified the core web service:
 W3SVC — Running


IIS was fully operational.

4️⃣ Serving a New Website in IIS
Opened IIS Manager.
Expanded QWIKLABS-BB-XXX → Sites.
Right‑clicked Sites → Add Website.
Filled in the details:
Site name: Tashinho
Physical path: C:\Users\qwiklabs\amazingsite
Binding: HTTP on port 80
Clicked OK → IIS created and started the site.
Opened a browser and navigated to the External IP address.
Verified the custom website loaded successfully.

**🧩 Problems I Faced & How I Solved Them**
❌ Smart Card service failed to start
Cause: Startup type was Disabled.
 Fix:
Set-Service ScardSvr -StartupType Manual
Start-Service ScardSvr

Service started successfully.
❌ Some services could not be started directly
Cause: Dependencies or disabled startup types.
 Fix: Used Properties → Dependencies and adjusted startup types as needed.
❌ Auto Time Zone Updater disabled
Cause: Controlled by Date & Time settings.
 Fix: Enabled Set time zone automatically, then refreshed Services.

**📘 What I Learned**
How to manage Windows services using both GUI and PowerShell
How service startup types affect whether a service can start
How Windows ties system settings (like timezone) to underlying services
How to install and verify IIS components
How to create and configure a website in IIS
How to troubleshoot service startup failures using PowerShell

**📄 Related Files**
commands.md — Full list of PowerShell commands used
C:\Users\qwiklabs\amazingsite — Website content directory
IIS configuration — Stored in applicationHost.config

**🚀 Next Steps**
Practice configuring IIS bindings (hostnames, SSL certificates)
Explore advanced Windows service recovery options
Automate service management with PowerShell scripts
Deploy multiple sites and test virtual directories
