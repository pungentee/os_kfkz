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

## Answers to control questions

## Conclusion

We gained practical experience in Linux system administration using the Bash command-line interface. We worked together on tasks such as creating users and groups, modifying file and directory permissions, applying special permissions like setuid, setgid, and sticky bit, and exploring hard and symbolic links. These activities strengthened our understanding of Linux file security and system management.
