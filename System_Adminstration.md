## Monitor Users
### who
- who (this command will show number of users currently logged-in with their terminal id and many more)
### last
- last (this will tell every user list logged in from last time)
### w
- w (this is same as "who" but it'll provide additional informations like current processes)
### finger
- finger or pinky  (same as who) 
### id
- id (this will show all information about userid and groupid and contexts)
- id username 
## Talking to Users
### users
- users (this will show current users)
### wall
- wall (this will broadcast your message to all users, after the command a space for message will apear)
### write
- write username  (this will enable sending message to a specific user)
## System Utility
In linux regular usage a user need to use some regular commands which are
### date
- date (It'll show detail current time with date and week we can modify using it's flags)
### uptime
- uptime  (shows howmany time system up for with average loads)
### hostname
- hostname  (it'll show host name of current system and other modification)
### uname
- uname -a  (it'll show which linux kernel you're using)
### cal
- cal  (it'll show the callender of the current month)
- cal [month number] [year]   (show the specified month)
- cal [year]
### which
- which [command name]  (It'll show the location of the executable of that specific command)
### bc
- bc  (binary calculator)

## System Monitoring
### top
- top (this will show linux processes)
### df
- df (this will show filesystem and It's disk usage)
- df -h (this will show in human readable format)
### dmesg
- dmesg (This will show all information including error everyting right from the bios every hardware configuration everything will show)
### iostat 1
- iostat  (this will show all i/o speed and everything)
- iostat [number]  (it will refresh by number of second)
we can install it by yum install sysstat -y
### netstat
- netstat  (it prints network connections,routing tables and other network informations)
- netstat -rnv  (this will show used network interface and getway and routing table in brief)
### free
- free  (this will show amount of used and free memory[RAM] in the system)
### cat /proc/cpuinfo
- this command will show whole detail about cpu's current state with core count etc.
### cat /proc/meminfo
- this will show all memory information with current utilization

## System Logs Monitoring
Another and most important way to system adminstration is log monitor
Log Directory: /var/log
- boot (it's the log system generates when it's booting.)
- chronyd = NTP ()
- cron
- maillog
- secure
- messages
- httpd (Web Application Logs)

## Process Management
### systemctl  (System Controll)
- systemctl start/stop/status [service name]  (to stop,start,chek status of a service)
- systemctl enable/disable [service name]  (to enable i.e. start service when system boot)
- systemctl restart/reload [service name]  (restart service)
- systemctl list-units --all  (list all services)
To add a service under systemctl management we can create a file in
        "/etc/systemd/system/servicename.service"
We can also control our entire system state using systemctl command
- systemctl poweroff
- systemctl halt
- systemctl reboot
### ps (Process Status)
- ps  (shows processes of current shell)
- ps -e  (shows all current running processes)
- ps aux  (all current running processes in detail)
- ps -ef  (just like aux)
- ps -u username  (to see all processes by  that username)
### top 
this command is used to show the linux processes and it provides a real-time view of the running system.
- top (this will show the list of processes currently managed by kernel)
- top -u username   (processes owned by user)
- top then press c  (to show absolute path of commands)
- top then press k  (to kill a process)
- top then M    (to sort processes according to memory usage)
NOTE: top command refreshes every information every 3 seconds
### kill
this command is used to kill a process manually.
- kill [pid]  (kill the process default)
- kill -l  (this will show all signals which can be used with kill command)
Some most used kill signals are
- kill -1 pid   (restart)
- kill -2 pid   (interupt the process just like ctrl+c)
- kill -9 pid   (kill the process forcefully)
- kill -15 pid   (kill the process gracefully)
- killall pid  (this will kill all child processes along with it)
- pkill processname  (when we don't have process id)
## Process Management Additionals
Some processes don't return prompt after executing i.e "sleep 10" to manage these type of processes we can use these commands
- Background: ctrl+z, jobs, then bg    OR  [command] &
- Foreground: fg
- Run Process even after exit Terminal:  nohup [command] &   (this will make sure the process runs even after we exit the terminal)
- Process Priority: nice -n [number between -20 to 19] [command]  (this will set priority to the process the lower the number the better)
- process monitoring: top
- List process: ps
- Kill process: kill
## Crontab
this command is used to scedule tasks.
- crontab -e   (edit the crontab)
- crontab -l   (list crontab entries)
- crontab -r   (remove the crontab)
- crond   (this is the service name of crontab i.e. systemctl status crond)
### NOTE: * * * * * <command to execute> --- the format is minute(0-59) hour(0-23) day_of_the_month(1-31) month(1-12) day_of_the_week(0-6) [sunday to saturday i.e. 7 is sunday on some systems]
example:
- 37 18 * 3 * echo "This is my first Crontab" > first-cron   (this command will execute the echo command everyday in march at 6:37pm and save the output to a file named first-cron)
- 40 18 11 3 1 echo "This is another" >> first-cron    (this will run at 6:40pm of 11th March Monday)
## at 
this command is just like crontab but It'll shedule the job for only once.
- at HH:MM PM/AM   (this will shedule a job NOTE: enter ctrl+d to register the job)
- atq   (list all jobs in "at" entry table)
- atrm [number]   (remove a entry of "at")
- atd   (this is the service name   i.e. systemctl status atd)
## Additional CronJobs
By default there're 4 types of cronjobs
- Hourly
- Daily
- Weekly
- Monthly
All the above Cronjobs can be achived by setting up in directory
- /etc/cron.daily/ , /etc/cron.hourly/ , /etc/cron.weekly/ , /etc/cron.monthly/
The timing for each job is set in "/etc/anacrontab" file except hourly.
For hourly cronjob "/etc/cron.d/0hourly" file.
