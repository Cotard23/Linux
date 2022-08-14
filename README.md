# Linux
Linux Enumeration

$hostname
The hostname command will return the hostname of the target machine

$uname -a
Will print system information giving us additional detail about the kernel used by the system. This will be useful when searching for any potential kernel vulnerabilities that could lead to privilege escalation.

$cat /proc/version
The proc filesystem (procfs) provides information about the target system processes

$cat /etc/issue
Systems can also be identified by looking at the /etc/issue file. This file usually contains some information about the operating system but can easily be customized or changes. 

$ps
The ps command is an effective way to see the running processes on a Linux system

$env
The env command will show environmental variables

$sudo -l
The target system may be configured to allow users to run some (or all) commands with root privileges. The sudo -l command can be used to list all commands your user can run using sudo.

$id  // $id username
The id command will provide a general overview of the user’s privilege level and group memberships.

$cat /etc/passwd
Reading the /etc/passwd file can be an easy way to discover users on the system.

$history
Looking at earlier commands with the history command can give us some idea about the target system and, albeit rarely, have stored information such as passwords or usernames.

$ifconfig
The target system may be a pivoting point to another network. The ifconfig command will give us information about the network interfaces of the system.

$netstat
Following an initial check for existing interfaces and network routes, it is worth looking into existing communications. The netstat command can be used with several different options to gather information on existing connections.

    $netstat -pnta
    
    
find Command
Searching the target system for important information and potential privilege escalation vectors can be fruitful. The built-in “find” command is useful and worth keeping in your arsenal.

Below are some useful examples for the “find” command.

Find files:

find . -name flag1.txt: find the file named “flag1.txt” in the current directory
find /home -name flag1.txt: find the file names “flag1.txt” in the /home directory
find / -type d -name config: find the directory named config under “/”
find / -type f -perm 0777: find files with the 777 permissions (files readable, writable, and executable by all users)
find / -perm a=x: find executable files
find /home -user frank: find all files for user “frank” under “/home”
find / -mtime 10: find files that were modified in the last 10 days
find / -atime 10: find files that were accessed in the last 10 day
find / -cmin -60: find files changed within the last hour (60 minutes)
find / -amin -60: find files accesses within the last hour (60 minutes)
find / -size 50M: find files with a 50 MB size
This command can also be used with (+) and (-) signs to specify a file that is larger or smaller than the given size.
