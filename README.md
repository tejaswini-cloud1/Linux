What is Linux?
Linux is an open-source UNIX-like operating system (OS). An operating system is a software that directly manages a system’s hardware and resources, like CPU, memory, and storage.
1. ls Command
ls is one of the most frequently used basic command in Linux. The ls command-line utility is used to list files and directories that exist inside a directory.

By default, when used without any options, ls lists only the contents of the current directory in alphabetical order without any additional information.

ls
Type ls /home/bob/Project to see the contents of the directory Project.

You can use options with the ls command for variation in results:

ls -a lists hidden files along with other files and directories.
ls -al lists files and directories with file permissions, ownership, and size information.
ls -ltr list file names in the last modification time in reverse order.
The output of ls -al

-rw-r--r-- 1 bob developers 281 Apr  1  2020 /source/project/learn.py
The owner (ie bob) has read and write permissions, other members of the group have read permissions, and the rest of the world has read permissions on the file. The file is owned by the user named bob and belongs to the developers group. The total size of the file is 281 bytes.


2. mkdir Command
The mkdir stands for make directory. The mkdir command is used to create a new directory in Linux.

When you type mkdir Pop, it will create a directory named Pop in the current directory. Whereas, the following Linux command will create a directory named Source inside the Documents directory:

mkdir Documents/Source
Use -p option to create the entire directory structure. For example to create a directory 2020 and its sub-directory Source in the existing Documents directory, type:

mkdir -p Documents/2020/Source
3. cd Command
cd stands for change directory, which is used to change the current working directory. The cd command is used to navigate through Linux files and directories. You need to specify either the full path of the target directory or the directory name you want to change to.

If you are in the /home/bob/Documents directory and need to go to the Photos subdirectory, then type:

cd Photos
Use the absolute path to change directory, change to /home/bob/Pictures directory:

cd /home/bob/Pictures
Some shortcuts that you can use for easy navigation:

cd .. moves one directory up.
cd moves to the home folder.
cd - switch to the parent directory
4. cat Command
The cat stands for concatenate. It is one of the basic command in the Linux operating system. The cat command is used to concatenate files, view the content of a file, create a new file, or redirect output in files.

Type cat command followed by a file name to see the contents of the file.

cat users.txt
The cat command can also be used to perform some advanced operations, such as:

To create a new file named file1.txt, type:

cat > file1.txt
The existing contents of the department.txt file will be overwritten by the contents of users.txt:

cat users.txt > department.txt
To convert the content of file users.txt from lowercase to uppercase and store it in output.txt, use the following command:

cat users.txt | tr a-z A-Z > output.txt
5. pwd Command
pwd stands for present working directory. The pwd command prints the absolute path of the current directory on your Linux terminal. The present working directory is the directory in which you are currently working.

pwd
Output
/home/linuxopsys
In the example /home/linuxopsys is the current directory.

6. uname Command
Use the uname (stands for UNIX name) command to display fundamental information about your Linux computer. By default, this command prints only the type of the operating system, such as Linux.

-a display all information about your computer.
-s display Linux kernel name.
-m displays machine information.
-i display hardware platform information.
The output of uname -a command on my machine:

Linux linux 5.13.0-37-generic #42~20.04.1-Ubuntu SMP Tue Mar 15 15:44:28 UTC 2022 x86_64 x86_64 x86_64 GNU/Linux
All system information including OS type, name, user name, kernel release, and hardware platform is displayed.

This command is useful for quickly gathering system details, especially when diagnosing issues or configuring software that depends on specific system properties

7. who Command
Use the who command to list currently logged-in users on your Linux computer. This command also supports few options to display specific information, such as:

-a displays all available information about logged-in users.
-b displays boot time.
-H displays header names.
The output of who command looks like this:

root     pts/0        2022-04-28 01:30 (192.168.1.10)
bob      pts/1        2022-04-28 02:40 (192.168.1.22)
linuxopsys pts/2        2022-04-28 02:05 (192.168.1.22)
It shows 3 users with their logged in date and time.

8. uptime Command
Use the uptime command to display the current system time, the duration for which the system has been up, the number of logged-in users, and average load time for 1, 5, and 15-minute intervals. This Linux command retrieves information from the /proc/uptime file.

The output of uptime command from my system:

17:11:28 up 6 days,  3:23,  1 user,  load average: 0.00, 0.01, 0.00
9. hostname Command
Use hostname command to display the Domain Name System (DNS) name and set the hostname or Network Information System (NIS) of your system.

Display host name and domain name, type:

hostname
linuxopsys
Some distributions allow you to set hostname for your machine, type:

sudo hostname NEW_HOSTNAME
You can replace NEW_HOSTNAME with your actual machine name.

10. shutdown Command
Use the shutdown command to gracefully and securely shut down your Linux computer.

Use the reboot command to restart your Linux computer. You can also use the shutdown -r command to restart your computer using the shutdown command.  

To restart your system after 5 minutes:

shutdown -r +5
To immediately restart your computer:

