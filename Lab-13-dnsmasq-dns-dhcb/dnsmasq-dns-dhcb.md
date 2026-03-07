⭐ 1. Overview
In this lab, I worked with a simulated dnsmasq environment to manage DNS and DHCP services for a small network. My main goal was to prepare the network for new servers by enabling detailed logging, reducing the dynamic DHCP range, and assigning fixed IP addresses to specific MAC addresses. I validated each configuration change using dnsmasq’s built‑in syntax checker, service restarts, DNS queries, DHCP lease renewals, and log inspection.

🎯 2. Objectives
Enable DNS and DHCP debug logging in dnsmasq
Reduce the dynamic DHCP range to free space for static server IPs
Assign fixed IP addresses to new servers using MAC → IP mappings
Verify DNS resolution, DHCP behavior, and logging output
Ensure dnsmasq configuration passes syntax checks and service restarts cleanly

🛠️ 3. Tools & Commands Used
Linux Tools
ip a — inspect network interfaces
nano — edit configuration files
systemctl — manage dnsmasq service
tail, grep — inspect logs
dnsmasq Commands
sudo dnsmasq --test -C /etc/dnsmasq.d/mycompany.conf
sudo systemctl restart dnsmasq
sudo service dnsmasq start
DNS Tools
dig example.com @localhost
dig example.local @localhost
DHCP Tools
sudo dhclient -i eth_cli -v -sf /root/debug_dhcp.sh
cat /var/lib/misc/dnsmasq.leases
Config Files Edited
/etc/dnsmasq.d/mycompany.conf

🧩 4. Steps Completed
Step 1 — Verified Network Interface
I inspected the simulated network interface eth_srv:
ip address show eth_srv

It showed:
IP: 192.168.1.1/24
Interface UP
MAC address available for DHCP testing
Step 2 — Enabled Debug Logging
At the bottom of /etc/dnsmasq.d/mycompany.conf, I added:
log-queries
log-facility=/var/log/dnsmasq.log

I confirmed logging by running DNS queries and checking:
sudo tail /var/log/dnsmasq.log

Step 3 — Reduced Dynamic DHCP Range
I modified the DHCP range from:
dhcp-range=192.168.1.2,192.168.1.254,24h

to:
dhcp-range=192.168.1.20,192.168.1.254,6h

This freed .2–.19 for static server assignments.
Step 4 — Assigned Static IPs to New Servers
I added three static DHCP leases:
dhcp-host=aa:bb:cc:dd:ee:b2,192.168.1.2
dhcp-host=aa:bb:cc:dd:ee:c3,192.168.1.3
dhcp-host=aa:bb:cc:dd:ee:d4,192.168.1.4

Step 5 — Validated Configuration
I ran:
sudo dnsmasq --test -C /etc/dnsmasq.d/mycompany.conf

Result:
dnsmasq: syntax check OK.

Step 6 — Restarted dnsmasq
I restarted the service:
sudo systemctl restart dnsmasq

Service started cleanly.
Step 7 — Verified DNS & DHCP Behavior
DNS queries (dig example.com) resolved correctly
Cached responses appeared in logs
DHCP client (dhclient) successfully requested leases
Log entries confirmed DHCPDISCOVER and DHCPOFFER events
Step 8 — Confirmed Lab Success
The platform validated:
Success: New servers have fixed addresses.

🐞 5. Problems & Fixes
Issue: None encountered
All syntax checks passed on first attempt, and dnsmasq restarted without errors.
 DNS and DHCP logs behaved exactly as expected.

📚 6. What I Learned
How dnsmasq handles DNS forwarding and caching
How to enable detailed DNS and DHCP logging
How to shrink a DHCP pool to reserve space for static servers
How to assign static DHCP leases using MAC → IP mappings
How to validate dnsmasq configuration safely using --test
How to inspect DHCP leases and debug DHCP client behavior
The importance of testing changes in a non‑production environment

📎 7. Related Files
/etc/dnsmasq.d/mycompany.conf — main configuration edited
/var/log/dnsmasq.log — DNS & DHCP debug logs
/var/lib/misc/dnsmasq.leases — active DHCP leases
Commands and outputs from this session
This documentation belongs in your Networking repo, filename suggestion:
dnsmasq-dns-dhcp-lab.md

🔜 8. Next Steps
Practice configuring DHCP reservations with hostnames
Explore DNS overrides using address=/domain/IP
Set up DHCPv6 and compare with IPv4 behavior
Build a multi‑subnet dnsmasq configuration for advanced networking
Continue strengthening troubleshooting skills with real‑world scenarios

