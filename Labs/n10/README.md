# Lab. #10

**Topic:** Changing file owners and permissions in Linux. Special directories and files in Linux

**Purpose of the Work:**

- Gaining practical skills in working with the Bash shell.
- Familiarization with basic actions when changing file owners, file permissions
- Familiarization with special directories and files in Linux.

## Answers to questions about preparing

### 1. Dictionary of Basic English Terms
Below is a concise dictionary of key English terms related to Linux file ownership, permissions, and commands, based on the provided theoretical information:

- **File Ownership**: The association of a file with a user (UID) and a group (GID).
- **UID (User ID)**: A numeric identifier for a user in the system.
- **GID (Group ID)**: A numeric identifier for a group in the system.
- **Permissions**: Access rights (read, write, execute) for a file or directory.
- **setuid**: A special permission allowing a program to run with the file owner's privileges.
- **setgid**: A special permission allowing a program to run with the group owner's privileges or setting group ownership on files in a directory.
- **Sticky Bit**: A permission restricting file deletion in a directory to the file's owner.
- **id**: Command to display user and group identity information.
- **newgrp**: Command to change the current primary group.
- **chmod**: Command to change file or directory permissions.
- **chown**: Command to change file or directory ownership.
- **ls -l**: Command to list files with detailed ownership and permission information.
- **touch**: Command to create an empty file.
- **groups**: Command to list groups a user belongs to.

### 4. Answers to Preliminary Questions

#### 4.1. What is the purpose of the id command?  
The `id` command displays the current user's identity information, including the user ID (UID), primary group ID (GID), and supplemental group memberships, shown as both names and numeric IDs.

#### 4.2. How can you view the access rights of a file’s owner?  
Use the `ls -l` command to list files in long format. The first part of the permission string (e.g., `rwxr-xr-x`) shows the owner’s permissions: the first three characters (rwx) indicate read, write, and execute rights for the owner.

#### 4.3. How can you change the group owner of a file?  
To change the group owner, use the `chown` command with the `:group_name` syntax, e.g., `chown :group_name file`. Alternatively, use `chgrp group_name file`. To change both user and group, use `chown user:group file`.

#### 4.4. How can you view the type of the current file in the terminal? Provide examples for different file types.  
Use the `ls -l` command, where the first character in the permission string indicates the file type:
- **Regular file**: `-` (e.g., `-rw-r--r-- file.txt`)
- **Directory**: `d` (e.g., `drwxr-xr-x dir`)
- **Symbolic link**: `l` (e.g., `lrwxrwxrwx link -> target`)
- **Block device**: `b` (e.g., `brw-rw---- disk`)
- **Character device**: `c` (e.g., `crw-rw---- tty`)
- **Named pipe**: `p` (e.g., `prw-r--r-- pipe`)
- **Socket**: `s` (e.g., `srw-rw-rw- socket`)

#### 4.5. What are the setuid and setgid permissions used for?  
- **setuid**: When set on an executable, it allows the program to run with the file owner’s privileges (e.g., `passwd` runs as root to modify `/etc/shadow`). Indicated by `s` in the owner’s execute position (e.g., `-rwsr-xr-x`).
- **setgid**: On an executable, it runs with the group owner’s privileges (e.g., `/usr/bin/wall` accesses tty group files). On a directory, it ensures new files inherit the directory’s group ownership. Indicated by `s` in the group’s execute position (e.g., `drwxrwsr-x`).

#### 4.6. What is the purpose of the “sticky bit” in the system? Provide examples of when it is appropriate to use.  
The sticky bit restricts file deletion in a directory to the file’s owner, even if others have write permissions. It is indicated by `t` in the others’ execute position (e.g., `drwxrwxrwt`).  
**Examples**: Commonly used on `/tmp`, where multiple users can create files, but only the file owner can delete their files. Another example is a shared project directory where users can create files but cannot delete others’ files.

---

## Main task

### Task 2. Linux Commands Description Table

