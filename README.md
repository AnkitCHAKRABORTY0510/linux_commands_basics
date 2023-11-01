
Linux commands cheat sheet & examples

In this cheat sheet tutorial I have consolidated a list of Linux commands with examples and man page link to give you an overview on Linux day to day usage. We know Linux is one of the preferred choice for most of the IT domains so having basic knowledge of Linux is mandatory for everyone. I have divided the Linux commands into different section so you can choose to only concentrate on the commands which suits your domain.

I will keep adding and updating this article from time to time to add more commands.

Environment Variables

Variables are local, which means they are specific to a process. Local means local to a process. For example, when you log in on a terminal or open a terminal emulator, you start a process that runs a shell and create this variable TEST with value as  Ankit


#TEST=Ankit

Verify the content of this variable

#echo $TEST Ankit

Now you open another terminal of the same Linux server and try to access this variable,

#echo $TEST

The output would be empty, so our variable is only accessible in the terminal where we created.

|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
|printenv|<p>- printenv</p><p>- printenv PATH</p>|<p>Displays environment variable names and values.</p><p>When called with the name of an environment variable, it displays the value of that variable.</p>|man page for printenv|
|env|# env|The env utility runs a program as a child of the current shell, allowing you to modify the environment the current shell exports to the newly created process.|man page for env|
|export|<p>- export</p><p>TEST=Ankit</p><p>- env | grep TEST</p><p>TEST=Ankit</p>|When you run an export command with variable names as arguments, the shell places the names (and values, if present) of those variables in the environment.|man page for export|
|set|<p>- TEST=Ankit</p><p>- set | grep TEST TEST=Ankit</p>|Display variables in the current shell These variables comprise shell variables (variables not in the environment) and environment variables.|man page for set|

File Management

The commands under this section are very basic commands and must be known to every system administrator. This is definitely not the complete list of Linux commands for file management but can give you a kickstart and can cover most of the basic to complex scenarios.

Recommended Read:![](Aspose.Words.783a1b43-fb78-493d-849c-0d9a178e50bc.004.png)

Linux copy directory and contents from remote to local & vice versa 5 commands to copy file from one server to another in Linux or Unix How to transfer files over SSH with SSHFS in Linux & Windows Securely transfer files between two hosts using HTTPS in Linux

10+ practical examples to create symbolic link in Linux



<table><tr><th colspan="1">Command</th><th colspan="1">Example/Syntax</th><th colspan="1">Comments</th><th colspan="1">For more details</th></tr>
<tr><td colspan="1" rowspan="4">ls</td><td colspan="1"># ls</td><td colspan="1">List files</td><td colspan="1" rowspan="4">man page for ls</td></tr>
<tr><td colspan="1"># ls -l</td><td colspan="1">Long list files</td></tr>
<tr><td colspan="1"># ls -la</td><td colspan="1">Long list files including hidden files</td></tr>
<tr><td colspan="1"># ls -ltr</td><td colspan="1">Long list files and sort by modification time. oldest placed first.</td></tr>
<tr><td colspan="1">cat</td><td colspan="1"># cat FILENAME</td><td colspan="1">Print the content of the provided file on the terminal</td><td colspan="1">man page for cat</td></tr>
<tr><td colspan="1">less</td><td colspan="1"># less FILENAME</td><td colspan="1"><p>When you want to view a file that is longer than one screen, you can use either the less utility or the more utility.</p><p>It will pause after displaying a screen of text You can use keyboard arrow to navigate around the file to read the text</p><p>Press q to return to the shell</p></td><td colspan="1">man page for less</td></tr>
<tr><td colspan="1">more</td><td colspan="1"># more FILENAME</td><td colspan="1"><p>more command is also similar to less but has few restrictions</p><p>We cannot use navigation arrow from the keyboard while reading with more</p><p>You must use SPACE bar to scroll through the file</p><p>Press q to return to console</p></td><td colspan="1">man page for more</td></tr>
<tr><td colspan="1">head</td><td colspan="1"># head -n 5 FILENAME</td><td colspan="1"><p>This example displays the top 5 lines of provided file</p><p>By default the head utility displays the first ten lines of a file.</p></td><td colspan="1">man page for head</td></tr>
<tr><td colspan="1" valign="top">tail</td><td colspan="1" valign="top"># tail -n 5 FILENAME</td><td colspan="1" valign="top">This example will display the last 5 lines of the provided file</td><td colspan="1" valign="top">man page for tail</td></tr>
</table>

<table><tr><th colspan="1" valign="top">Command</th><th colspan="1"></th><th colspan="1"></th><th colspan="1">For more details</th></tr>
<tr><td colspan="1" rowspan="2"></td><td colspan="1"></td><td colspan="1"></td><td colspan="1" rowspan="2"></td></tr>
<tr><td colspan="1"></td><td colspan="1"></td></tr>
<tr><td colspan="1" valign="top">sort</td><td colspan="1"></td><td colspan="1"></td><td colspan="1">man page for sort</td></tr>
<tr><td colspan="1" valign="top">uniq</td><td colspan="1"></td><td colspan="1"></td><td colspan="1" valign="top">man page for uniq</td></tr>
<tr><td colspan="1" rowspan="2">file</td><td colspan="1"></td><td colspan="1"></td><td colspan="1" rowspan="2">man page for file</td></tr>
<tr><td colspan="1"></td><td colspan="1"></td></tr>
<tr><td colspan="1" valign="top">cp</td><td colspan="1"></td><td colspan="1"></td><td colspan="1" valign="top">man page for cp</td></tr>
</table>

