# Work Case #1 (pungentee)

### 1. Install a hypervisor on your home workstation

![image](./attachments/Screenshot%202025-02-23%20at%2022.55.44.png)

### 2. Describe a set of basic actions in the hypervisor you have installed

#### Create a new virtual machine

- Select in menu File -> New...
- Window of VM creation opens

![image](./attachments/Screenshot%202025-02-23%20at%2023.00.27.png)

- Press on "Install from disc or image"
- Drag & drop your os image (Fedora's Net Installer ISO in my case)

![image](./attachments/Screenshot%202025-02-23%20at%2023.09.33.png)

- Press "Continue"
- Select OS type (if it isn't autodetected, as in my case)
- Check your os settings and name your VM
- Finish

#### Set up a network and connect to Wi-Fi points
You can set up network settings in the Network Adapter settings section

![image](./attachments/Screenshot%202025-02-23%20at%2023.33.21.png)

#### Ability to work with external media
You can set up external media in the CD/DVD settings section

![image](./attachments/Screenshot%202025-02-23%20at%2023.34.23.png)

### Install the GNU/Linux operating system (any distribution convenient for you) in your hypervisor in a basic configuration with a graphical shell

#### Run VM and select installer

![image](./attachments/Screenshot%202025-02-24%20at%2000.08.41.png)

#### Select language that will be used

![image](./attachments/Screenshot%202025-02-24%20at%2000.09.54.png)

#### Setup disk in Installation Destination

![image](./attachments/Screenshot%202025-02-24%20at%2000.10.50.png)

#### Select system edition in Software Selection (i will choose Cinnamon Desktop)

![image](./attachments/Screenshot%202025-02-24%20at%2000.12.31.png)

#### Setup up password for root user

![image](./attachments/Screenshot%202025-02-24%20at%2000.13.35.png)

#### Setup non-root user

![image](./attachments/Screenshot%202025-02-24%20at%2000.14.01.png)

#### Press Begin Installation

![image](./attachments/Screenshot%202025-02-24%20at%2000.14.28.png)

#### Wait...

![image](./attachments/Screenshot%202025-02-24%20at%2000.15.03.png)

#### Done

![image](./attachments/Screenshot%202025-02-24%20at%2001.09.24.png)

### Create a second virtual machine and do the following for it

#### Pure OpenSUSE without any DE

![image](./attachments/Screenshot%202025-02-24%20at%2001.10.23.png)

#### Installing minimal Gnome and Sway

![image](./attachments/Screenshot%202025-02-24%20at%2001.15.41.png)
![image](./attachments/Screenshot%202025-02-24%20at%2001.59.57.png)

#### Installed Gnome

![image](./attachments/Screenshot%202025-02-24%20at%2001.59.41.png)

#### Installed Sway

![image](./attachments/Screenshot%202025-02-24%20at%2002.02.52.png)


#### Gnome DE vs Sway WM ccomparison

| Feature              | Gnome Desktop Environment                                    | Sway Window Manager                     |
| -------------------- | ------------------------------------------------------------ | --------------------------------------- |
| Type                 | Full desktop environment                                     | Tiling window manager                   |
| Display Protocol     | X11 and Wayland support                                      | Wayland only                            |
| Window Management    | Floating by default, with optional tiling                    | Tiling by default                       |
| Resource Usage       | Heavier (500MB-1GB RAM%20at%20idle)                              | Very light (10-50MB RAM%20at%20idle)        |
| Configuration        | GUI-based (Settings, GNOME Tweaks)                           | Text file based (~/.config/sway/config) |
| Default Controls     | Mouse-oriented with keyboard shortcuts                       | Keyboard-focused with mouse support     |
| Learning Curve       | Gentle, familiar to most users                               | Steeper, requires manual configuration  |
| Built-in Features    | Complete suite (file manager, settings, notifications, etc.) | Window management only                  |
| Customization        | Through extensions and themes                                | Through config files and external tools |
| Dependencies         | Many (GTK, GNOME Shell, etc.)                                | Minimal (Wayland, wlroots)              |
| Workflow             | Traditional desktop paradigm                                 | Workspace-based tiling                  |
| Package Size         | Large (~1.5GB with default apps)                             | Small (~5MB core package)               |
| Default Apps         | Full suite of GNOME applications                             | None                                    |
| Status Bar           | GNOME Shell top bar                                          | Requires external (e.g., waybar)        |
| Application Launcher | Activities overview                                          | Requires external (e.g., wofi, bemenu)  |
