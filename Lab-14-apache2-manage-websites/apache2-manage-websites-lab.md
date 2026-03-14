📄 APACHE2 LAB: “Manage Websites With Apache2”

1. ⭐ Overview
In this lab, I installed Apache2, enabled a custom company website, and configured Server‑Side Includes (SSI). This lab simulated real sysadmin tasks: deploying a website, managing virtual hosts, enabling modules, and verifying service behavior.

2. 🎯 Objectives
Install Apache2
Enable the company website
Enable Server‑Side Includes (SSI)
Replace the default site with a custom site
Verify Apache2 functionality

3. 🛠️ Tools & Commands Used
Apache2 Commands
sudo apt install apache2
sudo service apache2 start
sudo service apache2 reload
sudo service apache2 status
sudo a2ensite 001-ourcompany.conf
sudo a2dissite 000-default.conf
sudo a2enmod include
File & Directory Commands
ls -l, cat, nano, cp, mkdir, chown

4. 🧩 Steps Completed
A. Install Apache2
Updated package lists
Installed Apache2 and dependencies
Started Apache2 manually due to lab restrictions
Verified service status
B. Enable Company Site
Copied site files from /opt/devel/ourcompany
Created /var/www/ourcompany
Created 001-ourcompany.conf virtual host
Enabled the site and disabled the default
Reloaded Apache2
Verified site loads correctly
C. Enable Server‑Side Includes (SSI)
Enabled include module
Added SSI configuration to <Directory> block
Reloaded Apache2
Verified SSI using <!--#include file="footer.html" -->

5. 🐞 Problems & Fixes
Problem
Fix
Apache2 did not auto-start
Started manually with sudo service apache2 start
FQDN warning
Identified as non-critical; optional fix available
SSI not active by default
Enabled module + added Options +Includes


6. 📚 What I Learned
How to deploy a custom website on Apache2
How to manage virtual hosts in Debian
How to enable and test SSI
How to troubleshoot Apache2 startup issues
How to replace the default site with a custom one

7. 📎 Related Files
/etc/apache2/sites-available/001-ourcompany.conf
/var/www/ourcompany/index.html
/var/www/ourcompany/footer.html

8. 🔜 Next Steps
Practice enabling SSL
Configure Apache2 logging
Explore reverse proxy features
Deploy multiple virtual hosts
Integrate Apache2 with PHP or Python apps

