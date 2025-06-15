# Lab. #8

**Topic:** Saving system service data and network configuration

**Purpose of the Work:**

- Gaining practical skills in working with the Bash shell.
- Familiarization with the basic structures for storing system data - processes, memory, log files, and kernel status messages.
- Familiarity with the FHS standard.
- Learn how to configure the network.

## Answers to questions about preparing

### 4.1. What is a “pseudo filesystem,” and why is it needed by the system?
A pseudo filesystem is a virtual filesystem that appears as a hierarchical structure of directories and files but exists only in memory, not on physical storage. Examples include `/proc` and `/sys`. It is needed to provide real-time access to system information, such as running processes, kernel configuration, and hardware details, allowing the system to manage and expose dynamic data efficiently.

### 4.2. Why do users rarely access the /proc directory directly, and how can information be obtained from it?  
Users rarely access `/proc` directly because it contains raw, low-level system data that is complex to interpret. Instead, commands like `top`, `free`, `ps`, and `mount` process and present this information in a user-friendly format. These commands read data from `/proc` and display it in a structured way, making it easier to understand.

### 4.3. What is the purpose of the /proc/cmdline, /proc/meminfo, and /proc/modules files?  
- **/proc/cmdline**: Contains command-line parameters and special instructions passed to the kernel at boot time.  
- **/proc/meminfo**: Provides information about the system’s memory usage, including total, free, and allocated memory.  
- **/proc/modules**: Lists currently loaded kernel modules that add extra functionality to the kernel.

### 4.4. What is the purpose of the `free` command?  
The `free` command displays a snapshot of the system’s memory usage, showing total, used, free, and cached memory. It helps monitor memory allocation and can be used with the `-s` option to update periodically (e.g., `free -s 10` for updates every 10 seconds).

### 4.5. What are log files used for, and provide examples of their application?  
Log files store system and process output to track operations, troubleshoot issues, and monitor for unauthorized access. Examples:  
- **/var/log/boot.log**: Records messages from services started during system boot.  
- **/var/log/secure**: Logs authentication-related events, such as login attempts.  
- **/var/log/messages**: Stores general kernel and process messages for system diagnostics.  

### 4.6. What is the purpose of the /var/log/dmesg file?  
The `/var/log/dmesg` file contains kernel messages generated during system startup, useful for diagnosing boot-related issues or hardware problems.

### 4.7. Why was the Filesystem Hierarchy Standard (FHS) developed?  
The FHS was developed to provide guidelines for organizing files and directories in Linux distributions, ensuring consistency across systems. It categorizes directories as shareable or non-shareable and static or variable, facilitating system administration and compatibility.

### 4.8. What are the main Linux commands for viewing and configuring the network?  
- **ifconfig**: Displays and configures network interface settings (deprecated in some distributions).  
- **ip**: A versatile command for network configuration, including IP address assignment and routing (`ip addr show`).  
- **ping**: Tests network connectivity to another host.  
- **netstat**: Displays network connections and routing tables.  
- **ss**: Shows socket statistics and connection details.  
- **dig**: Queries DNS servers for hostname-to-IP resolution.  
- **host**: Resolves hostnames to IP addresses.  
- **route**: Displays and manages the routing table.

## Main task

### Task 2. Linux Commands Description Table

| Command Name                                  | Purpose and Functionality                                                                                                      |
| --------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| cat /etc/sysconfig/network-scripts/ifcfg-eth0 | Displays the configuration file for the eth0 network interface, containing settings like IP address and gateway.               |
| cat /etc/resolv.conf                          | Shows the contents of the /etc/resolv.conf file, which lists DNS nameservers used for domain name resolution.                  |
| host example.com                              | Resolves the domain name example.com to its IP address(es) using DNS lookup.                                                   |
| host 192.168.1.2                              | Performs a reverse DNS lookup to find the hostname associated with the IP address 192.168.1.2.                                 |
| host -t CNAME example.com                     | Queries the Canonical Name (CNAME) record for the domain example.com.                                                          |
| host -t SOA example.com                       | Queries the Start of Authority (SOA) record for the domain example.com, providing administrative information about the domain. |
| host -a example.com                           | Performs a verbose DNS lookup for example.com, retrieving all available DNS records for the domain.                            |
| ssh bob@test                                  | Initiates a secure shell connection to the host 'test' as the user 'bob'.                                                      |
| exit                                          | Terminates the current shell session or logs out of the current user session.                                                  |
| cat /etc/hosts                                | Displays the contents of the /etc/hosts file, which maps hostnames to IP addresses for local resolution.                       |
| cat /etc/nsswitch.conf                        | Shows the contents of the /etc/nsswitch.conf file, which defines the order of sources (e.g., files, DNS) for name resolution.  |
| ifconfig                                      | Displays network interface configuration details, such as IP addresses and status (deprecated in favor of 'ip' command).       |
| ip addr show                                  | Shows detailed information about network interfaces, including IP addresses and their status.                                  |
| route                                         | Displays the kernel's IP routing table, showing routes for network traffic.                                                    |
| route -n                                      | Displays the IP routing table in numerical format, avoiding DNS lookups for faster output.                                     |
| ping -c 4 192.168.1.2                         | Sends 4 ICMP echo requests to the IP address 192.168.1.2 to check network connectivity.                                        |
| netstat -i                                    | Displays a table of network interfaces, including packet transmission and reception statistics.                                |
| netstat -r                                    | Shows the kernel's IP routing table, similar to the 'route' command.                                                           |
| netstat -tln                                  | Lists all listening TCP sockets with numerical addresses and ports, excluding non-listening connections.                       |
| netstat -tl                                   | Lists all listening TCP sockets, showing hostnames and ports for active listeners.                                             |
| ss                                            | Displays detailed socket statistics, including active connections, ports, and states (modern replacement for netstat).         |
| ss -s                                         | Shows a summary of socket statistics, including total connections and protocol-specific counts.                                |
| dig example.com                               | Performs a detailed DNS query for example.com, providing comprehensive DNS record information.                                 |

