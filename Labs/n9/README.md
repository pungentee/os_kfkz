# Lab. #9

**Topic:** System and User Security in Linux. Creating Users and Groups

**Purpose of the Work:**

- To gain practical skills in working with the Bash command-line shell.
- To become familiar with the basic operations for creating new users and user groups.

## Answers to questions about preparing

### 1. Create a glossary of basic English terms related to command purposes and their parameters.

   - **root**: The superuser account with full administrative privileges.
   - **sudo**: A command allowing users to execute commands with root privileges.
   - **su**: A command to switch to another user account, typically root.
   - **/etc/passwd**: File storing user account information.
   - **/etc/group**: File defining group memberships.
   - **UID**: User ID, a unique identifier for a user.
   - **GID**: Group ID, a unique identifier for a group.
   - **groupadd**: Command to create a new group.
   - **groupmod**: Command to modify group attributes.
   - **id**: Command to display user and group information.
   - **who**: Command showing currently logged-in users.
   - **last**: Command displaying login and reboot history.
   - **grep**: Command to search for patterns in files.
   - **getent**: Command to retrieve entries from system databases (e.g., groups).

### 4. Answer the following questions based on the material:

   #### 4.1. Explain the concept of UPG and when it is appropriate to use them.
   
   A User Private Group (UPG) is a group automatically created with the same name as a new user, where the user is the only member. It is used to enhance file privacy by setting the user’s home directory to be owned by the user and their private group, with permissions restricting access to others. UPGs are appropriate in systems where individual user privacy is prioritized, such as multi-user environments, to prevent unauthorized access to user files.

   #### 4.2. Which commands can be used to create user groups? Provide examples.
   
   The `groupadd` command is used to create new groups. Examples:
     - `sudo groupadd developers`: Creates a group named "developers" with an automatically assigned GID.
     - `sudo groupadd -g 1001 sales`: Creates a group named "sales" with GID 1001.

   #### 4.3. Which commands can be used to modify user group settings? Provide examples.
   
   The `groupmod` command modifies group settings. Examples:
     - `sudo groupmod -n newname oldname`: Renames the group "oldname" to "newname".
     - `sudo groupmod -g 1002 developers`: Changes the GID of the "developers" group to 1002.

---

## Main task

### Task 2. Linux Commands Description Table

| Command Name                                      | Purpose and Functionality                                                                                                            |
| ------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| su -                                              | Switches to the root user with a full login shell, loading the root user's environment settings.                                     |
| id                                                | Displays the user ID (UID), group ID (GID), and group memberships of the current user.                                               |
| id root                                           | Shows the UID, GID, and group memberships for the root user.                                                                         |
| who                                               | Lists currently logged-in users, their login times, and terminal information.                                                        |
| w                                                 | Displays detailed information about currently logged-in users, including their activities and system uptime.                         |
| last                                              | Shows a history of user logins and logouts, including system reboots, from the system log.                                           |
| head /etc/shadow                                  | Displays the first 10 lines of the /etc/shadow file, which stores encrypted user passwords (requires root access).                   |
| sudo head /etc/shadow                             | Uses sudo to run the head command as root, displaying the first 10 lines of /etc/shadow.                                             |
| head /etc/passwd                                  | Displays the first 10 lines of the /etc/passwd file, which contains user account information.                                        |
| head -3 /etc/shadow                               | Shows the first 3 lines of the /etc/shadow file (requires root access).                                                              |
| grep sysadmin /etc/passwd                         | Searches the /etc/passwd file for entries containing the term "sysadmin," typically to find the sysadmin user's details.             |
| ls -l /etc/shadow                                 | Lists detailed information (permissions, owner, etc.) about the /etc/shadow file.                                                    |
| sudo head -3 /etc/shadow                          | Uses sudo to run the head command as root, displaying the first 3 lines of /etc/shadow.                                              |
| getent passwd sysadmin                            | Retrieves the /etc/passwd entry for the sysadmin user from the system's name service database.                                       |
| man 5 passwd                                      | Displays the manual page for the /etc/passwd file format (section 5 of the man pages).                                               |
| groupadd -r research                              | Creates a system group named "research" for system-related purposes (e.g., services).                                                |
| getent group research                             | Retrieves the /etc/group entry for the research group from the system's name service database.                                       |
| grep sales /etc/group                             | Searches the /etc/group file for entries containing the term "sales," typically to find the sales group's details.                   |
| groupmod -n clerks sales                          | Renames the group "sales" to "clerks" in the /etc/group file.                                                                        |
| groupmod -g 10003 clerks                          | Changes the group ID (GID) of the "clerks" group to 10003.                                                                           |
| grep clerks /etc/group                            | Searches the /etc/group file for entries containing the term "clerks" to verify group details.                                       |
| groupdel clerks                                   | Deletes the "clerks" group from the system.                                                                                          |
| useradd -D                                        | Displays the default settings for creating new users, as defined in /etc/default/useradd.                                            |
| useradd -D -f 30                                  | Sets the default number of days after password expiration before the account is disabled to 30.                                      |
| nano /etc/default/useradd                         | Opens the /etc/default/useradd file in the nano text editor to modify default user creation settings.                                |
| useradd -G research -c 'Linux Student' -m student | Creates a new user "student" with a home directory (-m), a comment "Linux Student" (-c), and adds them to the "research" group (-G). |
| grep student /etc/passwd                          | Searches the /etc/passwd file for the "student" user entry to verify its creation.                                                   |
| grep student /etc/group                           | Searches the /etc/group file for entries containing "student" to check group memberships.                                            |
| usermod -aG research sysadmin                     | Adds the "sysadmin" user to the "research" group without removing them from other groups (-aG).                                      |
| passwd student                                    | Changes the password for the "student" user interactively.                                                                           |
| userdel -r student                                | Deletes the "student" user and removes their home directory and mail spool (-r).                                                     |

