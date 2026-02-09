Software Packaging and File Archiving on Linux
🔍 Overview
In this lab, I practiced installing, removing, and managing software on Linux using the command line.
I worked with .deb packages, extracted .tar archives, created .tar archives, installed 7‑Zip, and removed software using apt.
These tasks reflect real Linux system administration responsibilities involving package management and file archiving.
🎯 Objectives
• 	Install Sublime Text using dpkg and fix dependencies
• 	Extract files from a .tar archive
• 	Archive multiple files into a .tar file
• 	Install 7‑Zip using apt
• 	Uninstall GIMP using apt
🛠️ Tools & Commands Used
Linux Tools
• 	Terminal
• 	dpkg
• 	apt
• 	tar
• 	p7zip-full
Commands
sudo dpkg -i /home/qwiklab/downloads/sublime-text_build-3211_amd64.deb
sudo apt install -f
dpkg -s sublime-text
cd /home/qwiklab/downloads
sudo tar -xvf extract_me.tar
cd ~
tar -cvf Planets.tar --absolute-names /home/qwiklab/documents/Earth /home/qwiklab/documents/Mercury /home/qwiklab/documents/Venus
sudo apt install p7zip-full
dpkg -s p7zip-full
sudo apt remove gimp
dpkg -s gimp
🧪 Steps I Completed
1️⃣ Installing Sublime Text
• 	I attempted to install Sublime Text using dpkg: 
sudo dpkg -i sublime-text_build-3211_amd64.deb
• 	I encountered dependency errors
• 	I fixed the dependencies using:
sudo apt install -f
• 	Required packages (libgtk‑3‑0, libgtk‑3‑bin) were installed
• 	I verified the installation using:
dpkg -s sublime-text
2️⃣ Extracting an Archive
- I navigated to the downloads directory
- I extracted the archive using:
sudo tar -xvf extract_me.tar
- I confirmed the extracted folder and file appeared
3️⃣ Archiving Files
- I navigated to my home directory
- I created a .tar archive containing Earth, Mercury, and Venus using:
tar -cvf Planets.tar --absolute-names /home/qwiklab/documents/Earth /home/qwiklab/documents/Mercury /home/qwiklab/documents/Venus
- I verified the archive was created successfull
4️⃣ Installing 7‑Zip
- I installed 7‑Zip using:
sudo apt install p7zip-full
- I verified the installation using:
dpkg -s p7zip-full
5️⃣ Uninstalling GIMP
- I removed GIMP using:
sudo apt remove gimp
- I verified removal using:
dpkg -s gimp
- Output confirmed GIMP was no longer installed
🧩 Problems I Faced & How I Solved Them
❌ Dependency errors when installing Sublime Text
Cause: Missing package libgtk-3-0
Fix: I ran sudo apt install -f to automatically install required dependencies
❌ Repeated dpkg attempts
Cause: I accidentally re‑ran the Sublime Text dpkg command
Fix: I ignored the duplicate attempt and continued with the correct tasks
📘 What I Learned
- How to install .deb packages using dpkg
- How to fix broken dependencies using apt
- How to extract .tar archives using tar
- How to create .tar archives
- How to install software using apt
- How to uninstall software using apt
- How Linux package management differs from Windows
📄 Related Files
- Planets.tar — archive created during the lab
- Extracted contents of extract_me.tar
- dpkg and apt command logs
🚀 Next Steps
- Practice using gzip and bzip2 compression
- Explore apt-cache search and apt show
- Learn how to build .deb packages
- Continue documenting Linux administration labs for my portfolio
