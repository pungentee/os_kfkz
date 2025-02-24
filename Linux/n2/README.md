# Work Case №2

## Vladislav 'ElCapitan' Nazarov

### 1. Install hypervisor (IInd type)

![image](https://github.com/user-attachments/assets/a9488361-56f1-4637-85f5-c907fd8dc21a)

### 2. Describe the basic functionality of the hypervisor

#### Creating a new VM
  - Select virtualisation technology (KVM/Qemu in my case) via File -> New Connection
  - Create a new VM. File -> New Virtual Machine
  - Select whether to import or create a new VM (in our case we'll create a new one)

    ![image](https://github.com/user-attachments/assets/0e4be233-3764-4240-b299-393504b4f1e2)

  - Select installation media from the pool

    ![image](https://github.com/user-attachments/assets/69bfe1a1-6266-4fb7-885d-f6278d6da06d)

  - Configure settings of your hypervisor (RAM, Disk etc)
  - To add a flash drive you want to have it mounted to your os and add a mount point as a shared directory

### 3. Installing a distro

1. Booting OS

![image](https://github.com/user-attachments/assets/c5a22b74-04b3-4a8b-96a1-e7da9a28ddbe)

2. Installing the installer

![image](https://github.com/user-attachments/assets/4f026e3f-0567-48e9-a1c1-bd45028c8578)

3. Opening the installer

![image](https://github.com/user-attachments/assets/6a7b84ad-3770-46e3-9e95-9dbbd481fa29)

4.1. Installing base system

![image](https://github.com/user-attachments/assets/706df571-ec55-443d-91c9-53ecb6050f08)

4.2. Selecting base system only installation type

![image](https://github.com/user-attachments/assets/d989df3d-607a-4110-8c9e-788a6ef929d6)

5. Waiting for installation

![image](https://github.com/user-attachments/assets/3b562332-9bd9-4846-9633-875118be2562)

6. Installation complete

![image](https://github.com/user-attachments/assets/65131a1b-44a9-49d1-8b01-23a00aa772e1)

Rebooting

![image](https://github.com/user-attachments/assets/fe0758f3-ce51-4242-a375-dee69a6427d7)

System installed

![image](https://github.com/user-attachments/assets/a87fa562-d588-4cc0-a90c-f5b2c3c3b82a)

### 4. Installing the second VM

1. Installing basic Arch Linux

![image](https://github.com/user-attachments/assets/f8675d31-ab47-443c-b6cb-592c9df0ba6c)

2. Installing GNOME

```
pacman -Sy gnome
```

- Running GDM via systemctl

```
systemctl start gdm
```

![image](https://github.com/user-attachments/assets/10467c62-467f-4551-b662-1336254d9f17)

![image](https://github.com/user-attachments/assets/c561cebf-0e70-44cd-b7a9-3785e358ecad)

3. Installing the second DM

- Installing X11

```
pacman -S xorg-server xorg-xinit
```

- Installing i3

```
pacman -Sy i3
```

- Simply configuring .xinitrc file in user's home for `startx` (xorg-xinit package)

```
exec i3
```

- Starting Xorg/Xinit

```
startx
```

![image](https://github.com/user-attachments/assets/617776e5-f380-4829-909d-49eae8689585)

![image](https://github.com/user-attachments/assets/834f26c6-bfdd-4b1a-9ff8-f973385a3ae2)

5. Comparision

| Feature              | i3                                  | GNOME 47                            |
|----------------------|-------------------------------------|-------------------------------------|
| **Type**             | Lightweight Tiling Window Manager   | Full Desktop Environment            |
| **Display Server**   | X11/Xorg                            | Wayland-protocol based              |
| **Resource Usage**   | Very lightweight (~5-10MB RAM)      | Heavier (~1-2GB RAM)                |
| **UI Approach**      | Keyboard-driven, minimal            | Mouse-friendly, modern UI           |
| **Customization**    | Highly configurable via text files  | Limited but extensible via extensions |
| **Compositing**      | No built-in compositor (uses picom, etc.) | Built-in Mutter compositor    |
| **Application Launcher** | dmenu, rofi (customizable)      | GNOME Overview (Super key)          |
| **Workspace Management** | Manual control, workspaces assigned to numbers | Dynamic, automatic workspace handling |
| **Extensions**       | No official extensions, relies on scripts | GNOME Extensions available    |
| **System Integration** | Minimal system utilities          | Full integration with GNOME apps    |
| **Touchscreen Support** | Poor (no native support)         | Good (supports gestures)            |
| **Learning Curve**   | Steep (manual config needed)        | Easier (user-friendly interface)    |
| **Best For**         | Power users, keyboard enthusiasts   | General users, modern workflow      |


## pungentee

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
| Resource Usage       | Heavier (500MB-1GB RAM at idle)                              | Very light (10-50MB RAM at idle)        |
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