### Task 3. Execute commands in GNU/Linux terminal

1.

![image](https://github.com/user-attachments/assets/421b507f-71e0-4744-b66a-81667d8cd8f2)

2. Compare outputs:
- `last` shows login history
- `w` shows current users and what they are doing
- `who` shows current users but less detail than `w`

![image](https://github.com/user-attachments/assets/b66d2395-ff51-4a45-84a5-0dc163755b5d)

3. Group ids: 1000, 1001, 1002.

![image](https://github.com/user-attachments/assets/c4af4b46-9eb5-4b74-9856-dad26608f041)

4.

![image](https://github.com/user-attachments/assets/7ba1d6f4-beea-468f-8164-04146a61faf2)

5.

![image](https://github.com/user-attachments/assets/a307a50e-cc1d-403f-838b-ba0494ad17f9)

6. Explanation:
- Each line shows the group name, GID, and members.
- You should see your created groups and assigned users.

![image](https://github.com/user-attachments/assets/80ced57f-883d-4770-b0db-cc8db8ac08d8)

7.

![image](https://github.com/user-attachments/assets/3b07a0cd-ed0d-4ee3-a932-ae04f3c7b082)

8.

![image](https://github.com/user-attachments/assets/c8e6477e-1823-42d8-ba51-d5b62e88d890)

9.

![image](https://github.com/user-attachments/assets/067ab8c0-db8c-43a9-9b8d-c18c08b76c3b)

10.

![image](https://github.com/user-attachments/assets/27b6bf10-5411-4e00-beb2-dca29593465e)

## Answers to control questions

### 1. Why are passwords not stored in plain text in configuration files?

Passwords are stored in hashed form (e.g., in `/etc/shadow`) to enhance security. If stored in plain text, unauthorized access to the file could expose passwords, compromising system security. Hashing ensures that even if the file is accessed, the actual passwords cannot be easily retrieved.

### 2. Why is it not recommended to perform daily operations using the root account?

Using the root account for daily tasks is risky because it has unrestricted access, increasing the chance of accidental damage (e.g., deleting critical files). Running programs like browsers as root can also expose the system to vulnerabilities, as malicious code would have full system access. Instead, use `sudo` for specific administrative tasks to limit exposure.

### 3. What is the difference between the mechanisms for obtaining elevated privileges with `su` and `sudo`?

`su` switches the user to another account (typically root) and maintains that session until logout, requiring the target user’s password. `sudo` allows executing specific commands with elevated privileges without switching accounts, using the user’s own password (if configured). `sudo` provides better auditing and granular control via `/etc/sudoers`.

### 4. Why is the root user’s home directory not located in `/home`?

The root user’s home directory is typically `/root` to isolate it from regular user directories in `/home`. This separation ensures root’s critical files (e.g., configuration files) are not affected by issues in `/home` (e.g., disk quotas or permissions) and enhances security by reducing accidental access by non-root users.

### 5. What is the purpose of the `getent` command?

The `getent` command retrieves entries from system databases (e.g., `/etc/passwd`, `/etc/group`) or network-based services (e.g., LDAP). It is used to query user, group, or other system information, unifying local and network-based data. Example: `getent group developers` shows group details.

### 6. How can a user’s password be changed?

The `passwd` command changes a user’s password. Example: `sudo passwd username` prompts for a new password for the specified user. For the current user, simply run `passwd`.

### 7. How can existing user groups be deleted? Will information about them remain in the system?

The `groupdel` command deletes a group. Example: `sudo groupdel developers`. If no users are assigned to the group, it is fully removed from `/etc/group`. However, files previously owned by the group’s GID may still reference the GID numerically, but no group name will be associated unless a new group is created with the same GID.

### 8. What is the purpose of the `chage` command?

The `chage` command manages user password aging policies, such as expiration dates or intervals for password changes. Example: `sudo chage -M 90 username` sets the maximum password validity to 90 days for the specified user.

### 9. Which parameters of the `usermod` command do you consider most commonly used?

Common `usermod` parameters include:
	`-aG groupname`: Adds a user to a supplementary group (e.g., `sudo usermod -aG developers username`).
    `-g groupname`: Changes the primary group (e.g., `sudo usermod -g users username`).
    `-d /new/home`: Changes the home directory (e.g., `sudo usermod -d /home/newdir username`).
    `-l newname`: Changes the username (e.g., `sudo usermod -l newuser olduser`).
    These are frequently used for managing group memberships, home directories, and account renaming.

## Conclusion

During this practical work, the student acquired hands-on experience managing users and groups within the Linux operating system using the Bash command-line interface. The tasks included creating new users and groups, assigning users to multiple groups, setting passwords, and removing users and groups from the system.
