# Know Your Server

## Remote Access & SSH Security
*   **Initial Setup:** This challenge outlines the first encounter with a remote server and methods to secure remote access.
*   **Protocol Transition:** Connection to the server is facilitated by an SSH client. Previous legacy connections to the remote server relied on the insecure **Telnet** protocol.
*   **Network Persistence:** Access must be available from anywhere regardless of network changes (e.g., switching between home and office networks). This is achieved via a **Static Public IP or Domain Name** assigned by the VPS provider.
*   **Third-Party Trust:** Utilizing third-party clients like PuTTY or Termius requires placing trust in their software security and communication pipelines. 
*   **Native Execution:** Modern Windows 10/11 platforms, macOS, and Linux all include native OpenSSH clients, allowing you to bypass third-party tools entirely via the terminal.

### Establishing a Connection
Connections are initiated via an SSH client using the standard terminal terminal string:
```bash
ssh username@ip_address_or_domain
```
Access can be granted/Authenticated by the host server by password or the Public Key Infastructure
The ssh-keygen allows one to generate the 
The remote host handles these requests by listening on **Port 22** (the default SSH port).

*   **Provider Deployment:** A virtual private server (VPS) was successfully provisioned on the [InterServer Infrastructure](https://interserver.net) and accessed via native terminal configurations.

---

## General Server Reconnaissance

To identify the underlying Linux distribution and OS version running on the active VPS, execute the `lsb_release -a` or `cat etc/os-release` command.

**Command Output:**
```text
root@vps3614047:~# lsb_release -a
No LSB modules are available.
Distributor ID: Ubuntu
Description:    Ubuntu 24.04.5 LTS
Release:        24.04
Codename:       noble
```
To Get System Information such as the kernel version and hardware, execute the commands `uname -a`.

**Command Output:**
```Command Output 
root@vps3614047:~# uname -a
Linux vps3614047 6.8.0-111-generic #111-Ubuntu SMP PREEMPT_DYNAMIC Sat Apr 11 23:16:02 UTC 2026 x86_64 x86_64 x86_64 GNU/Linux
```
To know how long a server has been up and running, execute command `uptime`.

**Command Output:**
```Command Output 
root@vps3614047:~# uptime
10:30:30 up 7 days, 20:23,  3 users,  load average: 0.00, 0.00, 0.00
```
To know the username you logged on with - `whoami`. \
To know who is logged on - `who`. \
To know what the users are doing - `w`. 

**Command Output:**
 ```Command Output
 root@vps3614047:~# whoami
 root
 root@vps3614047:~# who
 root     pts/0        2026-09-19 08:39 (102.0.28.14)
 root@vps3614047:~# w
  10:43:02 up 7 days, 20:35,  3 users,  load average: 0.00, 0.00, 0.00
 USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU  WHAT
 root              102.0.28.14      08:39    4:38m  0.00s  0.98s sshd: root@pts/0
 lightdm           -                11Sep26  4:38m  0.00s  0.01s lightdm --session-child 17 20
 ```
## Hardware Reconnaissance
Commands helpful to get useful information about the hardware configuration such as the:
  CPU Archtecture - `lscpu`.
  Block Devices - `lsblk`.
  PCI Devices - `lspci`.
  USB Devices - `lsusb`.
