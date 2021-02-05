task 5.3

Part 1.

1. Linux has basically 5 states:
1) Running/Runnable (R): running processes are processes using a CPU core right now, a runnable process is a process that has everything to run and is just waiting for a CPU core slot.
2) Interruptible Sleep (S): may occasionally change to interruptible state and then goes back to the previous uninterruptible state again
3) Uninterruptible Sleep (D) is a process which happens to be in a system call (kernel function) that cannot be interrupted by a signal. 
4) Stopped (T): a process becomes stopped when it receives the SIGSTOP signal (not unlike when you press <ctrl>+z in the shell, although <ctrl>+z sends a SIGTSTP instead). 
When stopped, the process execution is suspended and the only signals it will handle are SIGKILL and SIGCONT. The former will remove the process permanently, while the later will put the process back to the Running/Runnable state (like when you run fg or bg after pressing <ctrl>+z in the shell).
5) Zombie (Z): When a process finishes with exit() system call, its state needs to be "reaped" by its parent (calling wait()); in the meantime, the child process remains in zombie state (not alive nor dead).

2.Pstree command in Linux that shows the running processes as a tree which is a more convenient way to display the processes hierarchy and makes the output more visually appealing.

 ![img](/../master/images/task_5_3_1_1.png?raw=true "screenshot")


![img](/../master/images/task_5_3_1_2.png?raw=true "screenshot")


![img](/../master/images/task_5_3_1_3.png?raw=true "screenshot")

3.  Proc file system (procfs) is virtual file system created on fly when system boots and is dissolved at time of system shut down. 
It contains the useful information about the processes that are currently running, it is regarded as control and information centre for kernel.

![img](/../master/images/task_5_3_1_4.png?raw=true "screenshot")

4. 
![img](/../master/images/task_5_3_1_5.png?raw=true "screenshot")

![img](/../master/images/task_5_3_1_6.png?raw=true "screenshot")

5. 
![img](/../master/images/task_5_3_1_7.png?raw=true "screenshot")

6. User-space processes have its own virtual address space.

Kernel processes or threads do not have their own address space, they operate within kernel address space only.
And they may be started before the kernel has started any user process (e.g. init).

7. When using ps with the “u” flag (ps -u) you will see a column called STAT that displays the process’s status. 
Here is a list of the various process statuses and what they mean: D – Uninterruptible sleep (usually a critical system process, a process that cannot be killed without rebooting) 
R – Running or runable (on run queue) 
S – Interruptible sleep (waiting for an event to complete) 
T – Stopped, either by a job control signal or because it is being traced. 
Z – Defunct (“zombie”) process, terminated but not closed by the parent process that created it. 
Additional characters may be seen if in a BSD environment or when using the “stat” modifier with ps: 
W – has no resident pages < – high-priority process 
N – low-priority task L – has pages locked into memory (for real-time and custom IO).

 ![img](/../master/images/task_5_3_1_9.png?raw=true "screenshot")

8. 
![img](/../master/images/task_5_3_1_10.png?raw=true "screenshot")

9. Linux provides us a utility called ps for viewing information related with the processes on a system which stands as abbreviation for “Process Status”. 
ps command is used to list the currently running processes and their PIDs along with some other information depends on different options. 
It reads the process information from the virtual files in /proc file-system. /proc contains virtual files, this is the reason it’s referred as a virtual file system.

10. The top program provides a dynamic real-time view of a running system. 

11.

![img](/../master/images/task_5_3_1_11.png?raw=true "screenshot")

12.  Listed below is a brief index of commands within categories.
       Some commands appear more than once  --  their meaning or scope
       may vary depending on the context in which they are issued.

         4a. Global-Commands
               <Ent/Sp> ?, =, 0,
               A, B, d, E, e, g, h, H, I, k, q, r, s, W, X, Y, Z
         4b. Summary-Area-Commands
               C, l, t, m, 1, 2, 3, 4, !
         4c. Task-Area-Commands
               Appearance:  b, J, j, x, y, z
               Content:     c, f, F, o, O, S, u, U, V, v
               Size:        #, i, n
               Sorting:     <, >, f, F, R
         4d. Color-Mapping
               <Ret>, a, B, b, H, M, q, S, T, w, z, 0 - 7
         5b. Commands-for-Windows
               -, _, =, +, A, a, g, G, w
         5c. Scrolling-a-Window
               C, Up, Dn, Left, Right, PgUp, PgDn, Home, End
         5d. Searching-in-a-Window
               L, &

13. One of the most frequent reasons to use a tool like top is to find out which process is consuming the most resources. 
We can press the following keys to sort the list:
‘M’ to sort by memory usage
‘P’ to sort by CPU usage
‘N’ to sort by process ID
‘T’ to sort by the running time
By default, top displays all results in descending order. However, you can switch to ascending order by pressing ‘R’.
We can also sort the list with the -o switch. For example, if you want to sort processes by CPU usage, you can do so with:
top -o %CPU
Wr=e can sort the list by any of the attributes in the summary area in the same way.


14. Processes with a higher priority will be executed before those with a lower priority, while processes with the same priority are scheduled one after the next, repeatedly.
There are a total of 140 priorities and two distinct priority ranges implemented in Linux. 
The first one is a nice value (niceness) which ranges from -20 (highest priority value) to 19 (lowest priority value) and the default is 0, this is what we will uncover in this guide. 
The other is the real-time priority, which ranges from 1 to 99 by default, then 100 to 139 are meant for user-space.
To see the nice values of processes, we can use utilities such as ps, top or htop.

15. Once given top command, press r. Give PID value of the process you want to change the process value. 
Give renice value (from -20 to +19)
Nice value of -20 means highest priority value and +19 means lowest priority value. 0 is by default value.
Don't confuse renice value (-20 to +19) with process value (0 to 39)
relation between nice value and priority is :
PR = NI + 20

16. kill command in Linux (located in /bin/kill), is a built-in command which is used to terminate processes manually. 
kill command sends a signal to a process which terminates the process. 
If the user doesn’t specify any signal which is to be sent along with kill command then default TERM signal is sent that terminates the process.

![img](/../master/images/task_5_3_1_12.png?raw=true "screenshot")

17. The shell, bg (background), and fg (foreground) shell subcommands allow you to manipulate foreground and background tasks:
The jobs command displays a list of processes that are running in the background,
 fg <task_number> brings the process to the foreground,
 bg <task_number> - takes the process to the background.

Part 2.
SSH uses public-key cryptography to authenticate the remote computer and allow it to authenticate the user, if necessary.
There are several ways to use SSH; one is to use automatically generated public-private key pairs to simply encrypt a network connection, and then use password authentication to log on.
Another is to use a manually generated public-private key pair to perform the authentication, allowing users or programs to log in without having to specify a password. 
In this scenario, anyone can produce a matching pair of different keys (public and private). The public key is placed on all computers that must allow access to the owner of the matching private key (the owner keeps the private key secret). While authentication is based on the private key, the key itself is never transferred through the network during authentication. SSH only verifies whether the same person offering the public key also owns the matching private key. In all versions of SSH it is important to verify unknown public keys, i.e. associate the public keys with identities, before accepting them as valid. 
Accepting an attacker's public key without validation will authorize an unauthorized attacker as a valid user.

![img](/../master/images/task_5_3_2_1.png?raw=true "screenshot")

![img](/../master/images/task_5_3_2_2.png?raw=true "screenshot")


