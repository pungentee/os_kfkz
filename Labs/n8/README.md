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

## Answers to control questions

## Conclusion

During this practical work, the student gained hands-on experience managing system data and network configurations in the Linux operating system using the Bash command-line interface. The tasks included exploring the /proc filesystem, analyzing log files, using network tools like ifconfig, ping, and dig, and applying the cal command to handle files, enhancing skills in system administration and troubleshooting.