|Example/Syntax|Comments|
| - | - |
||By default tail will show the last 10 lines of the file|
|<p># tail -f</p><p>/var/log/messages</p>|To continuously monitor the incoming log messages into /var/log/messages file in runtime|
|# sort FILENAME|<p>Displays a File in Order</p><p>The sort utility displays the contents of a file in order by lines</p><p>It does not change the original file.</p><p>The –u option generates a sorted list in which each line is unique (no duplicates). The –n option puts a list of numbers in</p><p>numerical order.</p>|
|# uniq FILENAME|<p>The uniq (unique) utility displays a file, skipping adjacent duplicate lines; it does not change the original file.</p><p>If a file contains a list of names and has two successive entries for the same person, uniq skips the extra line</p>|
|# file FILENAME|<p>Identifies the Contents of a File</p><p>You can use the file utility to learn about the contents of any file on a Linux system without having to open and examine the file yourself.</p>|
|# file dataFile.txt dataFile.txt: ASCII text|file command identified the dataFile.txt type as ASCII text|
|# cp SOURCE-FILE DESTINATION-FILE|<p>The cp (copy) utility makes a copy of a file. The SOURCE-FILE is the name of the file that cp will copy.</p><p>The DESTINATION-FILE is the name cp assigns to the resulting (new) copy of the</p><p>file.</p><p>If the DESTINATION-FILE exists before you give a cp command, cp overwrites it.</p>|

<table><tr><th colspan="1">Command</th><th colspan="1">Example/Syntax</th><th colspan="1">Comments</th><th colspan="1">For more details</th></tr>
<tr><td colspan="1"></td><td colspan="1" valign="top"># cp /root/myfile /tmp/dir1/</td><td colspan="1"><p>This command copied myfile from /root</p><p>to /tmp/dir1 directory</p></td><td colspan="1"></td></tr>
<tr><td colspan="1" rowspan="2">mv</td><td colspan="1"># mv EXISTING- FILENAME NEW- FILENAME</td><td colspan="1"><p>Changes the Name of a File</p><p>The mv (move) utility can rename a file without making a copy of it. The mv</p><p>command line specifies an existing file and a new filename using the same syntax as cp</p></td><td colspan="1" rowspan="2">man page for mv</td></tr>
<tr><td colspan="1"><p># mv</p><p>/root/debug.log /tmp/new_debug.log</p></td><td colspan="1"><p>In this example we rename the name of debug.log file to new_debug.log and also changed the location of the file from</p><p>/root/ to /tmp</p></td></tr>
<tr><td colspan="1" rowspan="2">grep</td><td colspan="1" valign="top"># grep STRING FILENAME</td><td colspan="1"><p>The grep utility searches through one or more files to see whether any contain a specified string of characters.</p><p>This utility does not change the file it searches but simply displays each line that contains the string.</p></td><td colspan="1" rowspan="2">man page for grep</td></tr>
<tr><td colspan="1"><p># grep ssh</p><p>/etc/services</p></td><td colspan="1">In this example we search for all the lines containing "ssh" in /etc/services file</td></tr>
<tr><td colspan="1">mkdir</td><td colspan="1"># mkdir DIR</td><td colspan="1">Create directories</td><td colspan="1">man page for mkdir</td></tr>
<tr><td colspan="1" valign="top">touch</td><td colspan="1"># touch FILE</td><td colspan="1" valign="top">Create empty file</td><td colspan="1">man page for touch</td></tr>
<tr><td colspan="1" valign="top">pwd</td><td colspan="1"># pwd</td><td colspan="1" valign="top">present working directory</td><td colspan="1" valign="top">man page for pwd</td></tr>
</table>

Finding files and directories

Most of the time we will end up using find command to find files and directories. But I also like which command as it gives is the path of the binary which is required at multiple events when we are required to execute a binary with complete PATH.





<table><tr><th colspan="1">Command</th><th colspan="1">Example/Syntax</th><th colspan="1">Comments</th><th colspan="1">For more details</th></tr>
<tr><td colspan="1" rowspan="2">which</td><td colspan="1"># which PROGRAMNAME</td><td colspan="1"><p>which will print the full path of the provided PROGRAMNAMEon STDOUT</p><p>It does this by searching for an executable or script in the directories listed in the environment variable PATH.</p></td><td colspan="1" rowspan="2">man page for which</td></tr>
<tr><td colspan="1"><p># which useradd</p><p>/usr/sbin/useradd</p></td><td colspan="1">In this example we are searching for the path of useradd command</td></tr>
<tr><td colspan="1" rowspan="2">whereis</td><td colspan="1"># whereis FILENAME</td><td colspan="1">whereis attempts to locate the desired program in the standard Linux places, and in the places specified by $PATH and $MANPATH</td><td colspan="1" rowspan="2">man page for whereis</td></tr>
<tr><td colspan="1"><p># whereis sshd</p><p>sshd: /usr/sbin/sshd /usr/share/man/man8/</p><p>sshd.8.gz</p></td><td colspan="1">In this example we are searching for the path of sshd binary and the man page location for sshd file</td></tr>
<tr><td colspan="1" rowspan="2">locate</td><td colspan="1"># locate FILENAME</td><td colspan="1">The locate utility ( locate package; some distributions use mlocate ) searches for files on the local system: Before you can use locate ( mlocate ), the updatedb utility must build or update the locate ( mlocate ) database. Typically the database is updated once a day by a cron script</td><td colspan="1" rowspan="2">man page for locate</td></tr>
<tr><td colspan="1"><p># locate sshd</p><p>/etc/pam.d/sshd /etc/ssh/sshd_config /etc/sysconfig/sshd</p></td><td colspan="1">In this example we are searching for all files in your Linux server containing string sshd in their name</td></tr>
<tr><td colspan="1" rowspan="2" valign="top">find</td><td colspan="1"># find PATH OPTIONS FILENAME</td><td colspan="1">find command will search for file or directory based on the OPTIONS provided</td><td colspan="1" rowspan="2">find cmnd examples</td></tr>
<tr><td colspan="1"># find / -type f - name sshd</td><td colspan="1">In this example we are searching for a file named sshd inside / location</td></tr>
</table>

These are some of the commands which we use to check the last logged in user information and some other commands to get more details on existing user.



