## Work-case 3

### Task 1. In the VMWare Fusion

#### 1. Clone guest OS

Select a virtual machine, click the RMB and then select "Create Full Clone..."

<img width="354" alt="Screenshot 2025-03-22 at 17 59 18" src="https://github.com/user-attachments/assets/e985279c-8ee9-427f-9cb1-1334a368807a" />

Select the directory where the clone will be saved and press "Save"

<img width="813" alt="Screenshot 2025-03-22 at 18 02 45" src="https://github.com/user-attachments/assets/af001bf7-5f83-4ac7-a30d-414e6186d367" />

Wait few seconds and the full clone of virtual machine will be created

#### 2. Export guest OS

Find where the guest OS is stored on the disk, select it and click the RMB and select "Show Package Contents"

<img width="454" alt="Screenshot 2025-03-22 at 18 09 27" src="https://github.com/user-attachments/assets/bc1eadf6-c485-4a25-875d-2f0fceab606f" />

There you can find file of the OS with ".vmx" format

<img width="285" alt="Screenshot 2025-03-22 at 18 13 04" src="https://github.com/user-attachments/assets/7bb44a0d-265d-4c5d-820a-c6777e1adc60" />

Then go to VMWare.app select it and in context menu select "Show Package Contents"

<img width="361" alt="Screenshot 2025-03-22 at 18 14 48" src="https://github.com/user-attachments/assets/b975f8f1-2570-4f74-acaa-539794bae8fd" />

There you can find `ovftool` file in `./Contents/Library/VMware OVF Tool/ovftool`

<img width="1001" alt="Screenshot 2025-03-22 at 18 15 58" src="https://github.com/user-attachments/assets/38c14c3d-91c5-49e2-a6b1-68da6f04fed1" />

Open terminal and enter there `path/to/ovftool --acceptAllEulas path/to/vmx export/destination/path ` and press enter

<img width="1129" alt="Screenshot 2025-03-22 at 18 18 26" src="https://github.com/user-attachments/assets/aedb6933-c5f5-4f01-b366-2a243b949681" />

Wait until the export process will be completed

<img width="1116" alt="Screenshot 2025-03-22 at 18 23 40" src="https://github.com/user-attachments/assets/ec1d67c1-721a-44b9-a866-0243fe491080" />

And then you can find the exported guest OS in OVF in entered folder

<img width="1052" alt="Screenshot 2025-03-22 at 18 24 36" src="https://github.com/user-attachments/assets/83067c51-e17d-4595-a84d-cc7192aca7a0" />

### Task 2. Different types of Virtual Machine Network Connections

#### NAT (Network Address Translation)

- Uses host's IP for external connections
- VMs get private IPs from VMware DHCP
- Internet access without extra IPs
- VMs are hidden behind host's firewall

#### Bridged

- VM connects directly to physical network
- Gets own IP from network DHCP
- Appears as independent device on network
- External devices can access VM directly

#### Host-only

- Private network between host and VMs
- VMs communicate with host and other VMs
- No external access without host routing
- Isolated from physical network

#### Internal Network

- Isolated network between VMs only
- No connection to host or external networks
- VMs only see other VMs on same internal network
- Complete network isolation

### Task 3

#### 1. Demonstrate the basic commands for configuring OS network settings and explain what they do.

1. `ip a`. This command displays all network interfaces and their assigned IP addresses.
2. `ip addr add <ip_addr>/<mask> dev eth0`. Adding static IP to network.
3. `ip link set eth0 up`, `ip link set eth0 down`. Enabling or disabling network inteface (eth0 in our case).
4. `ping <address>`. Check the connection (ping) between host and target. 
5. `ip route add <ip_addr>/<mask> via <address>`. Creating route between networks.

#### 2. Both operating systems must have access to the Internet. Open a browser and watch any video on youtube

![image](https://github.com/user-attachments/assets/476521b5-c665-45ae-a4a8-98cdbffdf999)

#### 3. Configure and demonstrate the exchange of messages between the two OSes over a local network. What commands do you need to enter in the terminal?

We will chat between machines using standard util - `netcat` (alias `nc`).

![image](https://github.com/user-attachments/assets/bb598429-d330-4d47-adbb-c3db03a8c2c1)

Running command `nc -l 1234` (or -nvlp for more information) on our listener machine to start listening.

![image](https://github.com/user-attachments/assets/04f349ac-33b4-4ed9-a8ce-c4c7bdcef5dc)

Running command `echo "Hello" | nc 192.168.122.124 1234` to send information to the listening machine. As you can see, a message appeared.

#### 4. Set up a shared network folder for both OSes. Try copying files from this directory to the user's home directory (virtual desktop) and to the desktop (clone of the virtual desktop)

To create file share between two machines we have to install `nfs-kernel-server` package on server machine and `nfs-client` on client one. 

The configuration process is pretty simple: all you have to do is edit `/etc/exports` by adding a line using the following pattern:

```
/folder {client_ip}({flag1}, {flag2}, ...)
```

A typical flag for shared directories is `rw`.

To connect to this share from the client you need to mount it using this command: `mount {ip}:{folder} {mount_point}`

### Task 4

There is many ways of communicating between host and VM.

1. Using Shared Folders (9p VirtFS) in virt-manager. Virt-manager supports 9p VirtFS, which allows you to share folders between your host and virtual machines.

- Enable Shared Folder in virt
- Open virt-manager → Select your VM → Click Edit → Virtual Machine Details.
- Go to Add Hardware → Choose Filesystem.
- Set Driver to virtiofs or default (depends on your system).
- Set Source Path to a folder on your host (e.g., C:\Shared in Windows or /home/user/shared in Linux).
- Set Target Path (mount point inside the VM), e.g., /mnt/shared.
- Start the VM and mount the shared folder: `sudo mount -t 9p -o trans=virtio shared_folder /mnt/shared`

2. Using scp (Secure Copy)

If your VM is running Linux and has SSH enabled, you can use scp to transfer files.

Let's try to copy an audio file from host to VM.

`scp ~/Music/audio.mp3 user@192.168.122.100:~/Desktop/`

That's how it works. It uses SSH to create a secure ssh-tunnel and then sends data via it.

3. Using rsync (For Large File Transfers)

Rsync is efficient for transferring large files between the host and VM.

`rsync -avz ~/Music/audio.mp3 user@192.168.122.100:~/Desktop/`

Flags -a, -v and -z used to perform archive mode, which will transfer all file metadata, -v for verbose mode and -z for compressing while transmitting.
