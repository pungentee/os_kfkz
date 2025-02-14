# Lab. #2

**Topic:** Introduction to the Interface and Features of Linux OS

**Purpose of the Work:**
Gaining practical skills in working with Linux OS and mobile OS environments – including their graphical interface, logging in and out of the system, familiarizing with the desktop structure, and learning the basic operations and settings for working within the system.

## Main task

### 1. Working in Graphical Mode in Linux OS

#### 1.1 Choose a Graphical Shell for a Linux OS to Review. Examine the structure of the user workspace and describe its main components.

- **Main menu.** The main menu in KDE, called Kickoff, is in the bottom-left corner by default. It provides access to installed applications, system settings, and recent files. Users can browse applications by category or use the search function to find what they need quickly. KDE also offers alternatives like the Application Dashboard, which presents a full-screen launcher, and Simple Menu, which offers a more minimalistic approach.
- **Quick access.** KDE uses a taskbar to display open applications, allowing users to switch between them easily. It supports grouping, window previews, and pinning frequently used applications.
- **Search.** Main search system is KRunner. Activated by pressing Alt + Space, KRunner allows users to launch applications, open files, perform calculations, search online, and execute commands.
- **Virtual desktops creation.** KDE supports multiple virtual desktops, allowing users to organize their workspace efficiently. Users can switch between them using keyboard shortcuts (Ctrl + F1 to Ctrl + F4 by default) or via the desktop switcher widget. Or by using Activities.

#### 1.2 Applications execution

- Via quick access

![image](https://github.com/user-attachments/assets/e39c6cca-0b0c-4412-8dee-4bfc375eab1b)

- Via search

![image](https://github.com/user-attachments/assets/c41cad05-707b-4854-a202-67b327bba3fb)

- Via widget

![image](https://github.com/user-attachments/assets/e8792430-0860-4bd5-9f7b-755f1dd0e8ce)

#### 1.3 Exit and shutdown

- Changing user to `root`

![image](https://github.com/user-attachments/assets/1ff3c61b-4a83-4cbb-b8d0-32aa9a98b893)

- System restart and shutdown (via main menu)

![image](https://github.com/user-attachments/assets/0384d88b-109d-439f-b0e3-703050b1eeeb)

### 2. Working in a mobile OS environment

#### 1. Describe the main menu of your mobile OS, what kind of graphical interface does it use?

The main menu of iOS is the Home Screen, which features a grid-based graphical interface. It uses a touch-friendly UI with app icons arranged in rows and columns. The interface is gesture-driven, allowing users to swipe between pages, tap icons to open apps, and use drag-and-drop for customization. The Dock at the bottom provides quick access to frequently used apps. iOS uses a flat design with smooth animations and transparency effects, following Apple’s Human Interface Guidelines.

#### 2. Describe the settings menu for the components of a mobile phone.

The Settings menu in iOS provides access to various system and hardware configurations. It has a list-based interface with categorized sections. Key components include:
- Wi-Fi & Bluetooth – Manage wireless connections
- Cellular – Control mobile data usage
- Sounds & Haptics – Adjust volume, ringtones, and vibration
- Display & Brightness – Configure screen brightness, text size, and dark mode
- Battery – View battery usage and enable Low Power Mode
- Privacy & Security – Manage app permissions and data access
- General – System settings, software updates, and device information
Each section has submenus for detailed customization

#### 3. Use keyboard shortcuts to perform special actions.

On iOS, you can use keyboard shortcuts when a physical keyboard is connected (e.g., via Bluetooth or Magic Keyboard). Some common shortcuts include:
- ⌘ + H – Go to the Home Screen
- ⌘ + Space – Open Spotlight search
- ⌘ + Tab – Switch between open apps
- ⌘ + Shift + 3 – Take a screenshot
- ⌘ + Shift + 4 – Take a screenshot and open Markup
- ⌘ + Option + D – Show or hide the Dock
Many apps, like Safari and Notes, support additional shortcuts for navigation and text editing

#### 4. Log in and shut down the device. Features of the battery power settings

To log in to an iOS device, press the Side button or the Home button on older models and use Face ID, Touch ID, or enter a passcode. To shut down the device, go to Settings, then General, and select Shut Down, or hold the Side button along with a Volume button until the power slider appears, then slide to turn off.

Battery power settings in iOS include options for monitoring battery health and charging, enabling Low Power Mode to reduce background activity, and viewing battery usage by app. The system also features Optimized Battery Charging, which slows down charging at night to extend battery lifespan. Additionally, users can manage Background App Refresh to control which apps update in the background, helping to save power.

## Control questions

### 1. Give examples of Linux server applications for database servers, messaging servers, and file sharing.

For database servers, common Linux applications include MySQL, PostgreSQL, and MariaDB for relational databases, while MongoDB and Redis handle NoSQL and caching needs. Messaging servers often use Postfix or Exim for email, with Dovecot managing mailbox access, and RabbitMQ or Kafka handling message queuing. For file sharing, Samba enables Windows compatibility, NFS supports Linux/Unix systems, and solutions like Nextcloud provide cloud-based storage.

### 2.	Compare the Bourne, C, Bourne Again (Bash) shells, the tcsh, the Korn shell (Ksh), and zsh

The Bourne shell (sh) is a simple, widely compatible scripting shell. The C shell (csh) introduced C-like syntax and job control but had weaker scripting. Bash improved on sh with better interactivity and scripting. Tcsh enhanced csh with auto-completion and editing. The Korn shell (ksh) combined sh’s reliability with advanced features. Zsh is the most feature-rich, offering customization, auto-completion, and scripting improvements.

### 3.	What is a package manager for? What package managers do you know in Linux?

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

## Conclusion

During the laboratory work, we explored the interface and capabilities of the Linux operating system, including graphical environments and the command line. We learned to perform basic operations such as launching applications, switching between virtual consoles, changing users, and shutting down the system.
