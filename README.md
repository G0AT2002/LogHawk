# LogHawk

What LogHawk does and why security teams need it:
LogHawk is a tool designed to help security teams automatically monitor and analyze log files for suspicious activity like failed login attempts or unauthorized access.”

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
To have LogHawk run every 10 minutes, you’ll want to add this to your crontab: */10 * * * * /path/to/loghawk.sh
