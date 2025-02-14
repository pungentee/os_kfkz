### 1. Give examples of Linux server applications for database servers, messaging servers, and file sharing.

For database servers, common Linux applications include MySQL, PostgreSQL, and MariaDB for relational databases, while MongoDB and Redis handle NoSQL and caching needs. Messaging servers often use Postfix or Exim for email, with Dovecot managing mailbox access, and RabbitMQ or Kafka handling message queuing. For file sharing, Samba enables Windows compatibility, NFS supports Linux/Unix systems, and solutions like Nextcloud provide cloud-based storage.

### 2. Compare the Bourne, C, Bourne Again (Bash) shells, the tcsh, the Korn shell (Ksh), and zsh.

The Bourne shell (sh) is a simple, widely compatible scripting shell. The C shell (csh) introduced C-like syntax and job control but had weaker scripting. Bash improved on sh with better interactivity and scripting. Tcsh enhanced csh with auto-completion and editing. The Korn shell (ksh) combined sh’s reliability with advanced features. Zsh is the most feature-rich, offering customization, auto-completion, and scripting improvements.

### 3. What is a package manager for? What package managers do you know in Linux?

A package manager automates the installation, updating, and removal of software on a Linux system, handling dependencies to ensure smooth operation. Common Linux package managers include APT (Debian, Ubuntu), DNF/YUM (Fedora, RHEL), Zypper (openSUSE), and Pacman (Arch Linux). There are also universal package managers like Flatpak, Snap, and AppImage for cross-distribution applications.

### 4. What security features are used in Linux?

There're a lot
- User and Group Permissions – Controls access to files and directories using read, write, and execute permissions
- Mandatory Access Control (MAC) – Systems like SELinux and AppArmor enforce stricter security policies
- Pluggable Authentication Modules (PAM) – Manages authentication, authorization, and password policies
- Firewall (iptables/nftables) – Controls network traffic and prevents unauthorized access
- File Encryption – Tools like LUKS and eCryptfs provide disk encryption
- Kernel Security Modules – Prevents exploits and enforces security policies (SELinux, AppArmor)
- Address Space Layout Randomization (ASLR) – Protects against memory-based attacks
- Audit Framework – Monitors system activity and logs security events
- Chroot and Namespaces – Isolate processes for security (used in containers)

### 5. Why has the use of virtualization become so relevant now?

Virtualization has become crucial in today's computing landscape primarily due to the increasing demands for efficient resource use and flexible computing solutions. Organizations can now run multiple virtual environments on single physical servers, dramatically cutting costs and improving hardware utilization. This technology has become especially vital with the rise of cloud computing and remote work, where businesses need to provide secure, accessible computing environments regardless of physical location. It's also become indispensable for software development and disaster recovery, while helping organizations reduce their environmental impact through more efficient use of computing resources. The ability to create, move, and manage virtual environments has fundamentally transformed how modern computing infrastructure is deployed and managed.

### 6. How do you understand the concept of containerization?

Containerization is a lightweight virtualization approach that bundles an application with everything it needs to run. Unlike full virtual machines that include an entire operating system, containers share the host system's OS kernel and carry only essential components. It's similar to shipping containers - standardized boxes that can transport any cargo consistently across different vessels. This technology gained widespread adoption through platforms like Docker, primarily because containers are both portable and efficient. Since each container holds all necessary dependencies, applications run consistently across any environment, solving many traditional deployment challenges developers face.

### 7. What are the advantages/disadvantages of using open source software?

Open source software offers significant benefits through its transparency and community-driven development, allowing organizations to inspect, modify, and improve code while avoiding licensing fees. The global developer community often provides rapid security fixes and continuous improvements. However, this comes with certain drawbacks - organizations may struggle with inconsistent technical support, documentation quality, and the risk of project abandonment. While the software itself is free, companies need to invest in skilled personnel who can effectively implement and maintain it. The decision between open source and proprietary solutions ultimately depends on an organization's specific needs and technical capabilities.

### 8. How many active virtual consoles (terminals) can be present in a Linux process by default. How to call them and switch between them? What are some examples?

In a typical Linux system, there are 6 virtual consoles (tty1 through tty6) available by default, with tty7 often reserved for the graphical interface (X server or Wayland).

You can access these virtual consoles using `Ctrl + Alt + F1 through F6` or using the command `chvt` followed by the terminal number (e.g., `chvt 2`)

To see which virtual console you're currently using, you can use the tty command. For example:

```bash
$ tty
/dev/tty2
```

This feature proves especially useful when troubleshooting system issues – for instance, if the graphical interface freezes, you can switch to a text console, log in, and resolve the problem. 

### 9. Which virtual console (terminal) performs the function of the graphical interface?

On most Linux distributions, the graphical session resides on virtual console 7 (TTY7) by default. It might be otherwise, however, depending on system configuration. Virtual consoles may be switched between using Ctrl + Alt + F1 to Ctrl + Alt + F6 for the text consoles and Ctrl + Alt + F7 (sometimes F2-F8) for the graphical session.

### 10. Is it possible to log in multiple times under the same system username in Linux? What advantages does this provide?

Yes, Linux does allow simultaneous logins using the same username, whether through multiple virtual consoles, SSH sessions, or GUI sessions.

Advantages:
- Allows a user to run multiple tasks in separate sessions without interfering with each other.
- Easy for remote use, as it enables users to log on from different places.
- Allows multitasking in server administration and development environments.

But some of GUI DM doesn't support logging in single user (usually X11/Xorg ones).
