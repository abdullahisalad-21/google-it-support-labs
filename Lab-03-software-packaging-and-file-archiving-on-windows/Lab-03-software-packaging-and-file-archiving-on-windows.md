Software Packaging and File Archiving on Windows
🔍 Overview
In this lab, I practiced installing, removing, and managing software on Windows using both the GUI and PowerShell. 
I also worked with archived files, including extracting .tar files using 7‑Zip and creating .zip archives using PowerShell.
These tasks reflect real IT Support responsibilities involving software deployment, file management, and system administration.

🎯 Objectives
• 	Install software using the Windows GUI
• 	Extract files using 7‑Zip (GUI)
• 	Archive files into a .zip using PowerShell
• 	Install and uninstall software using PowerShell
• 	Uninstall GIMP using PowerShell

🛠️ Tools & Commands Used
GUI Tools
• 	Google Chrome
• 	File Explorer
• 	7‑Zip
• 	Windows Search

PowerShell Commands
cd C:\Users\Qwiklab\Documents\
Compress-Archive -Path Earth, Mercury, Venus Planets.zip

$VLC_URL = "https://get.videolan.org/vlc/last/win64/"
$GET_HTML = Invoke-WebRequest $VLC_URL
$FILE = $GET_HTML.Links | Select-Object @{Label='href';Expression={@{$true=$_.href}[$_.href.EndsWith('win64.exe')]}} | Select-Object -ExpandProperty href
$URL = ($VLC_URL+$FILE)
$DOWNLOAD_DIR = "C:\users\qwiklabs\Downloads\"
$OUTPUT_FILE = ($DOWNLOAD_DIR+$FILE)
(new-object System.Net.WebClient).DownloadFile($URL, $OUTPUT_FILE)
cmd.exe /c $OUTPUT_FILE /S
Get-Package -Name *vlc*
cmd.exe /c "C:\Program Files\GIMP 2\uninst\unins000.exe" /VERYSILENT /NORESTART
Get-Package

🧪 Steps I Completed
1️⃣ Installing Software Using Windows GUI (Sublime Text)
• 	I opened Google Chrome and navigated to https://www.sublimetext.com
• 	I downloaded the installer: sublime_text_build_4126_x64_setup.exe
• 	I opened the Downloads folder and ran the installer
• 	I accepted the default installation path and completed the setup
• 	I searched for “Sublime Text” using the Windows Search icon to verify installation
• 	I closed the program after confirming it launched successfully
2️⃣ Extracting Files Using 7‑Zip (GUI)
• 	I navigated to C:\Users\Qwiklab\Downloads
• 	I located example.tar and moved it to the Desktop
• 	I confirmed the move when prompted
• 	I right‑clicked the file → 7‑Zip → Extract Here
• 	I verified that the extracted files appeared on the Desktop
3️⃣ Archiving Files Using PowerShell
• 	I opened PowerShell as Administrator
• 	I navigated to the Documents folder
• 	I created a .zip archive using:
Compress-Archive -Path Earth, Mercury, Venus Planets.zip
• 	I confirmed that Planets.zip was created successfully
4️⃣ Installing VLC Using PowerShell
• 	I retrieved the VLC download directory using PowerShell
• 	I parsed the HTML to identify the correct .exe installer
• 	I downloaded the installer to the Downloads folder
• 	I installed VLC silently using:
cmd.exe /c $OUTPUT_FILE /S
• 	I verified the installation with:
Get-Package -Name *vlc*
5️⃣ Uninstalling GIMP Using PowerShell
• 	I opened PowerShell as Administrator
• 	I executed the silent uninstall command:
cmd.exe /c "C:\Program Files\GIMP 2\uninst\unins000.exe" /VERYSILENT /NORESTART
• 	I verified removal using:
Get-Package
🧩 Problems I Faced & How I Solved Them
❌ I couldn’t extract the .tar file in the Downloads folder
Cause: The folder didn’t allow extraction
Fix: I moved the file to the Desktop and extracted it successfully
❌ PowerShell commands failed without admin rights
Cause: I launched PowerShell normally
Fix: I reopened it using Run as Administrator
❌ The VLC installer wasn’t directly available
Cause: VLC uses dynamic download links
Fix: I used PowerShell to parse the HTML and extract the correct installer URL

📘 What I Learned
• 	How to install software using the Windows GUI
• 	How to extract .tar files using 7‑Zip
• 	How to create .zip archives using PowerShell
• 	How to install and uninstall software using PowerShell
• 	How to verify installations using Get-Package
• 	How GUI and CLI complement each other in Windows administration
📄 Related Files
• 	Planets.zip — archive created during the lab
• 	Extracted contents of example.tar
• 	PowerShell command history
🚀 Next Steps
• 	Practice using Expand-Archive and Compress-Archive with more complex paths
• 	Explore winget for simplified software installation
• 	Learn differences between MSI and EXE installers
• 	Continue documenting Windows package management labs for my portfolio
