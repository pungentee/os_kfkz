# Lab. #8

**Topic:** Saving system service data and network configuration

**Purpose of the Work:**

- Gaining practical skills in working with the Bash shell.
- Familiarization with the basic structures for storing system data - processes, memory, log files, and kernel status messages.
- Familiarity with the FHS standard.
- Learn how to configure the network.

## Answers to questions about preparing

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

## Conclusion

We gained practical experience in managing system data and network configurations in Linux using the Bash command-line interface. We explored the /proc filesystem, analyzed log files, and used network tools like ifconfig, ping, and dig. Working with commands like cal helped us better understand system administration and troubleshooting, enhancing our skills in Linux system management.
