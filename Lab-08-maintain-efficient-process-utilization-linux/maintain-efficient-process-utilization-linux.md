**maintaining efficient process utilization on a Linux virtual machine**

**🟦 Overview**
This lab focused on maintaining efficient process utilization on a Linux virtual machine.
I practiced identifying running processes, terminating a specific process, and terminating multiple processes using Linux CLI tools.
These tasks simulate real IT Support responsibilities where runaway or suspicious processes must be safely identified and stopped.
**🎯 Objectives**
- Collect process information using Linux CLI tools
- Identify CPU‑heavy and memory‑heavy processes
- Terminate a specific process
- Terminate multiple processes
- Verify process termination and ensure system stability
**🛠️ Tools & Commands Used**
ps -aux
grep "<pattern>"
kill <PID>
kill -9 <PID>
pgrep -l <name>
top
htop
**📝 Steps Completed**
1. Identified the Target Process
ps -aux | grep "totally_not_malicious"
Returned:
root   319  0.0  0.8   7684  4712 ?  S  07:13  0:00 sudo nohup bash /home/totally_not_malicious
root   324  0.0  0.4   3816  2616 ?  S  07:13  0:00 bash /home/totally_not_malicious
student 9299 0.0 0.2   3240  1724 pts/0 S+ 08:28 0:00 grep totally_not_malicious
2. Terminated the Specific Process
Killed the parent process:
sudo kill 319
Attempted to kill the child:
sudo kill 324
Linux responded:
kill: (324): No such process
This is expected — killing PID 319 also terminated PID 324.
3. Verified Termination
ps -aux | grep "totally_not_malicious"
Output:
student 9486 0.0 0.3 3240 1816 pts/0 S+ 08:29 0:00 grep totally_not_malicious
Only the grep process remained → Process successfully terminated.
4. Identified Multiple “Razzle” Processes
ps -aux | grep "razzle"
Returned:
root   320 0.0 0.8 7684 4800 ? S 07:13 0:00 sudo nohup bash /home/razzle_dazzle
root   321 0.0 0.8 7684 4780 ? S 07:13 0:00 sudo nohup bash /home/my_cat_razzle
root   322 0.0 0.8 7684 4780 ? S 07:13 0:00 sudo nohup bash /home/razzles
root   323 0.0 0.4 3816 2704 ? S 07:13 0:00 bash /home/razzles
root   325 0.0 0.4 3816 2644 ? S 07:13 0:00 bash /home/razzle_dazzle
root   326 0.0 0.4 3816 2744 ? S 07:13 0:00 bash /home/my_cat_razzle
student 9621 0.0 0.3 3240 1752 pts/0 S+ 08:30 0:00 grep razzle
5. Terminated Multiple Processes
Killed processes one by one:
sudo kill 320
sudo kill 322
sudo kill 323
sudo kill 326
Linux responded:
kill: (323): No such process
Expected — killing PID 322 (parent) also terminated PID 323 (child).
6. Verified All “Razzle” Processes Were Gone
ps -aux | grep "razzle"
Output:
student 9748 0.0 0.3 3240 1816 pts/0 S+ 08:32 0:00 grep razzle
Only the grep process remained → All razzle processes successfully terminated.
**🧩 Problems & Fixes**
**Problem:**
Child processes sometimes disappeared before manual termination.
**Fix:**
Recognized that killing the parent (sudo nohup bash) automatically terminates its child (bash /home/...).
Verified using ps -aux after each kill.
**📚 What I Learned**
- How to identify processes using ps -aux and grep
- How parent/child process relationships affect termination
- How to safely terminate processes using kill and sudo kill
- How to verify process termination
- How Linux handles cascading process shutdowns
**📎 Related Files**
- Terminal screenshots
- Process output logs
**🚀 Next Steps**
- Add this lab to the Linux‑admin repo
- Continue Module 5 documentation
- Prepare for Module 6 labs

If you want, I can now generate a combined Windows + Linux summary for your daily log, or we can move straight into the next module.
