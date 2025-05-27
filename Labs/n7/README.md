# Lab. #7

**Topic:** Creating scripted scenarios and determining the hardware configuration of the system

**Purpose of the Work:**

- Gaining practical skills in working with the Bash command shell.
- Familiarization with basic actions when working with scripting.

## Answers on prepear questions

### 1. Describe the concept of a scripted script in a command shell.

A scripting script in the shell is a file containing a sequence of shell commands that automate tasks. It is executed like a program, allowing users to streamline repetitive operations, manage system processes, and perform complex workflows efficiently. Scripts use shell syntax, variables, loops, and conditionals to interact with the operating system and other programs.

### 2. How are scripts created and edited, what do you need to do to run a script?

Scripts are created and edited using text editors like nano, vim, or gedit. A script file typically has a .sh extension and starts with a shebang (#!/bin/bash) to specify the shell interpreter. To run the script, it must be given execute permissions using chmod +x script.sh, and then executed with ./script.sh or bash script.sh.

### 3. What are the main components of a motherboard you know?

The main components of a motherboard include the CPU socket, RAM slots, chipset, expansion slots (PCIe, PCI), storage connectors (SATA, M.2), power connectors, input/output ports, BIOS/UEFI chip, and cooling system interfaces. These components work together to connect and manage the computer’s hardware.

### 4. Briefly describe for which devices the concepts of MBR and GPT are used?

MBR (Master Boot Record) and GPT (GUID Partition Table) are partitioning schemes used for storage devices like hard drives and SSDs. MBR is older, supports up to 2TB drives, and is compatible with BIOS-based systems. GPT is more advanced, supports larger drives, allows more partitions, and is required for UEFI-based systems.

### 5. What is the essence of the mount operation, what is it for?

Mounting is the process of making a storage device or file system accessible to the operating system. It assigns a directory (mount point) where users can access the device’s data. This operation is essential for using external drives, network shares, or additional partitions in a system.

## Main part

### Task 2. Work through all of the sample commands presented in the NDG Linux Essentials labs - Lab 11: Basic Scripting and Lab 12: Understanding Computer Hardware. Create a table to describe these commands

|**Command Name**|**Purpose and Functionality**|
|---|---|
|vi|Launches the vi text editor for editing files in the terminal. Requires knowledge of its commands to operate.|
|vi myfile|Opens the file myfile in the vi editor for editing or creates it if it doesn’t exist.|
|nano|Launches the nano text editor, which is simpler to use compared to vi.|
|gedit|Launches the graphical text editor gedit (typically in systems with a GUI, e.g., Ubuntu).|
|bash sample.sh|Executes the Bash script sample.sh in the current shell.|
|ls -l sample.sh|Note: ls seems to be a typo (likely from Windows’ dir). In Linux, ls -l sample.sh displays detailed info about the file sample.sh.|
|chmod a+x sample.sh|Grants execution permissions to the file sample.sh for all users (a = all, +x = add execute permission).|
|echo "Today is" date +%A``|Outputs the phrase "Today is" followed by the current day of the week (e.g., "Today is Friday").|
|cat sample.sh|Displays the contents of the file sample.sh in the terminal.|
|echo $PATH|Outputs the value of the $PATH environment variable, which lists directories searched for executable files.|
|mkdir bin|Creates a new directory named bin.|
|mv sample.sh bin|Moves the file sample.sh to the bin directory.|
|read age|Waits for user input and stores it in the variable age.|
|lscpu|Displays detailed information about the system’s CPU (architecture, number of cores, etc.).|
|head -n 20 /proc/cpuinfo|Outputs the first 20 lines of the /proc/cpuinfo file, which contains CPU information.|
|free -m|Shows memory usage information in megabytes (free, used memory, etc.).|
|lspci|Lists all PCI devices connected to the system (e.g., video cards, network adapters).|
|lsusb|Lists all USB devices connected to the system.|
|lsmod|Displays a list of loaded kernel modules in the operating system.|
|fdisk|A utility for managing disk partition tables (typically requires root privileges and arguments, e.g., fdisk /dev/sda).|

### Task 3

## Answers to control questions

1. `arch` shows only the CPU architecture. `lscpu` provides detailed information about the CPU.

2. `free -h`, `top`, `htop`, `vmstat`, `cat /proc/meminfo`.

3. Using `if`, `case`, `for`, `while`, `until`, and variable syntax like `$VAR`, `$(command)` in Bash scripts.

4. `lsusb`, `lspci`, `dmesg`, `usb-devices`, `udevadm info`, `hwinfo`, `lshw`, `lsblk`.

5. Creating, deleting, resizing, formatting, checking, copying partitions and file systems.

## Conclusion

During completion of this lab, various Linux commands were practiced to retrieve system information and hardware details efficiently.
