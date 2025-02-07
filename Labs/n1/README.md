# Lab. #1

**Topic:** "Introduction to the Virtual Machine Environment and Features of the Linux Operating System"

**Purpose of the Work:**
1. Familiarization with different types of hypervisors and virtualization when working with operating systems.
2. Introduction to the main types of modern operating systems and a brief overview of their capabilities.

## Main task

### 2.1 List the steps to deploy an operating system based on a VirtualBox virtual machine.

VM creation stages:
1. Check wether CPU virtualisation is enabled in your BIOS/UEFI 
2. Download .ISO image of OS you prefer to install (if needed)
3. Open VirtualBox application on your machine
4. Press “Create New” button to create new virtual machine
5. Following simple GUI configure name of VM, guest OS type, amount of RAM and disk space
6. Run guest OS

### 2.2 32- and 64-bit OSes installation:

- For 32-bit OS nowadays there are no real hardware limitations (for CISC/RISC CPUs) because every 64-bit CPU has backward compatibility, except full-RISC CPUs. But for 64-bit OS will work only with 64-bit CPU.

- A 32-bit OS is typically limited to addressing around 4GB of RAM, while a 64-bit OS can support much more.

- Some modern 64-bit OSes require UEFI firmware, while older 32-bit OSes work only with BIOS.

- A 64-bit OS needs 64-bit drivers, which may not be available for older hardware

### 2.3  Linux OS install stages in CLI mode:
1. Formatting drive
2. Creating file systems with mkds.xxxx where x, name of FS.
3. Installing basic OS
4. Writing/Generating fstab
5. Entering new os (chroot)
6. Configuring OS
7. Setting up root password (passwd)
8. Setting up bootloader
9. reboot

### 2.4 KDE, GNOME installation for preinstalled OS:

#### KDE:

**Gentoo Linux**

(previously) 
```
eselect profile set 27
```

```
emerge –ask –verbose kde-plasma/plasma-meta
```

**Arch Linux**

```
pacman -Sy plasma-desktop
```

**Debian GNU/Linux**

```
apt install kde-plasma-desktop
```

#### GNOME:

**Gentoo Linux**

(previously) 
```
eselect profile set 25
```

```
emerge --ask gnome-base/gnome
```

**Arch Linux**

```
sudo pacman -Sy gnome gnome-extra
```

**Debian GNU/Linux**

```
sudo apt install gnome
```

### 2.5 

| Feature        | XFCE                           | LVWM                           |
|--------------|--------------------------------|--------------------------------|
| **Type**      | Desktop Environment           | Lightweight Virtual Window Manager |
| **Target Users** | Users looking for a lightweight but full-featured desktop | Advanced users preferring a minimal and scriptable WM |
| **Design Philosophy** | Lightweight, modular, and traditional UI | Minimal, highly configurable, and tiling-based |
| **Resource Usage** | Low (suitable for older hardware) | Extremely low (even lighter than XFCE) |
| **Customization** | Moderate (supports themes and panel plugins) | Very high (scriptable configuration) |
| **Default Apps** | Comes with Thunar (file manager), Mousepad (text editor), and other utilities | Does not include default apps, relies on external tools |
| **Keyboard Shortcuts** | Supports basic shortcuts and custom key bindings | Fully keyboard-driven workflow possible |
| **Compositing** | Built-in (xfwm4) with optional effects | No built-in compositing (requires external tools) |
| **Multi-Monitor Support** | Good support via XRandR | Requires manual configuration |
| **Commonly Used In** | Xubuntu, Manjaro XFCE, Debian XFCE | Advanced Arch Linux setups, custom lightweight distros |
| **Strengths** | Balance of speed and usability, easy to use | Extremely lightweight, flexible, efficient for power users |
| **Weaknesses** | Lacks some modern UI effects, less customizable than KDE | Steep learning curve, requires manual configuration |

## Control questions

### 5. What system administration tasks can be implemented on the basis of Linux?

Linux supports essential system administration tasks like managing users, groups, and file systems; configuring networks and security; installing and updating software; monitoring processes and performance; handling backups and logs; setting up servers; and automating tasks with scripts or tools like Ansible. It also excels in virtualization and container management (e.g., Docker, Kubernetes). Linux's flexibility and open-source nature make it a powerful platform for system administration.

### 6. What is the relationship between Android and Linux? 

Android is based on the Linux kernel, which provides core functionality like hardware interaction and process management. However, Android is not a traditional Linux distribution—it replaces GNU tools with a custom runtime (ART) and is tailored for mobile devices with features like touchscreens and power management. While the core Android system is open source, many devices include proprietary additions like Google Play Services.

### 7. What are the main features and scope of Embedded Linux?

Embedded Linux is a customized version of Linux designed for embedded systems, offering features like customizability, open-source flexibility, portability across hardware architectures, real-time capabilities, robust networking, and strong security. It is widely used in consumer electronics, industrial automation, automotive systems, networking devices, medical equipment, aerospace, IoT, and wearables. Its adaptability, cost-effectiveness, and extensive toolchain make it a popular choice for developers in diverse industries.

### 8. How can I change the Linux boot type: in text mode (level 3) or graphical mode (level 5)? What is the difference between CLI and GUI modes?

To change the Linux boot type between text mode (runlevel 3) and graphical mode (runlevel 5), you can permanently set the default runlevel or temporarily switch modes. For **SysV init**, edit `/etc/inittab` and set `id:3` for text mode or `id:5` for graphical mode. For **systemd**, use `sudo systemctl set-default multi-user.target` for text mode or `graphical.target` for graphical mode. Temporarily switch modes with `sudo systemctl isolate multi-user.target` (text) or `graphical.target` (graphical).