|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
|who|# who -u|The who utility displays a list of users who are logged in on the local system.|man page for who|
|users|# users|<p>Print the user names of users currently logged in to the current host</p><p>It does not give much information apart from usernames</p>|man page for users|
|last|# last -a|<p>This command searches back through the file /var/log/wtmp (or the file designated by the -f</p><p>flag) and displays a list of all users logged in (and out) since that file was created.</p>|man page for last|
|finger|# finger|If no arguments are specified, finger will print an entry for each user currently logged into the system.|man page for finger|
|whoami|# whoami|Print the user name associated with the current effective user ID|man page of whoami|
|id|# id|Print real and effective user and group IDs|man page for id|
|w|# w|The first line the w utility displays is the same as the output of uptime command. Following that line, w displays a list of the users who are logged in.||
Check System Information

As a sytem and Linux administrator you must be familiar with these commands. These will help you determine the type of server you are working on, such as load, cpu model, hardware model, hardware type etc. Some of the commands may be distribution specific such as  hwinfo is only available in SuSE Linux while others are expected to be found on almost all distros.


|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
|uptime|# uptime|<p>The uptime utility displays a single line that includes the time of day, the period of</p><p>time the computer has been running (in days, hours, and minutes), the number of users logged in, and the load average (how busy the system is). The three load average numbers represent the number of jobs</p><p>waiting to run, averaged over the past 1, 5, and 15 minutes.</p>|man page for uptime|
|free|# free -m|The free utility displays the amount of physical (RAM) and swap memory in the local system. It displays columns for total, used, and free memory as well as for kernel buffers.|Linux Memory Management|
|dmidecode|# dmidecode -t system|<p>dmidecode is a tool for dumping a computer's DMI (some say SMBIOS) table contents in a human-readable format. This table contains a description of the system's hardware components, as well as other</p><p>useful pieces of information such as serial numbers and BIOS revision</p>|man page for dmidecode|
|lshw|# lshw|lshw is a small tool to extract detailed information on the hardware configuration of the machine. It can report exact memory configuration, firmware version, mainboard configuration, CPU version and speed, cache configuration, bus speed, etc|man page for lshw|
|Command|Example/Syntax|Comments|For more details|
|hwinfo|# hwinfo|hwinfo is used to probe for the hardware present in the system. It can be used to generate a system overview log which can be later used for support. (available only with SuSE)|man page for hwinfo|
|lscpu|# lscpu|<p>lscpu gathers CPU architecture information from sysfs, /proc/cpuinfo</p><p>and any applicable architecture-specific libraries (e.g. librtas on Powerpc).</p>|man page for lscpu|
|lspci|# lspci|lspci is a utility for displaying information about PCI buses in the system and devices connected to them.|man page for lspci|
|/proc/cpuinfo|<p># cat</p><p>/proc/cpuinfo</p>|Provides information about the CPU model, architecture, processors, available modules, and many more CPU related information. lscpu gathers information from this file,|man page for lscpu|
|uname|<p># uname</p><p>[OPTIONS]</p>|Print system information|man page for uname|

Manage System Processes

These Linux commands will help you manage the Linux processes, and will help you troubleshoot any server resource related issues. You can use these commands to monitor your server's resource such as Memory, CPU, disk IO etc.


|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
|ps|# ps [OPTIONS]|ps displays information about a selection of the active processes. If you want a repetitive|man page for ps|

<table><tr><th colspan="1" rowspan="10"></th><th colspan="1" valign="top">Command</th><th colspan="1" valign="top">Example/Syntax</th><th colspan="1" valign="top">Comments</th><th colspan="1">For more details</th><th colspan="1" rowspan="10"></th></tr>
<tr><td colspan="1"></td><td colspan="1"></td><td colspan="1" valign="top">update of the selection and the displayed information, use top instead.</td><td colspan="1"></td></tr>
<tr><td colspan="1">nice</td><td colspan="1"># nice [OPTIONS]</td><td colspan="1">Run COMMAND with an adjusted niceness, which affects process scheduling. With no COMMAND, print the current niceness. Niceness values range from -20 (most favorable to the process) to 19 (least favorable to the process).</td><td colspan="1">nice example</td></tr>
<tr><td colspan="1" rowspan="2">renice</td><td colspan="1"><p># renice</p><p>[OPTIONS] PID</p></td><td colspan="1"><p>renice alters the scheduling priority of one or more running processes. The first argument is</p><p>the priority value to be used. The other arguments are interpreted as process IDs (by</p><p>default), process group IDs, user IDs, or user names.</p></td><td colspan="1" rowspan="2">renice example</td></tr>
<tr><td colspan="1"><p># renice -n 15 1121</p><p>1121 (process ID)</p><p>old priority 0, new priority 15</p></td><td colspan="1">In this example I have changed the nice value of PID 1121 from 0 to 15</td></tr>
<tr><td colspan="1">top</td><td colspan="1"># top</td><td colspan="1">The top program provides a dynamic real- time view of a running system. It can display system summary information as well as a list of processes or threads currently being managed by the Linux kernel.</td><td colspan="1">top examples</td></tr>
<tr><td colspan="1">pgrep</td><td colspan="1"># pgrep [OPTIONS] PATTERN</td><td colspan="1"><p>pgrep looks through the currently running processes and lists the process IDs which</p><p>match the selection criteria to stdout.</p></td><td colspan="1">man page for pgrep</td></tr>
<tr><td colspan="1">pkill</td><td colspan="1"># pkill [OPTIONS] PATTERN</td><td colspan="1">pkill will send the specified signal (by default SIGTERM) to each process instead of listing them on stdout.</td><td colspan="1">man page for pkill</td></tr>
<tr><td colspan="1" valign="top">kill</td><td colspan="1"># kill [OPTIONS] PID</td><td colspan="1">The command kill sends the specified signal to the specified processes or process groups.</td><td colspan="1" valign="top">man page for kill</td></tr>
<tr><td colspan="1" valign="top">sar</td><td colspan="1" valign="top"># sar [OPTIONS]</td><td colspan="1" valign="top">The sar command writes to standard output the contents of selected cumulative activity counters in the operating system. The accounting system, based on the values in the</td><td colspan="1" valign="top">sar examples</td></tr>
</table>

