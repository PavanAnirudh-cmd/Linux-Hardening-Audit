Linux Hardening Audit Tool
A simple Bash-based tool to audit a Linux system’s security configuration. It performs checks based on basic CIS benchmarks and provides a compliance score and recommendations.

Objective
To develop a Bash-based tool that audits Linux systems for security compliance and provides a hardening report with recommendations.

Tools & Technologies Used
Tool        Purpose
Bash        Scripting language used for audit automation      
Linux OS    Platform for execution (Ubuntu/Kali/Debian)       
chkrootkit  To check for rootkits                             
ufw         To check firewall status                          
netstat     To detect unwanted running services               
find, stat  To check file and directory permissions           
grep, awk   To parse configuration files                      

Script Overview
The script audits the following:
- Firewall status (ufw)
- SSH configuration:
- PermitRootLogin
- PasswordAuthentication
- Permissions on /etc/password and/etc/shadow
- Unwanted services (telnet, ftp, pop)
- Rootkit detection (via 'chkrootkit')
- Kernel version
- World-writable directories
- Displays compliance score and recommendations

How to Use bash
# Make script executable
chmod +x linux_audit.sh

# Run script with sudo
sudo ./linux_audit.sh

Sample Output
Total Checks : 8
Passed Checks: 4
Compliance Score: 50%

Recommendations:
- Enable firewall using: sudo ufw enable
- Set PermitRootLogin to no in /etc/ssh/sshd_config
- Disable PasswordAuthentication in /etc/ssh/sshd_config
- Set correct permissions: chmod 644 /etc/passwd and chmod 600 /etc/shadow
- Install chkrootkit for rootkit scanning

Screenshots:
- Folder creation
- Script editing and saving
- Permission setting (chmod)
- Audit run output
- chkrootkit installation
- Final audit report output

Conclusion:
The Linux Hardening Audit Tool simplifies the process of checking for common security misconfigurations in Linux systems. It provides an actionable, beginner-friendly report for improving Linux hardening based on best practices.