reboot
11. cp Command
The cp command is used to copy files and directories from the source directory to another location. By default, it copies only the given file or directory, but you can use the -r option to copy a directory along with its subdirectories.

The following command copy the file users.txt from the current working directory to the Documents/records directory.

cp users.txt Documents/records/
To create a copy of the file file2.txt with the name file2_backup.txt in your current working directory.

cp file2.txt file2_backup.txt
12. mv Command
Use the mv (stands for move) command to move files or directories from the source to the destination directory. It can be used to rename a file/directory.

The following mv command moves the users.txt file to the Documents/records directory.

mv users.txt Documents/records
To rename the employees.txt file to users.txt:

mv employees.txt users.txt
13. rm Command
Use the rm (stands for remove) command to remove the given file, multiple files, or a group/type of files. By default, the rm command does not require user confirmation to delete a file, but you can enable user confirmation using the -i option.

Options can be used with the rm command for the following needs:

-i deletes files in interactive mode.
-f forcefully removes the write-protected file.
-r recursively deletes files, directories, and subdirectories in the specified parent directory.
-d deletes the specified empty directory.
Removes the file named documents.txt from the current directory:

rm documents.txt
To remove directories and their contents recursively, type:

rm -r Documents
To remove the directory without being prompted, type:

rm -rf dir1
The rm-rf command should be used with caution.

14. df Command
The df stands for disk filesystem. It is used to get a complete summary of used and available disk space of the file system in your Linux computer.

Options can be used with the df command to get variations in the output such as:

-a displays all file systems.
-h displays output in a human-readable format.
-T displays file system type.
-m displays output in mebibyte (MiB).
-g displays output in gibibyte (GiB).
Check disk usage information of a particular file system, type:

df /dev/sda5
Output
Filesystem 1K-blocks Used        Available Use%  Mounted on

/dev/sda5   40503552    9132528   29283856  24% /
Here, /dev/sda5 has a total size of 40503552, the used size is 9132528, and the available size is 29283856. The file system has used 24% of the total allocated space and it is mounted on /.

15. vi and nano Command
Use the vi and nano commands to create a new file, read a file, or edit an existing file. Vi is the default text editor for several Linux distributions and it is very simple to use. Nano is a terminal-based text editor that is ideal for making some changes to any files or creating basic plain text files.

To open the existing file or to create a new file:

vi updates.txt
or
nano filename.txt
16. touch Command
Use the touch command to create an empty file on your Linux computer, or to modify the timestamp of a file. The primary function of this command is to update file timestamps, but it is most commonly used to create a file. The touch command can update access and modification timestamps of the specified file, and create the file if it does not already exist.

To create a new empty file named install.doc, type:

touch install.doc
In this example, the modification time of the file updates.txt is updated to the current time.

touch -m updates.txt
17. du Command
Use the du (stands for disk usage) command to gain disk usage information of a particular file or directory on your Linux computer. By default, the du command displays disk usage information in the number of blocks used by a file. Use the -h option with this command to display output in a human-readable format.

Specify the file name or directory name to display its disk usage.

du -h /var/log/apache/access.log
du -h /var/log
18. chmod command
The chmod command is used to change the mode (permission) of a file. The basic permissions a file can have are r(read), w(write), and x(execute).