|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
|||count and interval parameters, writes information the specified number of times spaced at the specified intervals in seconds. If the interval parameter is set to zero, the sar command displays the average statistics for the time since the system was started.||
|vmstat|<p># vmstat</p><p>[OPTIONS]</p>|vmstat reports information about processes, memory, paging, block IO, traps, disks and cpu activity.|man page for vmstat|
|iostat|<p># iostat</p><p>[OPTIONS]</p>|The iostat command is used for monitoring system input/output device loading by observing the time the devices are active in relation to their average transfer rates.|man page for iostat|
|crond|# crond [OPTIONS]|crond daemon is used to execute scheduled commands. You can create new job using crontab -e and provide the time when the script should be executed and the script path|crond examples|

Managing Users and Groups

These are some of the basic Linux commands to perform user management such as create, modify, delete user or groups.

|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
|useradd|# useradd USERNAME|The useradd command creates a new user account using the values specified on the command line plus the default values from the system. Depending on command line|useradd examples|

<table><tr><th colspan="1" rowspan="12"></th><th colspan="1">Command</th><th colspan="1">Example/Syntax</th><th colspan="1">Comments</th><th colspan="1">For more details</th><th colspan="1" rowspan="11"></th></tr>
<tr><td colspan="1"></td><td colspan="1"></td><td colspan="1" valign="top"><p>options, the useradd command will update system files and may also create the new</p><p>user's home directory and copy initial files.</p></td><td colspan="1"></td></tr>
<tr><td colspan="1" rowspan="2">usermod</td><td colspan="1"><p># usermod</p><p>OPTIONS USERNAME</p></td><td colspan="1">The usermod command modifies the system account files to reflect the changes that are specified on the command line.</td><td colspan="1" rowspan="2">man page of usermod</td></tr>
<tr><td colspan="1" valign="top"># usermod -G admin Ankit</td><td colspan="1">In this example I am adding additional group to my existing Ankit user</td></tr>
<tr><td colspan="1" valign="top">userdel</td><td colspan="1"># userdel USERNAME</td><td colspan="1">The userdel command modifies the system account files, deleting all entries that refer to the user name USERNAME. The named user must exist</td><td colspan="1">man page for userdel</td></tr>
<tr><td colspan="1" valign="top">passwd</td><td colspan="1"># passwd USERNAME</td><td colspan="1"><p>The passwd utility is used to update user's authentication token(s).</p><p>You can lock, unlock, assign passwords using passwd utility for any system user</p></td><td colspan="1" valign="top">passwd examples</td></tr>
<tr><td colspan="1">groupadd</td><td colspan="1"># groupadd GROUPNAME</td><td colspan="1">The groupadd command creates a new group account using the values specified on the command line plus the default values from the system. The new group will be entered into the system files as needed</td><td colspan="1" valign="top">add or remove user from group</td></tr>
<tr><td colspan="1" valign="top">groupdel</td><td colspan="1" valign="top"># groupdel GROUPNAME</td><td colspan="1">The groupdel command modifies the system account files, deleting all entries that refer to GROUPNAME. The named group must exist.</td><td colspan="1">add or remove user from group</td></tr>
<tr><td colspan="1" rowspan="2">groupmod</td><td colspan="1"># groupmod [options] GROUPNAME</td><td colspan="1">The groupmod command modifies the definition of the specified GROUPby modifying the appropriate entry in the group database.</td><td colspan="1" rowspan="2">add or remove user from group</td></tr>
<tr><td colspan="1" valign="top"># groupmod -n administrator admin</td><td colspan="1">In this example I am renaming the group name from admin to administrator</td></tr>
<tr><td colspan="1" rowspan="2" valign="top">sudo</td><td colspan="1"><p>$ sudo OPTIONS</p><p>COMMAND</p></td><td colspan="1">sudo allows a permitted user to execute a command as the superuser or another user, as specified by the security policy.</td><td colspan="1" rowspan="2" valign="top">Add sudo permisison</td></tr>
<tr><td colspan="2"></td></tr>
</table>

|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
||$ sudo systemctl network restart|<p>Observe the $ sign in the beginning of the shell, it donates a normal user shell. A root user's shell will have hash ( # )</p><p>So in this example a normal user is performing network restart using sudo</p><p>privilege</p>||
Managing Permissions

Linux permission is a very vast topic and here I have only covered the basic commands which we use to assign/modify/remove permissions to files and directories.





<table><tr><th colspan="1" valign="top">Command</th><th colspan="1" valign="top">Example/Syntax</th><th colspan="1" valign="top">Comments</th><th colspan="1">For more details</th></tr>
<tr><td colspan="1" rowspan="2">chown</td><td colspan="1" valign="top"># chown OPTIONS USER:GROUP TARGET</td><td colspan="1">chown changes the user and/or group ownership of each given file or directory USER represents the user owner of the target file GROUPrepresents the group owner of the target file TARGET represents any file or directory or PATH</td><td colspan="1" rowspan="2">man page for chown</td></tr>
<tr><td colspan="1"># chown Ankit:admin /tmp/file</td><td colspan="1">In this example I am assigning user owner permission to Ankit , group owner permission to admin group for /tmp/file</td></tr>
</table>

