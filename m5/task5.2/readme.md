task 5.2

1. The /etc/passwd contains one entry per line for each user (user account) of the system.
After command: cat /etc/passwd we can see list of users. 

![img](/../master/images/task_5_2_1.png?raw=true "screenshot") 
Come fields are present, such as:
1. Username. 
2. Password.
3. User ID (UID).
4. Group ID (GID). 
5. User ID Info.  
6. Home directory.  
7. Command/shell.  

Accounts with UIDs less than 10 belong to the system, and UIDs 10 to 100 are reserved for pseudo-users associated with special programs.

2. User ID (UID): Each user must be assigned a user ID (UID). 
UID 0 (zero) is reserved for root and UIDs 1-99 are reserved for other predefined accounts. 
Further UID 100-999 are reserved by system for administrative and system accounts/groups. 

3. Group ID (GID): The primary group ID (stored in /etc/group file)
After command: cat /etc/group we can see list of users.
 
![img](/../master/images/task_5_2_2.png?raw=true "screenshot") 

4. Command: group [username], help to check which group a certain user belongs.
Command: id [username], help to see the list the group members along with their GIDs.

![img](/../master/images/task_5_2_3.png?raw=true "screenshot")

5. Only root or users with sudo privileges can add new users your system. Command 'sudo useradd username' adds new users.
The command adds an entry to the /etc/passwd, /etc/shadow, /etc/group and /etc/gshadow files.
6. I changed the name (account name) of an existing user with the command 'usermod -l new_login_name old_name

![img](/../master/images/task_5_2_4.png?raw=true "screenshot")

7. The skel directory contains files and directories that are automatically copied over to a new user’s when it is created from useradd command.
We can see structure of skel.dir with command 'ls -la /etc/skel'

![img](/../master/images/task_5_2_5.png?raw=true "screenshot")

8. I use the command 'userdel -r user_name' to force userdel to remove the user’s home directory and mailbox.

9.  We can to lock a user account with command 'sudo passwd -l'. 
The effect of this command is to insert an exclamation point as the first character in the encrypted password field in the /etc/shadow file. 
This is enough to keep the password from working. 
We can to unlock a user account with command 'sudo passwd -u'. 
Another way to lock a user account is to the the 'chage' command that helps manage account expiration dates (command 'sudu chage -E0', 'sudo passwd -S').

10. We can to remove a user's password with command 'sudo passwd -d user_name'.
We can to provide user with a password-free login with command 'usermod -s /usr/sbin/nologin username'.

11. We can to extende format of information about the directory with commands 'ls -l' and 'stat'.

![img](/../master/images/task_5_2_6.png?raw=true "screenshot")
With command 'ls' we receive next information:
The first character shows the file type:  
- - Regular file.
b - Block special file.
c - Character special file.
d - Directory.
l - Symbolic link.
n - Network file.
p - FIFO.
s - Socket.

The next nine characters are showing the file permissions. 
The first three characters are for the user, the next three are for the group, and the last three are for others. 
You can change the file permissions with the chmod command. The permission character can take the following value:
r - Permission to read the file.
w - Permission to write to the file.
x - Permission to execute the file.
s - setgid bit.
t - sticky bit.

12. The permission character can take the following value:
r - Permission to read the file.
w - Permission to write to the file.
x - Permission to execute the file.
s - setgid bit.
t - sticky bit.

13. We can to define the relationship between the file and the user with command "ls -l'.

14. 
![img](/../master/images/task_5_2_7.png?raw=true "screenshot")

15. Umask is a Linux command that is used to assign the default file permission sets for newly created folders and files. 
The term mask references the grouping of the permission bits, each of which defines how its corresponding permission is set for newly created files. 
The bits in the mask may be changed by invoking the umask command.
When using the term Umask, we are referring to one of the following two meanings:
The user file creation mode mask that is used to configure the default permissions for newly created files and directories
The command “umask” which is used to set the umask value.
Octal value : Permission
0 : read, write and execute
1 : read and write
2 : read and execute
3 : read only
4 : write and execute
5 : write only
6 : execute only
7 : no permissions

![img](/../master/images/task_5_2_8.png?raw=true "screenshot")

16. When set on an executable, the sticky bit flagged to the operating system that the text portions of the executable should be held in swap, making their re-use faster. 
On Linux, the sticky bit only affects a directory—setting it on a file wouldn’t make sense.
When you set the sticky bit on a directory, people can only delete files that belong to them within that directory. 
They can’t delete files that belong to someone else, no matter which combination of file permissions are set on the files.
This allows you to create a directory that everyone—and the processes they launch—can use as shared file storage. 
The files are protected because, again, no one can delete anyone else’s files.

![img](/../master/images/task_5_2_9.png?raw=true "screenshot")

![img](/../master/images/task_5_2_10.png?raw=true "screenshot").

![img](/../master/images/task_5_2_12.png?raw=true "screenshot").

17. File attribute should be present with command 'lsattr'. 

![img](/../master/images/task_5_2_11.png?raw=true "screenshot").



