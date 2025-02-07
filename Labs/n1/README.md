# Lab. #1

**Topic:** "Introduction to the Virtual Machine Environment and Features of the Linux Operating System"

**Purpose of the Work:**
1. Familiarization with different types of hypervisors and virtualization when working with operating systems.
2. Introduction to the main types of modern operating systems and a brief overview of their capabilities.

## Main task

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
eselect profile set 25 (for GNOME)
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