<table><tr><th colspan="1" rowspan="9"></th><th colspan="1" valign="top">Command</th><th colspan="1" valign="top">Example/Syntax</th><th colspan="1" valign="top">Comments</th><th colspan="1">For more details</th><th colspan="1" rowspan="9"></th></tr>
<tr><td colspan="1" rowspan="2">chmod</td><td colspan="1"># chmod PERM PATH</td><td colspan="1">chmod changes the file mode bits i.e. PERM of each given file according to mode, which can be either a symbolic representation of changes to make, or an octal number representing the bit pattern for the new mode bits</td><td colspan="1" rowspan="2">man page for chmod</td></tr>
<tr><td colspan="1"># chmod 755 /tmp/dir1</td><td colspan="1">In this example I am changing permission of /tmp/dir1 to 755 i.e. full permission for user, read+execute permission for group and other users</td></tr>
<tr><td colspan="1" rowspan="2">chgrp</td><td colspan="1"># chgrp GROUPNAME FILE</td><td colspan="1"><p>Change group ownership of files and directories GROUPNAMErepresents the group to be assigned for</p><p>FILE</p></td><td colspan="1" rowspan="2">man page for chgrp</td></tr>
<tr><td colspan="1"># chgrp admin /tmp/file</td><td colspan="1"><p>In this example we are changing the group ownership to admin group for</p><p>/tmp/file</p></td></tr>
<tr><td colspan="1" rowspan="2">groups</td><td colspan="1"># groups USERNAME</td><td colspan="1"><p>Print group memberships for</p><p>each USERNAME</p></td><td colspan="1" rowspan="2">man page for groups</td></tr>
<tr><td colspan="1"><p># groups Ankit</p><p>Ankit : Ankit admin</p></td><td colspan="1">In this example we are checking the list of group which user Ankit is part of.</td></tr>
<tr><td colspan="1" rowspan="2" valign="top">newgrp</td><td colspan="1">$ newgrp GROUPNAME</td><td colspan="1">The newgrp command is used to change the current group ID during a login session</td><td colspan="1" rowspan="2" valign="top">man page for newgrp</td></tr>
<tr><td colspan="1" valign="top">$ id uid=1001(Ankit) gid=1001(Ankit) groups=1001(Ankit),1003(admin)</td><td colspan="1" valign="top">In this example we are changing the primary group of user Ankit to admin group</td></tr>
</table>

<table><tr><th colspan="1" valign="top">Command</th><th colspan="1" valign="top">Example/Syntax</th><th colspan="1" valign="top">Comments</th><th colspan="1">For more details</th></tr>
<tr><td colspan="1"></td><td colspan="1" valign="top"><p>$ newgrp admin</p><p>$ id uid=1001(Ankit) gid=1003(admin) groups=1003(admin),1001(Ankit)</p></td><td colspan="1"></td><td colspan="1"></td></tr>
<tr><td colspan="1" rowspan="2">setfacl</td><td colspan="1"># setfacl OPTIONS FILE</td><td colspan="1"><p>This utility sets Access Control Lists (ACLs) of files and directories.</p><p>It is useful to give individual permission to users and groups as chmod assigns permission of file level but here we have more control over each user permission</p></td><td colspan="1" rowspan="2">setfacl examples</td></tr>
<tr><td colspan="1"># setfacl -m u:Ankit:rx /tmp/file</td><td colspan="1"><p>In this example I am giving read and execute permission for user Ankit for</p><p>/tmp/file</p></td></tr>
<tr><td colspan="1" rowspan="2">getfacl</td><td colspan="1"># getfacl FILE</td><td colspan="1"><p>For each file, getfacl displays the file name, owner, the group, and the Access Control List (ACL). If a</p><p>directory has a default ACL,</p><p>getfacl also displays the default ACL</p></td><td colspan="1" rowspan="2">getfacl examples</td></tr>
<tr><td colspan="1"><p>- getfacl /tmp/file</p><p>getfacl: Removing leading '/'</p><p>from absolute path names</p><p>- file: tmp/file</p><p>&emsp;- owner: root</p><p>- group: admin user::rw- user:Ankit:r-x group::r-- mask::r-x other::r--</p></td><td colspan="1"><p>In this example I am collecting the acl permission list from /tmp/file</p><p>It has the permission detail which we applied earlier with setfacl</p></td></tr>
<tr><td colspan="1" valign="top">Command</td><td colspan="1" valign="top">Example/Syntax</td><td colspan="1" valign="top">Comments</td><td colspan="1">For more details</td></tr>
<tr><td colspan="1" rowspan="2">chattr</td><td colspan="1"># chattr OPTIONS FILE</td><td colspan="1">chattr changes the file attributes on a Linux file system</td><td colspan="1" rowspan="2">chattr examples</td></tr>
<tr><td colspan="1"># chattr +i /tmp/file</td><td colspan="1"><p>In this example we have restricted the modification permission on /tmp/file . Now not even root user can modify the content of</p><p>/tmp/file</p><p>To remove this permission use chattr -i /tmp/file</p></td></tr>
<tr><td colspan="1" rowspan="2">lsattr</td><td colspan="1"># lsattr FILE</td><td colspan="1"><p>list file attributes on a Linux second extended file system. By default ls command will not show the permission</p><p>attributes applied by chattr</p><p>so we must use lsattr to get these details</p></td><td colspan="1" rowspan="2">lsattr examples</td></tr>
<tr><td colspan="1"><p># lsattr /tmp/file</p><p>----i---------e---- /tmp/file</p></td><td colspan="1"><p>In this example we can see the "i" attribute which we added with chattr in the previous example</p><p>The 'e' attribute indicates that the file is using extents for mapping the blocks on disk. It may not be removed using</p><p>chattr</p></td></tr>
</table>
Configure and Troubleshoot Network

This section will help Network engineers who are new to Linux environment. I have tried to place the most used commands for network troubleshooting, we also have tcpdump, iperf, netperf and many other networking tools which are used for troubleshooting network related issues but they can get complicated hence those are not mentioned in this list.

<table><tr><th colspan="1">Command</th><th colspan="1">Example/Syntax</th><th colspan="1">Comments</th><th colspan="1">For more details</th></tr>
<tr><td colspan="1">ifconfig</td><td colspan="1"># ifconfig</td><td colspan="1"><p>This program is obsolete! For replacement check ip addr and ip link . For statistics use ip -s link .</p><p>If no arguments are given, ifconfig displays the status of the currently active</p><p>interfaces. If a single interface argument is given, it displays the status of the given interface only;</p></td><td colspan="1">man page for ifconfig</td></tr>
<tr><td colspan="1" rowspan="2">ip</td><td colspan="1"># ip [OPTIONS]</td><td colspan="1">Newer command to monitor and set IP address and other network card–related information</td><td colspan="1" rowspan="2">ip examples</td></tr>
<tr><td colspan="1"># ip link show</td><td colspan="1">This example lists the available network device on the Linux server along with their Link status</td></tr>
<tr><td colspan="1">route</td><td colspan="1" valign="top"><p># route</p><p>[OPTIONS]</p></td><td colspan="1">This program is obsolete. For replacement check ip route .</td><td colspan="1">ip route examples</td></tr>
<tr><td colspan="1" rowspan="2">ip route</td><td colspan="1"># ip route [OPTIONS]</td><td colspan="1">Manipulate route entries in the kernel routing tables keep information about paths to other networked nodes.</td><td colspan="1" rowspan="2">ip route examples</td></tr>
<tr><td colspan="1"># ip route show</td><td colspan="1">In this example we are printing the configured routes on the Linux server from the routing table</td></tr>
<tr><td colspan="1" rowspan="2">ethtool</td><td colspan="1" valign="top"><p># ethtool</p><p>[OPTIONS] DEVICE</p></td><td colspan="1">query or control network driver and hardware settings</td><td colspan="1" rowspan="2">man page for ethtool</td></tr>
<tr><td colspan="1"># ethtool -i eth0</td><td colspan="1">In this example we are printing the interface details for eth0 . The interface name may vary based on the environment and configuration.</td></tr>
<tr><td colspan="1" valign="top">ping</td><td colspan="1"># ping OPTIONS DESTINATION</td><td colspan="1" valign="top"><p>ping is used to check the connectivity of</p><p>remote computers</p></td><td colspan="1">man page for ping</td></tr>
</table>