Using numeric mode you can set read (value is 4), write (value is 2 and execute (value is 1) permissions for owner, group and all others.

For example to give file1.txt owner and group read and write permissions and only read permission to all others, type:

chmod 664 file1.txt
You may use -R option to recursively set permissions for all files and directories in a given directory.

To make the file executable, type:

chmod +x myscript.sh
19. chown command
The chown command is used to change file and directory ownership in Linux.

To change both owner and group of file, type:

chown ownername:groupname filename
You may use -R option to recursively set ownership for all files and directories in a given directory.

20. top
Use the top or htop commands to monitor the server’s processes or vital system resources in real-time. Both these commands are used for the same purpose, but their output is different. The default output displays information about top CPU-consuming processes along with RAM usage.

top
The command also displays system up time, load average, number of logged in users, memory, total tasks, and running tasks.

Htop is an improved version of the top command. It display colorful text and allows for output scrolling. Htop doesnt comes preinstalled on most Linux distros.

21. zip and unzip Command
Use the zip command-line utility to create an archive of files, and the unzip command for uncompressing a zip archive. The zip command can also be used to modify a zip archive.

To create a zip archive named users.zip from the specified files:

zip users.zip output.txt install.doc newfiles.txt updates.txt
To extract the contents of the users.zip archive to the current directory: 

unzip users.zip
22. tar Command
Use the tar command to create a compressed or uncompressed archive of specified files. You can also use this command to modify, maintain, or extract tar archives. Tar archives can combine multiple files or directories into a single file.

The tar command provides multiple options to create a tarball:

-c creates an archive.
-x extracts the archive.
-f assigns filename to the archive.
-t displays files in an archive.
To create an uncompressed archive file named users.tar of the specified files.

tar cf users.tar updates.txt newfiles.txt
23. sudo Command
Use the sudo command to execute commands as root or another Linux user, as specified in your security policy. This command allows you to execute commands that otherwise require a root password.

Specify the command that requires root permissions after the sudo command. To run the useradd command as sudo to create a new user named bob:

$ sudo useradd bob
24. useradd Command
Use the useradd command to add new users to your Linux system. This command enables you to add a new user with specific group preferences, user ID (UID), and login shell. When you run this command without any option, it creates a user using the default account settings specified in the /etc/default/useradd file.

To create a new user named steve that has GID 1000, and UID 1021, and will expire on 31st May 2022:

sudo useradd -g 1000 -u 1021 -e 2022-05-31 steve
25. groupadd Command
Use the groupadd command to add a new group to your Linux system. This command enables you to add a new group with specific group preferences and override default /etc/login.def default values. When you create a new user group using this command, it adds a new entry in the /etc/group file.

To create a new group named docs that has GID 1018:

sudo groupadd -g 1018 docs
26. usermod Command
Use the usermod command to change the properties of existing users in Linux. Using this command, you can modify the password, primary group, login directory, expiry date, and other user attributes. You can also add a user to an existing group using this command.

To add the user steve to sudo group, type:

sudo usermod -aG sudo steve
27. passwd Command
Use the passwd command to change the user account password. A normal user can change only their own password, but the root user or user with sudo privileges can change the password of any user account. This command can also be used to delete or expire an account password.

To change the password for the user bob:

sudo passwd bob
28. ps Command
Use the ps command to check the status of the active processes on your Linux system, and display information about these processes. Administrators can use this information to kill the processes or to set process priorities.

To show all running processes in the default output format:

ps
To display all running processes in full format: 

ps -af
29. history Command
Use the history command to view the history of all the previously executed terminal commands that you run. The maximum number of entries that BASH should store can be defined in your .bashrc file. Linux commands that you execute are considered events and every event is associated with an event number. You can recall, remove, or change commands using their event numbers.

To list the last 5 commands, including itself:

history 5
To remove the history of event number 1525:

history -d 1525
Note: history command behavior may change depending on the shell you are being used.

30. which Command
Use the which command to locate the executable file of the specified command. This command searches for the executable file location in the $PATH environment variable. The which command returns any of the following status:

To display executable file locations for useradd command, type:

which useradd /usr/sbin/useradd
31. less Command
Use the less command to view the contents of a file one screen at a time, starting at the beginning. This command provides the capability of both backward and forward navigation. The less command has quick file access because it does not access the entire file if the file is large.

To display the contents of the updates.txt file one screen at a time.

less updates.txt
32. tail Command
Use the tail command to view the contents of a file, starting at the bottom. By default, it displays the last 10 lines of the file, but you can change this default behavior. The tail command can also be used to monitor the file. When you add new lines to the file, then the display is updated.

To display the last 10 lines of the file updates.txt:

tail updates.txt
To display the last 15 lines of the file access.log:

tail -n 15 access.log
33. head Command
Use the head command to display the contents of a file, starting at the beginning. By default, it displays the first 10 lines of the file, but you can change this default behavior.

To display the first 10 lines of the file updates.txt:

head updates.txt
34. grep Command
Use the grep, also known as global regular expression print, the command to search for a word or string of characters in a file or directory. The search pattern is termed regular expression. When the grep command finds a matching string in the file, then this command prints the line that contains the string.

To search for the string 'welcome' in the file log.txt:

grep welcome log.txt
35. find Command
Use the find command to search and locate the files and directories that match the specified conditions. This command enables you to search using file or folder name, creation date, modification date, permissions, and owner.

To search the file named program.py in the /home/linuxopsys/projects directory, type:

find /home/linuxopsys/projects -type f -name program.py
To search for files with given permissions in the current directory:

find . -perm 664
36. echo Command
Use the echo command to display the specified text or string on the terminal. This command is most commonly used in batch files and scripting languages to display standard text output. You can also use this command to display the values of an environment variable.

To print the string “This is a sample string” on the terminal:

echo "This is a sample string"
This is a sample string
To print the value of the PATH environment variable:

echo $PATH
Output:

/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin
37. alias
The Alias command allows you to define temporary aliases for current sessions. It allows you to execute one or more commands.

Create a new alias named 'lsall', type:

alias lsall="ls -a"
Lists all aliases for the current session:

alias
Note: Alias behavior may change depending on the shell you are being used. It is traditionally used in bash shell.

38. wget command
The wget command is used to retrieve or download content from the internet.

To download WordPress using wget, type:

wget https://wordpress.org/latest.tar.gz
The latest.tar.gz file will be downloaded to the current directory.

39. clear command
The clear command is used in Linux to clear the terminal screen. This is similar to cls command in other operating systems.

clear
40. man Command
Use the man command to display the user manual of the Linux command. Almost all the Linux commands have man pages, which is a kind of documentation that is displayed on the terminal. The Linux commands manual page explains what a particular command does, syntax, and accepted arguments.

Type man followed by the command name to display the command user manual page.

man mkdir
Similarly, you can also use the –-help option to display the help pages of a particular command.

mkdir --help