|Command Name|Purpose and Functionality|
|---|---|
|cd /tmp|Changes the current working directory to /tmp, a temporary directory for storing transient files.|
|mkdir priv-dir pub-dir|Creates two directories named priv-dir and pub-dir in the current directory.|
|touch priv-dir/priv-file|Creates an empty file named priv-file in the priv-dir directory, or updates its timestamp if it exists.|
|touch pub-dir/pub-file|Creates an empty file named pub-file in the pub-dir directory, or updates its timestamp if it exists.|
|ls -l priv-dir|Lists the contents of the priv-dir directory in long format, showing permissions, owner, and other details.|
|ls -l pub-dir|Lists the contents of the pub-dir directory in long format, showing permissions, owner, and other details.|
|ls -la|Lists all files (including hidden ones) in the current directory in long format.|
|ls -ld priv-dir/|Lists details of the priv-dir directory itself (not its contents) in long format.|
|chmod o-rx priv-dir/|Removes read and execute permissions for others (non-owner, non-group) on the priv-dir directory.|
|ls -ld pub-dir/|Lists details of the pub-dir directory itself in long format.|
|chmod o+w pub-dir/|Grants write permission for others on the pub-dir directory.|
|ls -l priv-dir/priv-file|Lists details of the priv-file in the priv-dir directory in long format.|
|chmod g-rw,o-r priv-dir/priv-file|Removes read and write permissions for the group and read permission for others on priv-file.|
|ls -l pub-dir/pub-file|Lists details of the pub-file in the pub-dir directory in long format.|
|chmod a=rw pub-dir/pub-file|Sets read and write permissions for all (owner, group, others) on pub-file, removing other permissions.|
|echo "date" > test.sh|Writes the string "date" to a file named test.sh, creating or overwriting it.|
|./test.sh|Attempts to execute test.sh as a script in the current directory (requires execute permission).|
|ls -l test.sh|Lists details of the test.sh file in long format, showing permissions and ownership.|
|chmod u+x test.sh|Grants execute permission to the owner of test.sh.|
|stat test.sh|Displays detailed status information about test.sh, including permissions, ownership, and timestamps.|
|chmod 775 test.sh|Sets test.sh permissions to rwxrwxr-x (owner and group have read/write/execute, others have read/execute).|
|su -|Switches to the root user with a full login shell, loading the root user's environment.|
|chown root:root pub-dir|Changes the owner and group of pub-dir to root.|
|chown bin pub-dir/pub-file|Changes the owner of pub-file to the user bin, leaving the group unchanged.|
|chgrp -R users priv-dir|Recursively changes the group of priv-dir and its contents to the users group.|
|ls -ld /tmp|Lists details of the /tmp directory itself in long format.|
|ls -ld /var/tmp|Lists details of the /var/tmp directory itself in long format.|
|ls -l /etc/shadow|Lists details of the /etc/shadow file, which stores encrypted user passwords (requires root access).|
|ls -l /usr/bin/passwd|Lists details of the /usr/bin/passwd executable, used for changing user passwords.|
|ls -l /usr/bin/wall|Lists details of the /usr/bin/wall executable, used to broadcast messages to all users.|
|cd|Changes the current working directory to the user's home directory.|
|echo "data" > source|Writes the string "data" to a file named source, creating or overwriting it.|
|ls -li source|Lists details of the source file, including its inode number, in long format.|
|ln source hardlink|Creates a hard link named hardlink pointing to the same inode as source.|
|ls -li source hardlink|Lists details of source and hardlink, including their inode numbers, to confirm they share the same inode.|
|ln hardlink hardlinktwo|Creates another hard link named hardlinktwo pointing to the same inode as source and hardlink.|
|ls -li hardlink hardlinktwo source|Lists details of hardlink, hardlinktwo, and source, showing they share the same inode.|
|rm hardlinktwo|Deletes the hardlinktwo file, leaving the original data and other hard links intact.|
|ls -li source hardlink|Lists details of source and hardlink, confirming they still share the same inode.|
|rm hardlink|Deletes the hardlink file, leaving the source file intact.|
|ls -li source|Lists details of the source file, including its inode number.|
|ln -s source softlink|Creates a symbolic (soft) link named softlink pointing to the source file.|
|ls -li source softlink|Lists details of source and softlink, showing different inodes and the symbolic link's target.|
|ln -s /proc crossdir|Creates a symbolic link named crossdir pointing to the /proc directory.|
|ls -l crossdir|Lists details of the crossdir symbolic link, showing it points to /proc.|