|||
| :- | :- |
|||
|||
|||
|||
|||
|||
|||
|||
|||

<table><tr><th colspan="1">Command</th><th colspan="1">Example/Syntax</th><th colspan="1">Comments</th><th colspan="1">For more details</th></tr>
<tr><td colspan="1"></td><td colspan="1" valign="top"><p># ping</p><p>192\.168.0.100</p></td><td colspan="1">In this example we are testing the connectivity between localhost and 192.168.0.100 server</td><td colspan="1"></td></tr>
<tr><td colspan="1" rowspan="2">traceroute</td><td colspan="1"># traceroute HOST</td><td colspan="1"><p>Utility that helps you analyzing reachability of hosts on the network.</p><p>In most cases it is possible that due to firewall you may not get the list of hops towards the destination</p></td><td colspan="1" rowspan="2">man page for traceroute</td></tr>
<tr><td colspan="1"><p># traceroute</p><p>192\.168.0.100</p></td><td colspan="1"><p>In this example we are checking the route</p><p>used to connect 192.168.0.100</p></td></tr>
<tr><td colspan="1" valign="top">nmap</td><td colspan="1" valign="top"># nmap OPTIONS HOST</td><td colspan="1"><p>Utility that helps you check which services are offered by an other host</p><p>It is used to check the list of open ports on destination server</p></td><td colspan="1">man page for nmap</td></tr>
<tr><td colspan="1" rowspan="2">netstat</td><td colspan="1"># netstat [OPTIONS]</td><td colspan="1"><p>Utility that helps you find out which services are offered by the local host</p><p>It will give you a list of ports which are used by different system services and any service from the network</p></td><td colspan="1" rowspan="2">man page for netstat</td></tr>
<tr><td colspan="1"># netstat -tunlp</td><td colspan="1">In this example I am listing the listening TCP and UDP protocols on my Linux server</td></tr>
<tr><td colspan="1">nmcli</td><td colspan="1" valign="top"><p># nmcli</p><p>[OPTIONS]</p></td><td colspan="1">nmcli is a command-line tool for controlling NetworkManager and reporting network status.</td><td colspan="1">nmcli examples</td></tr>
<tr><td colspan="1">nmtui</td><td colspan="1"># nmtui</td><td colspan="1"><p>nmtui is a curses-based TUI application for interacting with NetworkManager</p><p>It is a graphical alternative to nmcli</p></td><td colspan="1">nmtui examples</td></tr>
<tr><td colspan="1">ss</td><td colspan="1"># ss [OPTIONS]</td><td colspan="1"><p>ss is used to dump socket statistics. It allows showing information similar to</p><p>netstat . It can display more TCP and state information than other tools.</p><p>When no option is used ss displays a list of open non-listening sockets (e.g. TCP/UNIX/UDP) that have established connection</p></td><td colspan="1">man page for ss</td></tr>
</table>

Managing Partitions and Logical Volumes

One of the primary roles of system administrator would be to configure partitions, storage layouts in the Linux server. Here you can get the list of most used Linux commands for managing partitions and file systems.



