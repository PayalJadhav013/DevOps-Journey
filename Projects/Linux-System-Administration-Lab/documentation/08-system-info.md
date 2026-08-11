# Part 8 — System Information

## Objective

Practice Linux system information commands to inspect the hostname, kernel, operating system, CPU, memory, disk usage, uptime, logged-in users, system architecture, and basic system statistics.

---

## 1. Check Hostname

```bash
hostname
```
Output:
```text
localhost.localdomain
```
Displays the hostname of the Linux system.

## 2. Check Kernel and System Information
```bash
uname -a
```
Output:
```text
Linux localhost.localdomain 5.14.0-514.el9.x86_64 #1 SMP PREEMPT_DYNAMIC Mon Sep 30 14:56:52 UTC 2024 x86_64 x86_64 x86_64 GNU/Linux
```
Displays detailed kernel and system information.

## Check Kernel Version
```bash
uname -r
```
Output:
```text
5.14.0-514.el9.x86_64
```
Displays the currently running kernel release.

## Check System Architecture
```bash
uname -m
```
Output:
```text
x86_64
```
Displays the machine architecture.

## 3. Check Operating System Information
```bash
cat /etc/os-release
```
The system is running:
```text
CentOS Stream 9
```
This file contains information about the Linux distribution and version.

## 4. Check CPU Information
```bash
lscpu
```
The system reported:
```text
Architecture:    x86_64
CPU(s):          2
Vendor ID:       GenuineIntel
Model name:      11th Gen Intel(R) Core(TM) i5-1135G7 @ 2.40GHz
Socket(s):       1
Core(s) per socket: 2
```
`lscpu` displays detailed CPU architecture, processor, core, thread, virtualization, and cache information.

## 5. Check Memory Usage
```bash
free -h
```
Output:
```text
Mem:   1.7Gi   355Mi   1.2Gi   5.0Mi   349Mi   1.4Gi
Swap:  1.0Gi     0B   1.0Gi
```
Displays RAM and swap memory usage in human-readable format.

## Check Memory in MB
```bash
free -m
```
Displays memory usage in megabytes.

## Detailed Memory Information
```bash
cat /proc/meminfo
```
Displays detailed information about system memory.

## 6. Check Disk Usage
```bash
df -h
```
Displays filesystem disk usage in human-readable format.

Example:
```text
/dev/sda2   xfs   78G   2.1G   76G   3%   /
/dev/sda1   xfs  1014M   241M  774M  24%  /boot
```
This command is useful for checking available disk space.

## 7. Check System Uptime
```bash
uptime
```
Output:
```text
09:42:18 up 56 min, 1 user, load average: 0.02, 0.01, 0.00
```
Displays:
```text
Current time
System uptime
Number of logged-in users
Load average
```
## 8. Check Current Date and Time
```bash
date
```
Output:
```text
Tue Aug 11 09:42:27 AM UTC 2026
```
Displays the current system date and time.

## 9. Check Logged-in Users
```bash
who
```
Output:
```text
vagrant pts/0 2026-08-11 08:47 (10.0.2.2)
```
Displays currently logged-in users and their login sessions.

## 10. Check Current User
```bash
whoami
```
Output:
```text
root
```
Displays the username of the current user.

## 11. Check System Architecture
```bash
arch
```
Output:
```text
x86_64
```
Displays the system architecture.

## 12. Practice Output Redirection
## Redirect uptime output to a file
```bash
uptime > /tmp/systinfo.txt
```
The > operator creates the file or overwrites an existing file.

## Append uptime output
```bash
uptime >> /tmp/systinfo.txt
```
The >> operator appends output to the existing file.

## Redirect date output
```bash
date > /tmp/systinfo.txt
```
This overwrites the existing contents of the file with the date output.

Important: `>` overwrites the file, while `>>` appends to the file.

## 13. Count Lines in /etc/passwd
```bash
wc -l /etc/passwd
```
Output:
```text
33 /etc/passwd
```
Counts the number of lines in `/etc/passwd`.

## 14. Practice `echo`
```bash
echo "hello payal!"
```
Output:
```text
hello payal!
```
Displays text on the terminal.

---

# Commands Practiced

| Command | Purpose |
|---|---|
| `hostname` | Display hostname |
| `uname -a` | Display detailed kernel/system information |
| `uname -r` | Display kernel release |
| `uname -m` | Display machine architecture |
| `cat /etc/os-release` | Display OS information |
| `lscpu` | Display CPU information |
| `free -h` | Display memory usage in human-readable format |
| `free -m` | Display memory usage in MB |
| `cat /proc/meminfo` | Display detailed memory information |
| `df -h` | Display disk usage |
| `uptime` | Display system uptime and load |
| `date` | Display system date/time |
| `who` | Display logged-in users |
| `whoami` | Display current user |
| `arch` | Display system architecture |
| `echo` | Display text |
| `wc -l` | Count lines |
| `>` | Redirect and overwrite output |
| `>>` | Append output |

---

## Concepts Practiced
- Hostname identification
- Kernel information
- Operating system identification
- CPU information
- Memory monitoring
- Disk space monitoring
- System uptime
- Load average
- Logged-in user identification
- System architecture
- Output redirection
- File line counting

---

## Status

✅ **Part 8** — System Information Completed