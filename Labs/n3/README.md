# Lab. #3

**Topic:** Introduction to basic CLI commands in Linux

**Purpose of the Work:**
Learn basic commands for working in CLI mode and basic text commands in terminal mode of various operating systems. Learn how to perform basic operations with files and directories, use commands to view, edit, and manage data through the command interface

## Main task

### 1.

### 2. Working with variables and aliases in the terminal

#### 2.1 Working with variables and aliases in the terminal

Created variables containing students' nicknames

![image](./attachments/1.png)

Created aliases for displaying birthdays calendars

![image](./attachments/2.png)

#### 2.2 Working with functions in the terminal

Created a function that displays students' names and years of birth

![image](./attachments/3.png)

#### 2.3 Working with quotes (Quoting) in the terminal

![image](./attachments/4.png)

![image](./attachments/5.png)

#### 2.4 Working with Control Statements in the terminal

Task 2.1 and 2.2 ware completed using the loop

![image](./attachments/6.png)

#### 2.5 Working with help commands (Man Pages) in the terminal

Manual was received for the command `uname`

![image](./attachments/7.png)

![image](./attachments/8.png)

Displaying information using different parameters of the `uname` command

![image](./attachments/9.png)


## Control questions

1. Bash commands fall into several types: built-in commands (like cd and echo), external executables (ls, grep), shell functions, and aliases. You can also use control operators (&&, ||, ;), pipelines (|), and redirections (>, <, >>). Job control commands manage background processes, while scripts execute multiple commands in sequence.

2. Environment variables are key-value pairs that store system and user-specific information used by the shell and applications. They define paths, user settings, and system behavior. You can view them in the terminal using the printenv, env, or export commands.

3. The $PS1 variable defines Bash's primary command prompt appearance. It can include text, special characters, and escape sequences like `\u` for the username or `\w` for the current directory. To view its contents, use the command echo $PS1 in the terminal.

4. You can change the value of $PS1 by assigning a new value, like PS1="MyPrompt> ". This immediately updates the Bash prompt (invitation line) before each command. To make the change permanent across sessions, add the assignment to `~/.bashrc` or `~/.bash_profile` and reload the file with source `~/.bashrc`.

5. Quotation marks in Bash control how the shell interprets special characters. Double quotes (") allow variable expansion and command substitution, while single quotes (') treat everything literally. Backticks (`) or $(...) execute commands and replace them with their output.

6. Control instructions in Bash manage the flow of execution in scripts and commands. They include conditional statements (if, case), loops (for, while, until), and branching/control operators (&&, ||, ;, &). These structures help automate decisions, repeat tasks, and handle logic efficiently.

7. The difference between $ and # at the end of the Bash prompt indicates the user type:
  - `$` appears for regular (non-root) users.
  - `#` appears for the root (superuser) account, which has administrative privileges.
In the image, [centos@localhost Desktop]$ means a regular user, while [root@localhost Desktop]# indicates the superuser, who can execute system-wide commands with full control.

8. The whereis command is used to find the binary, source, and manual pages of a command, while locate searches for files in the system using a pre-built database. The main difference is whereis looks in standard system directories, whereas locate provides fast results but may show outdated data if the database is not updated with updatedb.

## Conclusion

In the course of the laboratory work, the goal was achieved - to familiarize oneself with the basic commands of the CLI mode in Linux.The theoretical information on working with the shell command prompt was studied and practical skills in working with variables, aliases, functions, and control instructions in Bash were acquired. The acquired knowledge and skills are the basis for further studying Linux system administration and writing shell scripts.