<table><tr><th colspan="1">Command</th><th colspan="1">Example/Syntax</th><th colspan="1">Comments</th><th colspan="1">For more details</th></tr>
<tr><td colspan="1">df</td><td colspan="1"># df [OPTIONS]</td><td colspan="1"><p>Report file system disk space usage</p><p>If no file name is given, the space available on all currently mounted file systems is shown</p></td><td colspan="1">man page for df</td></tr>
<tr><td colspan="1">fdisk</td><td colspan="1"># fdisk [OPTIONS] DEVICE</td><td colspan="1">fdisk is interactive program for creation and manipulation of partition tables. It understands GPT, MBR, Sun, SGI and BSD partition tables</td><td colspan="1">fdisk example</td></tr>
<tr><td colspan="1">cfdisk</td><td colspan="1"><p># cfdisk</p><p>[OPTIONS] DEVICE</p></td><td colspan="1">Display or manipulate a disk partition table</td><td colspan="1">man page for cfdisk</td></tr>
<tr><td colspan="1">parted</td><td colspan="1"># parted</td><td colspan="1">parted is a program to manipulate disk partitions. It supports multiple partition table formats, including MS-DOS and GPT.</td><td colspan="1">parted example</td></tr>
<tr><td colspan="1" rowspan="2">pvcreate</td><td colspan="1" valign="top"><p># pvcreate</p><p>[OPTIONS] DEVICE</p></td><td colspan="1">Create LVM Physical Volume</td><td colspan="1" rowspan="2">pvcreate example</td></tr>
<tr><td colspan="1" valign="top"># pvcreate /dev/sda</td><td colspan="1">In this example we are creating a physical volume using /dev/sda device</td></tr>
<tr><td colspan="1">pvdisplay</td><td colspan="1" valign="top"># pvdisplay DEVICE</td><td colspan="1">It shows the attributes of PVs, like size, physical extent size, space used for the VG descriptor area, etc</td><td colspan="1">man page for pvdisplay</td></tr>
<tr><td colspan="1">Command</td><td colspan="1">Example/Syntax</td><td colspan="1">Comments</td><td colspan="1">For more details</td></tr>
<tr><td colspan="1">pvs</td><td colspan="1"># pvs</td><td colspan="1">Display information about physical volumes This can be used as an alternative to pvdisplay to display limited information of available physical volumes</td><td colspan="1">man page for pvs</td></tr>
<tr><td colspan="1" rowspan="2" valign="top">vgcreate</td><td colspan="1"># vgcreate [OPTIONS]</td><td colspan="1" valign="top">It creates a new Volume Group on block devices (physical volume)</td><td colspan="1" rowspan="2" valign="top">vgcreate example</td></tr>
<tr><td colspan="1"><p># vgcreate</p><p>test_vg /dev/sda</p></td><td colspan="1"><p>In this example we are create a new volume</p><p>group "test_vg" by adding /dev/sda</p><p>Here /dev/sda is a new physical volume, you cannot use any existing device used by other logical volumes</p></td></tr>
<tr><td colspan="1">vgdisplay</td><td colspan="1"># vgdisplay DEVICE</td><td colspan="1">vgdisplay shows the attributes of VGs, and the associated PVs and LVs</td><td colspan="1">man page for vgdisplay</td></tr>
<tr><td colspan="1">vgs</td><td colspan="1"># vgs</td><td colspan="1">Display information about Volume Groups This can be used as an alternative to vgdisplay to display limited information of available volume groups</td><td colspan="1">man page for vgs</td></tr>
<tr><td colspan="1" rowspan="2">lvcreate</td><td colspan="1"># lvcreate [OPTIONS]</td><td colspan="1">This is used to create logical volumes</td><td colspan="1" rowspan="2">lvcreate example</td></tr>
<tr><td colspan="1"># lvcreate -L 1G -n test_lv1 test_vg</td><td colspan="1"><p>In this example I am creating a logical volume test_lv1 of size 1GB under</p><p>test_vg volume group</p></td></tr>
<tr><td colspan="1">lvdisplay</td><td colspan="1" valign="top"># lvdisplay DEVICE</td><td colspan="1">Display information about a logical volume</td><td colspan="1">man page for lvdisplay</td></tr>
<tr><td colspan="1">lvs</td><td colspan="1"># lvs</td><td colspan="1">Display information about logical volumes in shorter output compared to lvdisplay command. You can use this as an alternative to lvdisplay</td><td colspan="1">man page for lvs</td></tr>
<tr><td colspan="1">pvscan</td><td colspan="1"><p># pvscan</p><p>[OPTIONS]</p></td><td colspan="1"><p>Scans storage devices for the presence of LVM physical volumes.</p><p>It is used when a new physical volume metadata is not loaded and a pvscan can load the metadata of all the available PV</p></td><td colspan="1">pvscan example</td></tr>
</table>

<table><tr><th colspan="1">Command</th><th colspan="1">Example/Syntax</th><th colspan="1">Comments</th><th colspan="1">For more details</th></tr>
<tr><td colspan="1">vgscan</td><td colspan="1"><p># vgscan</p><p>[OPTIONS]</p></td><td colspan="1"><p>Scans storage devices for the presence of LVM volume groups.</p><p>It can be used when any VG metadata is not visible and vgscan can scan the available VG</p></td><td colspan="1">man page for vgscan</td></tr>
<tr><td colspan="1" valign="top">lvscan</td><td colspan="1" valign="top"><p># lvscan</p><p>[OPTIONS]</p></td><td colspan="1"><p>Scans storage devices for the presence of LVM logical volumes.</p><p>It can be used when any LV metadata is not visible and lvscan can scan the available LV</p></td><td colspan="1">man page for lvscan</td></tr>
<tr><td colspan="1" rowspan="2">vgchange</td><td colspan="1"># vgchange [OPTIONS]</td><td colspan="1">Changes the status from LVM volume groups and the volumes in it from active to inactive and vice versa</td><td colspan="1" rowspan="2">vgchange example</td></tr>
<tr><td colspan="1"># vgchange -ay</td><td colspan="1">In this example we are activating all the available volume groups. To deactivate all volume groups use vgchange -an</td></tr>
<tr><td colspan="1">e2fsck</td><td colspan="1"><p># e2fsck</p><p>[OPTIONS]</p></td><td colspan="1">check a Linux ext2/ext3/ext4 file system We cannot perform a check on a mounted file system so normally this is performed during reboot or in single user mode</td><td colspan="1">e2fsck example</td></tr>
<tr><td colspan="1">tune2fs</td><td colspan="1"><p># tune2fs</p><p>[OPTIONS] DEVICE</p></td><td colspan="1">tune2fs allows the system administrator to adjust various tunable filesystem parameters on Linux ext2, ext3, or ext4 filesystems.</td><td colspan="1">tune2fs example</td></tr>
<tr><td colspan="1">dumpe2fs</td><td colspan="1"><p># dumpe2fs</p><p>[OPTIONS] DEVICE</p></td><td colspan="1">prints the super block and blocks group information for the filesystem present on device.</td><td colspan="1">man page for dumpe2fs</td></tr>
<tr><td colspan="1">mkfs.</td><td colspan="1"><p>- mkfs.ext4</p><p>- mkfs.xfs</p></td><td colspan="1"><p>mkfs is used to build a Linux filesystem on a device, usually a hard disk partition. The device argument is either the device name</p><p>(e.g. /dev/hda1, /dev/sdb2), or a regular file that shall contain the filesystem.</p></td><td colspan="1">create filesystem</td></tr>
<tr><td colspan="1">lvextend</td><td colspan="1" valign="top"># lvextend OPTIONS</td><td colspan="1">Add space to a logical volume</td><td colspan="1">lvextend example</td></tr>
<tr><td colspan="1" valign="top">vgextend</td><td colspan="1"># vgextend VGNAME PV</td><td colspan="1" valign="top">Add physical volumes to a volume group</td><td colspan="1" valign="top">vgextend example</td></tr>
</table>

