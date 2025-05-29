# Lab. #9

**Topic:** System and User Security in Linux. Creating Users and Groups

**Purpose of the Work:**

- To gain practical skills in working with the Bash command-line shell.
- To become familiar with the basic operations for creating new users and user groups.

## Answers to questions about preparing

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

## Conclusion

During this practical work, the student acquired hands-on experience managing users and groups within the Linux operating system using the Bash command-line interface. The tasks included creating new users and groups, assigning users to multiple groups, setting passwords, and removing users and groups from the system.