### Task 3

#### `cat` command

The `cat` command is used to:

- Create files
- Show file contents
- Copy or merge files
- Remove empty lines or add line numbers

#### `cat` usage examples

#### 1. **Create a file**

```bash
cat > file
```

#### 2. **View file content**

```bash
cat file
```

![Screenshot_20250612_123258](https://github.com/user-attachments/assets/ea4559c7-71f2-4471-997c-c35dc10c8bfd)

#### 3. **Copy to another file**

```bash
cat file > file2
```

![Screenshot_20250612_123328](https://github.com/user-attachments/assets/2893caa9-a3ad-4808-881b-2eee4835e9f5)

#### 4. **Merge files**

```bash
cat file file2 > merged
```

![Screenshot_20250612_123410](https://github.com/user-attachments/assets/97b93902-af7c-4de2-8ed8-a4a7dbf85f60)


#### 5. **Useful Options**

- Number lines:

```bash
cat -n file
```

![Screenshot_20250612_123450](https://github.com/user-attachments/assets/1f8b3af9-5c50-41c0-aff2-6d341b06c33d)

- Show hidden characters:

```bash
cat -v file
```

- Remove extra empty lines:

```bash
cat -s file
```

#### `dig` command

`dig` is used to get DNS info (like IP addresses of websites)

- Check IP of website:

```bash
dig google.com
```

![Screenshot_20250612_123511](https://github.com/user-attachments/assets/2b040110-9832-41fd-860e-75e7032c8444)

- Short answer (just IP):

```bash
dig +short google.com
```

- Show mail servers (MX records):

```bash
dig google.com MX
```

![Screenshot_20250612_123533](https://github.com/user-attachments/assets/8f3078fe-33f1-4db3-99aa-1cf2d2211568)

#### `netstat` command

`netstat` shows network connections, ports, and listening services.

- Show all connections:

```bash
netstat -a
```

![Screenshot_20250612_123559](https://github.com/user-attachments/assets/539ee50f-eac7-470a-9fd0-1f388b7b0fcd)

- Show open ports:

```bash
netstat -tuln
```

![Screenshot_20250612_123617](https://github.com/user-attachments/assets/d616b0cc-0c21-4086-847c-3ec3bc1a4d68)

- Show programs using ports:

```bash
netstat -tulnp
```

![Screenshot_20250612_123628](https://github.com/user-attachments/assets/d18fb33c-c85d-420f-b273-e2d385bb421b)

## Answers to control questions

### 1. How are the `cat` and `tac` commands related?  
The `cat` command displays file contents in their original order, while `tac` displays them in reverse order (line by line, starting from the last line). Both are used for viewing text files but differ in output direction.

### 2. What does the `ss` command do?  
The `ss` command displays socket statistics, showing active network connections, their states, and related details. It is a modern replacement for `netstat`, offering more features and detailed output about network sockets.

### 3. What is the difference between the `ps --forest` and `pstree` commands?  
- **ps --forest**: Displays running processes in a hierarchical, tree-like format, showing parent-child relationships, but is part of the `ps` command’s output.  
- **pstree**: Specifically designed to display a tree of processes, providing a clearer, more concise visualization of process hierarchies.

### 4. In which directories are system configuration files stored?  
System configuration files are typically stored in:  
- **/etc**: Main directory for system-wide configuration files (e.g., `/etc/syslog.conf`, `/etc/network/interfaces`).  
- **/proc**: Contains runtime kernel configuration (e.g., `/proc/sys/`).  
- **/sys**: Stores kernel and device configuration settings.

### 5. In which directories can user-accessible installed programs be found?  
User-accessible programs are typically found in:  
- **/usr/bin**: Standard user-executable binaries.  
- **/usr/local/bin**: Locally installed user programs.  
- **/bin**: Essential user binaries available during system boot.

### 6. In which directories can system programs and those intended for the superuser be found?  
System and superuser programs are located in:  
- **/sbin**: Essential system binaries for administrative tasks (e.g., `fsck`, `init`).  
- **/usr/sbin**: Non-essential system binaries for superuser tasks.  
- **/usr/local/sbin**: Locally installed system binaries for superuser use.

### 7. Explain the purpose of the `ping`, `ifconfig`, and `traceroute` commands.  
- **ping**: Tests network connectivity by sending packets to a host and measuring response time.  
- **ifconfig**: Displays and configures network interface parameters, such as IP addresses (e.g., for `eth0`).  
- **traceroute**: Traces the route packets take to a destination host, showing each hop and latency.

### 8. What are network interfaces called in Linux?  
Network interfaces in Linux are typically named `eth0`, `eth1` (for Ethernet), `wlan0` (for Wi-Fi), or `lo` (for the loopback interface). Modern systems may use names like `enp0s3` based on hardware location.

### 9. How can you use the `ifconfig` command to display the parameters of only one network interface (e.g., eth1)?  
To display parameters for a specific interface like `eth1`, use:  
```bash
ifconfig eth1
```

## Conclusion

We gained practical experience in managing system data and network configurations in Linux using the Bash command-line interface. We explored the /proc filesystem, analyzed log files, and used network tools like ifconfig, ping, and dig. Working with commands like cal helped us better understand system administration and troubleshooting, enhancing our skills in Linux system management.