### Task 3

#### 1. Create 3 New Users
```bash
sudo useradd user1 && \
sudo useradd user2 && \
sudo useradd user3
```

#### 2. Create a New Group and Add 2 Users to It
```bash
sudo groupadd mygroup && \
sudo usermod -aG mygroup user1 && \
sudo usermod -aG mygroup user2
```

![Screenshot_20250612_124602](https://github.com/user-attachments/assets/ca02d6d3-cb57-42e0-b5ea-0aaa5df8f530)

#### 3. Create a Script File with Full Owner Permissions
```bash
echo -e "#!/bin/bash\necho Hello" > myscript.sh && \
chmod 700 myscript.sh
```

#### 4. Set File Permissions for Group and Others
```bash
chmod 750 myscript.sh && \
sudo chown user1:mygroup myscript.sh
```
![Screenshot_20250612_124806](https://github.com/user-attachments/assets/172e9f72-5dfa-476e-a02a-2567fe5f386d)

#### 5. Create Directories with Specific Access Rules

##### Directory for All Users (Read/Write/Execute)
```bash
mkdir shared_dir && \
chmod 777 shared_dir
```

##### Directory for Owner Only
```bash
mkdir private_dir && \
chmod 700 private_dir
```

##### Directory for Group Users (Read + Execute Only)
```bash
mkdir group_read_only && \
sudo chown user1:mygroup group_read_only && \
chmod 750 group_read_only
```

![Screenshot_20250612_125003](https://github.com/user-attachments/assets/1780c343-7b51-4b13-8cc5-a12677c6495d)

#### 6. Create an Empty File and Test chmod Behavior
```bash
touch emptyfile && \
chmod 000 emptyfile
```

Test with numeric permissions:
```bash
chmod 4 emptyfile && \
ls -l emptyfile && \
chmod 44 emptyfile && \
ls -l emptyfile
```

![Screenshot_20250612_125030](https://github.com/user-attachments/assets/159465f3-8a7f-4ad0-83f6-533aecdbe762)

#### 7. Create a Group-Owned Directory with setgid Bit
```bash
mkdir groupdir && \
sudo chown :mygroup groupdir && \
chmod 2770 groupdir
```

![Screenshot_20250612_125107](https://github.com/user-attachments/assets/5b0cec6b-3f51-4233-9915-1c840d5660a0)

#### 8. For Each User: Create a File, Hard Link, and Symbolic Link

##### As `user1`:
```bash
sudo -u user1 bash -c "cd ~ && \
touch file1 && \
ln file1 file1_hard && \
ln -s file1 file1_symlink"
```

##### As `user2`:
```bash
sudo -u user2 bash -c "cd ~ && \
touch file2 && \
ln file2 file2_hard && \
ln -s file2 file2_symlink"
```

##### As `user3`:
```bash
sudo -u user3 bash -c "cd ~ && \
touch file3 && \
ln file3 file3_hard && \
ln -s file3 file3_symlink"
```

![Screenshot_20250612_125154](https://github.com/user-attachments/assets/10d5c7cc-db05-4f76-8262-bc24c8908619)

#### 9. Test Access and Deletion by Other Users

##### Try Reading Another Users File
```bash
sudo -u user2 cat /home/user1/file1
```

##### Try Deleting Another User’s File

```bash
sudo -u user2 rm /home/user1/file1
```

![Screenshot_20250612_125307](https://github.com/user-attachments/assets/74449a5b-4904-46dd-b97d-45a83207c050)

## Answers to control questions

### 1. Provide examples of changing access rights using the symbolic method.  
- Add read permission for the owner: `chmod u+r file.txt`
- Remove write permission for the group: `chmod g-w file.txt`
- Set execute permission for others: `chmod o+x file.txt`
- Add setuid permission: `chmod u+s program`
- Remove sticky bit from a directory: `chmod o-t dir`

### 2. Provide examples of changing access rights using the numeric (octal) method.  
- Set read/write/execute for owner, read/execute for group, read for others: `chmod 754 file.txt`
- Set read/write for owner, read for group, no permissions for others: `chmod 640 file.txt`
- Add setuid to existing permissions (e.g., 755): `chmod 4755 program`
- Set sticky bit on a directory (e.g., 777): `chmod 1777 dir`
- Remove all permissions: `chmod 000 file.txt`

### 3. What is the purpose of the umask command?  
The `umask` command sets the default permission mask for new files and directories, subtracted from the default permissions (666 for files, 777 for directories). For example, a umask of `022` results in new files with permissions `644` (666 - 022) and directories with `755` (777 - 022).

### 4. Compare hard links and symbolic links.  
- Hard Link:
  - Points directly to the inode of the original file.
  - Cannot link to directories or files on different filesystems.
  - Deleting the original file does not affect the hard link (data remains accessible).
  - Created with: `ln original_file hard_link`
- Symbolic Link:
  - Points to the file’s path, not the inode.
  - Can link to directories or files across filesystems.
  - Becomes invalid if the original file is deleted (broken link).
  - Created with: `ln -s original_file symbolic_link`

### 5. Can you execute a file that has execute permissions but no read permissions (--x)? Explain.  
Yes, a file with `--x` permissions can be executed if the user has access to the file’s contents (e.g., via a script or binary already loaded in memory). However, you cannot read or modify the file’s contents. For scripts, execution may fail if the interpreter (e.g., bash) needs to read the file, but for compiled binaries, execution typically succeeds.

### 6. If we change access rights and permissions in the current session, will they be preserved in the next session?  
Yes, changes to file permissions (e.g., via `chmod` or `chown`) are persistent across sessions because they are stored in the filesystem. However, temporary changes like switching the primary group with `newgrp` are session-specific and revert when the shell exits.

### 7. Is there a pattern that the system uses for permissions when creating new files? How can you change the default permissions?  
Yes, new files are created with default permissions of `666` (rw-rw-rw-) and directories with `777` (rwxrwxrwx), modified by the user’s `umask`. For example, a umask of `022` results in `644` for files and `755` for directories. To change default permissions, set a new umask value, e.g., `umask 027` in the user’s shell configuration file (e.g., `~/.bashrc`).

### 8. How can you create a hard link? In what situations is it appropriate to use them?  
- **Creation**: `ln original_file hard_link`
- **Use Cases**: Hard links are useful for creating multiple references to the same file within the same filesystem, such as backups or maintaining multiple access points to critical data. They ensure data persistence even if the original filename is deleted, as long as one hard link remains.

### 9. How can you create a symbolic link? In what situations is it appropriate to use them?  
- **Creation**: `ln -s original_file symbolic_link`
- **Use Cases**: Symbolic links are ideal for linking to files or directories across different filesystems, creating shortcuts, or referencing frequently updated files (e.g., linking `/var/www/html` to a website’s root directory). They are commonly used in software installations to point to the latest version of a directory.

### 10. Imagine a program needs to create a one-time file that will never be used again after the program closes. What is the correct directory for creating this file?  
The correct directory is `/tmp`. It is designed for temporary files that can be created by any user or process. Files in `/tmp` are often automatically deleted on reboot or by system cleanup processes, making it ideal for one-time temporary files.

### 11. There is an original file with and both a symbolic link and a hard link to it. What happens if you delete:
- Original File:  
  - The symbolic link becomes invalid (broken) and points to a non-existent file.  
  - The hard link remains valid, as it points to the inode, and the file’s data is still accessible until all hard links are deleted.  
- Symbolic Link:  
  - No effect on the original file or hard link, as the symbolic link is just a pointer.  
- Hard Link:  
  - The original file remains unaffected as long as at least one link (original or another hard link) exists. The file’s data is only deleted when all hard links are removed, and the inode references are gone.  

## Conclusion

We gained practical experience in Linux system administration using the Bash command-line interface. We worked together on tasks such as creating users and groups, modifying file and directory permissions, applying special permissions like setuid, setgid, and sticky bit, and exploring hard and symbolic links. These activities strengthened our understanding of Linux file security and system management.
