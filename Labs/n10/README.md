# Lab. #10

**Topic:** Changing file owners and permissions in Linux. Special directories and files in Linux

**Purpose of the Work:**

- Gaining practical skills in working with the Bash shell.
- Familiarization with basic actions when changing file owners, file permissions
- Familiarization with special directories and files in Linux.

## Answers to questions about preparing

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

## Conclusion

We gained practical experience in Linux system administration using the Bash command-line interface. We worked together on tasks such as creating users and groups, modifying file and directory permissions, applying special permissions like setuid, setgid, and sticky bit, and exploring hard and symbolic links. These activities strengthened our understanding of Linux file security and system management.