|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
|resize2fs|# resize2fs DEVICE|The resize2fs program will resize ext2, ext3, or ext4 file systems. It can be used to enlarge or shrink an unmounted file system located on device|resize2fs example|
|lsscsi|<p># lsscsi</p><p>[OPTIONS]</p>|list attached SCSI devices (or hosts)|man page for lsscsi|
|lsblk|# lsblk|lsblk lists information about all available or the specified block devices. The lsblk command reads the sysfs filesystem and udev db to gather information|man page for lsblk|
|blkid|# blkid|It prints the UUID valud of all the connected storage device. You can use this UUID to identify the storage device instead of using the physical name|man page for blkid|

Managing RPM and Software Repositories

With package manager such as yum, dnf, apt-get, the life of a system administrator becomes very easy. You can easily install, update, remove packages, upgrade server operating system and much more using these commands.


|Command|Example/Syntax|Comments|For more details|
| - | - | - | - |
|rpm|# rpm [OPTIONS] FILE|RPM Package Manager which can be used to build, install, query, verify, update, and erase individual software packages.|man page for rpm|
|yum|# yum [OPTIONS] FILE|<p>yum is short abbreviation for Yellow Dog Updater Modified.</p><p>It is obsolete now and is replaced by dnf in most recent Linux</p>|yum examples|

<table><tr><th colspan="1" rowspan="11"></th><th colspan="1">Command</th><th colspan="1">Example/Syntax</th><th colspan="1">Comments</th><th colspan="1">For more details</th><th colspan="1" rowspan="11"></th></tr>
<tr><td colspan="1"></td><td colspan="1"></td><td colspan="1" valign="top"><p>distributions.</p><p>YUM is a package manager for RPM-based Linux distributions</p></td><td colspan="1"></td></tr>
<tr><td colspan="1">yumdownloader</td><td colspan="1"># yumdownloader [OPTIONS]</td><td colspan="1">Allows you to download packages from a repository to your system without installing them</td><td colspan="1">yumdownloader examples</td></tr>
<tr><td colspan="1">zypper</td><td colspan="1"><p># zypper</p><p>[OPTIONS] FILE</p></td><td colspan="1"><p>Package management utility in the SUSE works. Works more or less the same as yum.</p><p>The handling of repository is slightly different with zypper</p><p>compared to yum</p></td><td colspan="1">zypper examples</td></tr>
<tr><td colspan="1">apt-get</td><td colspan="1"><p># apt-get</p><p>[OPTIONS] FILE</p></td><td colspan="1">Ubuntu/Debian package management utility. Does a great job in installing and updating software.</td><td colspan="1">man page for apt- get</td></tr>
<tr><td colspan="1">apt-cache</td><td colspan="1"><p># apt-cache</p><p>[OPTIONS] FILE</p></td><td colspan="1">Tool that allows you to search for packages in the locally cached index files</td><td colspan="1">man page for apt- cache</td></tr>
<tr><td colspan="1" valign="top">dpkg</td><td colspan="1"># dpkg [OPTIONS] ACTION</td><td colspan="1">Original Debian package management utility, which has been made more or less obsolete by apt-get</td><td colspan="1">man page for dpkg</td></tr>
<tr><td colspan="1">dpkg- scanpackages</td><td colspan="1"><p># dpkg-</p><p>scanpackages</p><p>[OPTIONS]</p></td><td colspan="1">Tool that allows you to convert a directory containing .deb packages into a repository.</td><td colspan="1">man page for dpkg- scanpackages</td></tr>
<tr><td colspan="1">dnf</td><td colspan="1"># dnf [OPTIONS]</td><td colspan="1">DNF is the next upcoming major version of YUM, a package manager for RPM-based Linux distributions.</td><td colspan="1">dnf examples</td></tr>
<tr><td colspan="1">createrepo</td><td colspan="1" valign="top"><p># createrepo</p><p>[OPTIONS] PATH</p></td><td colspan="1">createrepo is a program that creates a repomd (xml-based rpm metadata) repository from a set of rpms.</td><td colspan="1">createrepo examples</td></tr>
<tr><td colspan="1" valign="top">repoquery</td><td colspan="1" valign="top"># repoquery [OPTIONS]</td><td colspan="1" valign="top">This is part of yum-utils , Searches the available DNF</td><td colspan="1" valign="top">repoquery examples</td></tr>
</table>

|Command|Example/Syntax|Comments|For more details|
| - | - | - | - |
|||repositories for selected packages and displays the requested information about them||
|repotrack|# repotrack [OPTIONS]|This is part of yum-utils , track packages and its dependencies and download them|repotrack examples|
|reposync|# reposync [OPTIONS]|Synchronize packages of a remote DNF or YUM repository to a local directory.|reposync examples|
|subscription- manager|# subscription- manager [OPTIONS]|Registers systems to a subscription management service and then attaches and manages subscriptions for software products|subscription- manager examples|

Manage logging

Now you know about most of the Linux commands to manager different areas of Linux server but you must be familiar of how logging works in Linux? This may vary based on different distribution, with old distros we used syslog-ng for logging but now almost all major distros have moved to rsyslog solution.


|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
|logger|<p># logger</p><p>[OPTIONS]</p><p>MESSAGE</p>|<p>logger makes entries in the system log. When the optional message argument is</p><p>present, it is written to the log.</p>|logger examples|
|logrotate|# logrotate [OPTIONS]|Command that helps you to prevent log files from growing too big and rotate them after a|logrotate examples|

|Command|Example/Syntax|Comments|For more details|
| - | - | - | :-: |
|||certain amount of time or once a given size has been reached||
|journalctl|# journalctl [OPTIONS]|journalctl may be used to query the contents of the systemd journal as written by systemd-journald.service|journalctl examples|

Conclusion

In this cheat sheet  I have tried to consolidate most used Linux commands by different types of experts across IT domains. I am yet to add commands for many other scenarios such as Managing Linux services, archiving, firewall etc but that would just make this tutorial infinite long. So that I know people are reading and loving this cheat sheet then I may decide to spend some more time to write about the remaining Linux commands.


