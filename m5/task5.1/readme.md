task 5.1

Part 1. 
Passwd is the command used in Linux and UNIX-like operating systems to change password.
When we run passwd command the user's encrypted password is stored in /etc/shadow file.

To get the lists of users using the getent run the command:getent passwd

![img](/../master/images/task_5_1_1.png?raw=true "screenshot") 

There are lists the content of the /etc/passwd file using the database info stored in the /etc/nsswitch.conf file.

![img](/../master/images/task_5_1_2.png?raw=true "screenshot") 


Help is a bash command. It uses internal bash structures to store and retrieve information about bash commands.

Man is a macro set for the troff (via groff) processor. The output of processing a single file is sent to a pager by the man command by default.

Info is a text-only viewer for archives in the info format output of Texinfo.


![img](/../master/images/task_5_1_3.png?raw=true "screenshot") 
![img](/../master/images/task_5_1_4.png?raw=true "screenshot") 

![img](/../master/images/task_5_1_5.png?raw=true "screenshot") 


![img](/../master/images/task_5_1_6.png?raw=true "screenshot") 

Part 2.

I used command "file" to determine the type of file 

![img](/../master/images/task_5_1_7.png?raw=true "screenshot") 

To return to user's home directory from any directory within a filesystem I used cd ~/ command without any options and arguments.

Ls command with
-a switche - do not ignore entries starting with .
-l switch - use a long listing format
![img](/../master/images/task_5_1_8.png?raw=true "screenshot")
 
![img](/../master/images/task_5_1_9.png?raw=true "screenshot")
 
![img](/../master/images/task_5_1_10.png?raw=true "screenshot") 

![img](/../master/images/task_5_1_11.png?raw=true "screenshot") 


![img](/../master/images/task_5_1_12.png?raw=true "screenshot") 
 

I change the data by opening a symbolic link. File data changes are displayed in the hard link.


 I delete the labwork2. A hard link displayed content of the file labwork2. A symbolic link is empty.
![img](/../master/images/task_5_1_13.png?raw=true "screenshot") 


![img](/../master/images/task_5_1_15.png?raw=true "screenshot") 

The types of devices are character, block, pipe, socket.
To determine the type of device you must to enter command: ls -l /dev

For example: 

![img](/../master/images/task_5_1_17.png?raw=true "screenshot") 

To determine the type of file I enter command df -Th


![img](/../master/images/task_5_1_18.png?raw=true "screenshot") 

In Linux there are basically three types of files: Ordinary/Regular files, Special files, Directories.
Ordinary/Regular Files contains text, data or program instructions and they are the most common type of files you can expect to find on a Linux system and they include:
Readable files
Binary files
Image files
Compressed files and so on.

15) 
![img](/../master/images/task_5_1_16.png?raw=true "screenshot") 

