# LogHawk

What LogHawk does and why security teams need it:

LogHawk is a simple yet powerful tool designed to help security teams monitor system logs for suspicious activity. It leverages regular expressions to identify common security events like failed logins, critical system errors, and potentially malicious behavior — making it a great companion for early threat detection and response automation.

Installation steps:
Before using LogHawk, make sure you have Python 3 installed. You can install it by running:
sudo apt-get install python3

How to use it:
For a Python script: python3 loghawk.py /path/to/logfile.log
example of what the output should look like:

[ALERT] Suspicious Activity Detected!

[FAILED_LOGIN] Line 1: Apr 7 10:00:00 server sshd[1234]: Failed password for invalid user admin from 192.168.1.1 port 22 ssh2
[SSH_BRUTE_FORCE] Line 1: Apr 7 10:00:00 server sshd[1234]: Failed password for invalid user admin from 192.168.1.1 port 22 ssh2
[UNAUTHORIZED_ACCESS] Line 3: Apr 7 10:10:00 server app[1234]: unauthorized access attempt detected from 10.0.0.1



How to automate it with cron:
1. Make the script executable (if not already):

chmod +x loghawk.py

2. Add it to your crontab:
Open your crontab editor:

crontab -e
Add a line like this to run it every 15 minutes:


*/15 * * * * /usr/bin/env python3 /path/to/loghawk.py /var/log/syslog >> /home/youruser/loghawk_output.txt 2>&1
This will scan /var/log/syslog every 15 minutes and log output to loghawk_output.txt.


