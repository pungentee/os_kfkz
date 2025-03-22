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
