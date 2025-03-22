# Lab. #5

**Topic:** Introduction to File System Navigation and File/Directory Management Commands

**Purpose of the Work:**
- Gaining practical skills in working with the Bash command shell.
- Learning basic commands for navigating the file system.
- Becoming familiar with basic commands for managing files and directories.

## Anwers to preparision questions

1. Comparison of File Structures: Windows-like vs. Linux-like Systems

- Windows follows a drive-letter-based hierarchy (e.g., `C:\`, `D:\`), where each storage device or partition is assigned a separate letter. System files are usually stored in `C:\Windows\`, and user files are located in `C:\Users\Username\`.
- Linux follows a single-root hierarchy, where everything starts from `/` (the root directory). All devices, partitions, and even network shares are mounted within this hierarchy. Key system directories include `/bin`, `/etc`, `/home`, `/var`, and `/usr`.

2. Filesystem Hierarchy Standard (FHS)

FHS (Filesystem Hierarchy Standard) defines how files and directories should be structured in Unix-like operating systems (including Linux). It ensures consistency across distributions by specifying standard directories and their purposes.
Key FHS Directories:

`/` – Root directory, contains all other directories.

`/bin` – Essential binaries (e.g., `ls`, `cp`, `mv`).

`/etc` – System configuration files.

`/home` – User home directories.

`/var` – Variable data like logs (`/var/log`), mail, and cache.

`/usr` – User utilities and applications.

`/tmp` – Temporary files, cleared on reboot.

`/dev` – Device files (e.g., `/dev/sda` for a disk).

`/mnt` and `/media` – Mount points for removable drives.

3. Basic Linux Commands for File and Directory Management

| **Operation**         | **Command Example**                        |
|-----------------------|--------------------------------------------|
| **Create a file**     | `touch file.txt`                           |
| **Create a directory**| `mkdir newdir`                             |
| **Move/Rename**       | `mv file.txt /path/to/new/location/`       |
| **Copy a file**       | `cp file.txt /path/to/destination/`        |
| **Copy a directory**  | `cp -r dir1 dir2` (recursive copy)         |
| **Delete a file**     | `rm file.txt`                              |
| **Delete a directory**| `rm -r dir/` (recursive delete)            |

## Main task

### 3. Work in the terminal

Identify your current working directory

<img width="379" alt="Screenshot 2025-03-22 at 18 37 53" src="https://github.com/user-attachments/assets/8689037b-971b-4447-8ec0-41178a40ea05" />

Navigate to the root directory and determine your current working directory

<img width="248" alt="Screenshot 2025-03-22 at 18 38 34" src="https://github.com/user-attachments/assets/193b7c99-67e7-4cff-a2e8-2f54db50ec97" />

View the contents of the current directory in long format

<img width="838" alt="Screenshot 2025-03-22 at 18 39 31" src="https://github.com/user-attachments/assets/137323f7-88da-4ca4-ac98-473fc67ac613" />

Change to the `/usr/share` directory and identify your current working directory

<img width="302" alt="Screenshot 2025-03-22 at 18 40 23" src="https://github.com/user-attachments/assets/49ac69aa-5e57-4996-b239-556fb9ad82da" />

View the contents of the current directory, including hidden files

<img width="796" alt="Screenshot 2025-03-22 at 18 41 14" src="https://github.com/user-attachments/assets/d21ce34f-c8d3-450f-ad0c-b0c84b8f75c8" />

Change to the /etc
Browse contents of directory, displaying only files beginning with a letter of your name

<img width="162" alt="Screenshot 2025-03-22 at 18 42 29" src="https://github.com/user-attachments/assets/87be80e1-110b-4275-91f5-e61bf17e4ec4" />

Browse through the contents of this directory, but make sure that it displays only files with names that contain 6 letters

<img width="290" alt="Screenshot 2025-03-22 at 18 44 52" src="https://github.com/user-attachments/assets/7d73bb7b-4bc0-4709-b428-64c6d5d74d36" />

Browse contents showing only files whose names end with letters from your name

<img width="785" alt="Screenshot 2025-03-22 at 18 50 24" src="https://github.com/user-attachments/assets/4a974c5c-8396-4f44-8287-93a72f7be22a" />

Navigate to home directory and view contents in recursive reverse alphabetical format

<img width="442" alt="Screenshot 2025-03-22 at 19 02 29" src="https://github.com/user-attachments/assets/348d5c6d-b86a-4f2b-bb5a-f43ae70551dc" />

Create a directory with the name of your group

<img width="318" alt="Screenshot 2025-03-22 at 19 04 32" src="https://github.com/user-attachments/assets/9e6b352f-e4f0-42eb-8e15-807bd721c6e3" />

View updated contents of home directory using -r argument

<img width="859" alt="Screenshot 2025-03-22 at 19 05 20" src="https://github.com/user-attachments/assets/752f2346-72e2-47c5-9608-976e5f78ef2e" />

Change to your group directory and create an empty file

<img width="322" alt="Screenshot 2025-03-22 at 19 06 07" src="https://github.com/user-attachments/assets/e4a23285-c459-4d93-875e-8289c5be53c9" />

Create 3 directories for team members

<img width="482" alt="Screenshot 2025-03-22 at 19 07 04" src="https://github.com/user-attachments/assets/fec16ac8-b37e-4f22-98c1-58b4608a3bef" />

Go to first subdirectory and create an empty file

<img width="386" alt="Screenshot 2025-03-22 at 19 07 55" src="https://github.com/user-attachments/assets/c6a40418-d9c0-435c-8886-b02a1951a550" />

Add text to the file; View the contents of the file

<img width="598" alt="Screenshot 2025-03-22 at 19 08 38" src="https://github.com/user-attachments/assets/37e5a040-a63d-49f7-b674-4643ac3afecb" />

Copy and rename the file; View directory contents; View contents of the second file

<img width="555" alt="Screenshot 2025-03-22 at 19 09 37" src="https://github.com/user-attachments/assets/00f78d86-439a-4508-8a04-c16a34ab7a5c" />

Replace contents of the second file

<img width="696" alt="Screenshot 2025-03-22 at 19 10 40" src="https://github.com/user-attachments/assets/54d9faf3-f83a-43d2-abc8-1465f7fbaff8" />

Move name2 file to surname2 directory

<img width="462" alt="Screenshot 2025-03-22 at 19 11 57" src="https://github.com/user-attachments/assets/173f036a-5bc0-4b0d-bc1e-0de99adec201" />

Copy and rename first file to name3; Move name3 to surname3 directory

<img width="480" alt="Screenshot 2025-03-22 at 19 13 38" src="https://github.com/user-attachments/assets/c76e3346-95b1-475e-a810-e9a4044a57e6" />

Change to surname3 directory; View contents of name3;
Replace contents of name3; View updated contents

<img width="684" alt="Screenshot 2025-03-22 at 19 14 56" src="https://github.com/user-attachments/assets/ffd3e47a-8fcd-4daf-948c-29ed3e597b03" />

View your group directory and all its contents with color coding

<img width="583" alt="Screenshot 2025-03-22 at 19 15 48" src="https://github.com/user-attachments/assets/fc38889c-9b8c-4561-a1c9-6e0e1cd741e6" />

## Answers on questions

### 1. How to View the Path to the User's Home Directory Using echo

There are two ways to display the home directory path in the terminal:

```
echo $HOME
echo ~
```

Both commands return the absolute path to the user's home directory (e.g., `/home/username`).

### 2. Viewing the Root Directory Contents Without Changing the Current Directory

You can list the contents of the root directory (`/`) while staying in your home directory by running:

`ls /`

This command directly displays the files and directories located in `/` without requiring navigation.

### 3. How to Add Information to an Empty File in the Terminal

There are several ways to add content to an empty file:

Using echo:

```
echo "Some text" > file.txt
```

Using cat:

```
cat > file.txt
```

Using nano, vim, or vi:

```
nano file.txt
```

### 4. Copying and Deleting a Directory (Empty vs. Non-Empty)

Copying a Directory:

If the directory is empty or contains files, you must use -r (recursive):

```
cp -r directory_name destination/
```

Deleting a Directory:

```
rm -r directory_name
```

The `-r` flag ensures that all files and subdirectories inside are deleted recursively.  
