# Lab. #4

**Topic:** Linux commands for process management

**Purpose of the Work:**
- Gaining practical skills in working with the Bash command shell.
- Familiarization with basic commands for process management.

## Main task

### 2. Answer the questions:
1. How do I display the contents of the /proc directory? Where is it located and what is it for? Describe the information about its contents?

The `/proc` directory is a virtual filesystem used by the Linux kernel to provide real-time information about running processes. To display directory contents you simply have to use any of folder listener applications (`ls`, `ds`, `dir` etc). List of files and directories inside `/proc`:
    - `/proc/cpuinfo` – Information about the CPU.
    - `/proc/meminfo` – Memory usage details.
    - `/proc/<PID>/` – Process-specific details, where \<PID\> is the process ID.
    - `/proc/uptime` – System uptime.

2. How to display information about current user sessions. What command can I use to do this?

Command `who`

3. What actions can be performed in the terminal using the Ctrl + C, Ctrl + D, and Ctrl + Z combinations?

- `Ctrl + C` – Terminates the currently running process.
- `Ctrl + D` – Closes terminal session.
- `Ctrl + Z` – Suspends (pauses) the currently running process and moves it to the background.

4. What is the difference between a background process and a regular one? Where are they used?

A normal process runs in the foreground, taking control of the terminal until it finishes. But a background process runs in the background, allowing the user to continue working in the terminal. Background processes can be used to interact with the terminal while, for example, downloading a file.

5. Describe the following commands and explain what they do - jobs, bg, fg.

- `jobs` – Lists background jobs running in the current shell.
- `bg <ID>` – Resumes a suspended job in the background.
- `fg <ID>` – Brings a background job back to the foreground.

6. What command can I use to view information about background processes and tasks running in the system?

- `ps aux` – Shows all running processes.
- `top` or `htop` – Displays an interactive list of processes.
- Any other system process viewer application. Plasma System Monition, for example.

7. How do I pause a background process, resume it, and restart it if necessary?

- `kill -STOP <ID>` - to stop process execution
- `kill -CONT <ID>` - to continue process execution
- `kill -HUP <ID>` - to reload process

### 3.

Q## Launch the terminal, and in the command line, do the following to familiarize yourself with the processes

### Run the top command, analyze the result obtained in this command, and characterize the most active processes in the system;

![image](./Screenshot%202025-02-24%20at%2002.15.31.png)

### System Summary:
- **Uptime**: 0 minutes
- **Users**: 2
- **Load Average**: 0.45, 0.15, 0.05
- **Tasks**: 409 total (1 running, 408 sleeping)
- **CPU Usage**: 0.8% user, 0.6% system, 98.3% idle
- **Memory**: 1945.1 MiB total, 254.8 MiB free, 1170.7 MiB used
- **Swap**: 1945.0 MiB total, 1942.2 MiB free, 2.8 MiB used

### Most Active Processes:
1. **Xorg (PID 1207)**:
   - **CPU**: 5.8%
   - **Memory**: 114992 KiB
   - **Description**: X Window System server

2. **dnfdragora-upda (PID 1872)**:
   - **CPU**: 4.1%
   - **Memory**: 81620 KiB
   - **Description**: Package management or updates

3. **cinnamon-screen (PID 1886)**:
   - **CPU**: 2.4%
   - **Memory**: 46824 KiB
   - **Description**: Cinnamon desktop screen management

### pause the execution of the top command (use the key combination);
### display information about processes using the ps command;

![image](Screenshot%202025-02-24%20at%2002.19.30.png)

### Provide 5 examples using different ps command options (e.g., list only system processes, list processes of a specific user, list process tree, etc.). Describe what the options you have chosen do

- List All Processes
```bash
ps -e
```

-  List Processes of a Specific User
```bash
ps -u pungent+
```

- List Processes in a Tree Format
```bash
ps -e --forest
```

- List Processes with Detailed Information
```bash
ps -ef
```

List Processes with Custom Format
```bash
ps -eo pid,user,comm,%cpu,%mem
```

### See if you have any background processes running, which ones?

![image](Screenshot%202025-02-24%20at%2002.34.59.png)
### Resume execution of the suspended background process first in the foreground position, then pause it again, and then resume its execution in the background position

![image](Screenshot%202025-02-24%20at%2002.36.56.png)

![image](Screenshot%202025-02-24%20at%2002.36.57.png)

#### Terminate the work of this background process

![image](Screenshot%202025-02-24%20at%2002.39.13.png)

## Control questions

1. The /proc directory in Linux is a virtual filesystem that provides an interface to kernel and process information. It stores real-time system data, including details about running processes, hardware configuration, memory usage, CPU statistics, and kernel parameters. Since it is dynamically generated by the kernel, it does not contain actual files on disk but instead represents system state in a structured format. This allows users and programs to access and modify system information efficiently.

2. You can determine which of three processes is using the most memory by extracting their memory usage from /proc/<PID>/status or using ps -o pid,%mem --sort=-%mem to get memory percentages. By comparing their resident memory (RSS) values, you can identify the highest consumer. To find the percentage of total memory, divide the process's memory usage by the system's total memory, which can be obtained from /proc/meminfo, and multiply by 100. This can be done dynamically using a script in Bash or Python for continuous monitoring.

3. The hierarchy of parent processes in Linux follows a tree structure, starting from init or systemd as the root. Each process has a parent process, except for the root process, and can spawn child processes. This relationship can be observed using pstree for a visual representation or by checking the PPID field in /proc/<PID>/status or ps -e -o pid,ppid,cmd. When a parent process terminates, its child processes may be adopted by init or systemd. This structure helps manage processes efficiently and ensures system stability.

4. The top command provides a real-time, continuously updated view of system processes, showing CPU and memory usage dynamically. It allows interaction, such as sorting or killing processes directly. The ps command, on the other hand, captures a snapshot of processes at a specific moment, displaying detailed information about selected processes without real-time updates. While top is useful for monitoring system performance live, ps is better suited for static analysis and scripting.

5. htop enhances top by providing a more user-friendly, interactive interface with color-coded output and better readability. It allows vertical and horizontal scrolling to view all processes and their details, supports searching and filtering, and offers easier process management with function key shortcuts. Unlike top, htop displays system resource usage as graphical bars, making it more intuitive for monitoring CPU, memory, and swap utilization.

6. A mobile OS for monitoring processes includes a process manager, which tracks running applications and background services, displaying their CPU and memory usage. A kernel scheduler manages process execution, ensuring efficient resource allocation. System logs and debugging tools capture process events and errors, aiding in diagnostics. User-facing task managers provide options to view, stop, or prioritize applications. Security modules monitor unauthorized or malicious processes, enforcing system integrity. These components work together to maintain performance, stability, and security.

7. Most mobile operating systems, like Android and iOS, have limited built-in terminal access for process control, but Android supports it through ADB (Android Debug Bridge). Using ADB, users can list processes with ps, monitor resource usage with top, and manage processes by killing or modifying them with kill or renice. Rooted Android devices provide full terminal control via shell access, allowing deeper process management. iOS, however, restricts terminal access unless jailbroken, where SSH or local terminal apps enable similar functionality.

8. Yes, third-party apps can enhance process management and monitoring on mobile phones. On Android, apps like Termux provide a Linux terminal for command-line process control, while SystemPanel 2 and CPU Monitor offer detailed resource tracking and process management. Greenify helps optimize background apps to improve performance and battery life. For rooted devices, Tasker automates process handling, and Kernel Adiutor fine-tunes system parameters. On iOS, third-party monitoring is limited due to restrictions, but jailbroken devices can use tools like Filza and NewTerm for process control.

## Conclusion
