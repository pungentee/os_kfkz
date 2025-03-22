## Work-case 3

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
