# Linux Notes

## Topics Covered

- Introduction to Linux
- Linux File System
- Basic Linux Commands
- File & Directory Operations
- Vim Editor
- Linux File Types
- Linux Filters & Text Processing
- Linux Log Files
- Search and Replace
- Input / Output (I/O) Redirection
- Pipes
- Searching Files
- Users and Groups
- File Permissions
- Sudo
- Package Management
- Linux Services
- Linux Processes
- Archiving & Compression

---

# 1. Introduction to Linux

Linux is an open-source, Unix-based operating system widely used in servers, cloud computing, DevOps, and embedded systems.

## Features

- Open Source
- Multi-user
- Multitasking
- Secure
- Stable
- Portable
- Command Line Interface (CLI)

## Why Linux in DevOps?

- Most cloud servers run Linux.
- Automation and scripting are easier.
- Lightweight and reliable.
- Widely used with Docker, Kubernetes, Jenkins, AWS, and Terraform.

---

# 2. Linux File System

Everything in Linux is considered a file.

## Root Directory

```
/
```

## Common Directories

```
/home    User home directories
/root    Root user's home directory
/bin     Essential user commands
/sbin    System administration commands
/etc     Configuration files
/usr     User applications
/var     Log and variable data
/tmp     Temporary files
/dev     Device files
/proc    Process information
```

---

# 3. Basic Linux Commands

## Current Directory

```bash
pwd
```

Displays the current working directory.

---

## List Files

```bash
ls
```

Lists files and directories.

Useful options:

```bash
ls -l
```

Displays detailed information.

```bash
ls -a
```

Displays hidden files.

---

## Change Directory

```bash
cd directory_name
```

Move into a directory.

```bash
cd ..
```

Move one directory back.

```bash
cd ~
```

Go to the home directory.

---

## Clear Terminal

```bash
clear
```

Clears the terminal screen.

---

## Current User

```bash
whoami
```

Displays the currently logged-in user.

---

## Command History

```bash
history
```

Displays previously executed commands.

---

# 4. File and Directory Operations

## Create Directory

```bash
mkdir project
```

Creates a new directory.

---

## Create File

```bash
touch file.txt
```

Creates an empty file.

---

## Copy Files

```bash
cp source destination
```

Copy directories recursively:

```bash
cp -r folder1 folder2
```

---

## Move or Rename

```bash
mv oldname newname
```

Moves or renames files/directories.

---

## Remove File

```bash
rm file.txt
```

Remove directory recursively:

```bash
rm -r folder
```

---

## Display File Content

```bash
cat file.txt
```

---

## View First Lines

```bash
head file.txt
```

---

## View Last Lines

```bash
tail file.txt
```

---

# 5. Vim Editor

Vim is a powerful command-line text editor available in Linux.

## Vim Modes

### 1. Command Mode (Default Mode)

- Vim starts in **Command Mode** by default.
- Used for navigation, copying, deleting, and moving around the file.
- Press **Esc** anytime to return to Command Mode.

---

### 2. Insert Mode (Edit Mode)

Used for writing or editing text.

Enter Insert Mode:

```bash
i
```

Return to Command Mode:

```bash
Esc
```

---

### 3. Extended Command Mode

Enter this mode by pressing:

```bash
:
```

Common commands:

Save file

```bash
:w
```

Quit

```bash
:q
```

Save and Quit

```bash
:wq
```

Quit without Saving

```bash
:q!
```

---

## Basic Vim Workflow

Open a file:

```bash
vim filename
```

1. Vim opens in **Command Mode**.
2. Press **i** to enter **Insert Mode (Edit Mode)**.
3. Press **Esc** to return to **Command Mode**.
4. Press **:** to enter **Extended Command Mode**.
5. Use `:w`, `:q`, `:wq`, or `:q!`.

---

# 6. Linux File Types

Linux supports different file types.

| File Type | Description |
|-----------|-------------|
| Regular File | Stores normal data files |
| Directory | Contains files and directories |
| Symbolic Link | Shortcut to another file or directory |
| Character Device | Represents devices like keyboard and terminal |
| Block Device | Represents storage devices such as HDD or SSD |
| Socket | Used for communication between processes |
| Named Pipe (FIFO) | Used for inter-process communication |

---

# Practical Commands Practiced

- pwd
- ls
- ls -l
- ls -a
- cd
- mkdir
- touch
- cp
- mv
- rm
- cat
- head
- tail
- vim
- whoami
- history
- clear


---

# 7. Linux Filters & Text Processing

Linux filters process text by reading input, performing operations, and producing output. They are commonly used with files, logs, and pipelines.

## grep

Searches for a specific word or pattern in a file.

Example:

```bash
grep "error" logfile.txt
```

Useful options:

```bash
grep -i "linux" file.txt    # Ignore case
grep -n "hello" file.txt    # Show line numbers
grep -v "test" file.txt     # Exclude matching lines
```

---

## less

Displays file content one screen at a time.

```bash
less file.txt
```

Useful keys:

- `Space` → Next page
- `b` → Previous page
- `/word` → Search
- `q` → Quit

---

## more

Displays file content page by page.

```bash
more file.txt
```

---

## head

Displays the first 10 lines of a file.

```bash
head file.txt
```

Show first 20 lines:

```bash
head -20 file.txt
```

---

## tail

Displays the last 10 lines of a file.

```bash
tail file.txt
```

View logs in real time:

```bash
tail -f logfile.log
```

---

# 8. Linux Log Files

Linux stores logs that help monitor system activity and troubleshoot issues.

Common log locations:

```text
/var/log/
```

Examples:

```text
/var/log/messages
/var/log/syslog
/var/log/secure
/var/log/auth.log
/var/log/dmesg
```

Useful commands:

```bash
cat /var/log/syslog
less /var/log/syslog
tail -f /var/log/syslog
grep "error" /var/log/syslog
```

---

# 9. Search and Replace

Use `sed` to search and replace text.

Replace the first occurrence:

```bash
sed 's/Linux/Ubuntu/' file.txt
```

Replace all occurrences:

```bash
sed 's/Linux/Ubuntu/g' file.txt
```

Replace and save changes:

```bash
sed -i 's/old/new/g' file.txt
```

---

# Practical Commands Practiced

- grep
- grep -i
- grep -n
- grep -v
- less
- more
- head
- tail
- tail -f
- sed

---

---

# 10. Input / Output (I/O) Redirection

I/O Redirection allows the output of one command to be redirected to a file, another command, or discarded.

### Standard Streams

- Standard Input (stdin)
- Standard Output (stdout)
- Standard Error (stderr)

### Common Commands

Display system uptime

```bash
uptime
```

Display memory usage

```bash
free -m
```

Display disk usage

```bash
df -h
```

Print text to the terminal

```bash
echo "Hello Linux"
```

Redirect output to a file

```bash
echo "Hello Linux" > file.txt
```

Append output to a file

```bash
echo "DevOps" >> file.txt
```

Discard output

```bash
command > /dev/null
```

---

# 11. Pipes

A pipe (`|`) passes the output of one command as the input to another command.

Example:

```bash
ls -l | grep txt
```

```bash
cat file.txt | less
```

---

# 12. Searching Files

## find

Search files and directories based on different criteria.

```bash
find /home -name file.txt
```

```bash
find . -type f
```

---

## locate

Quickly searches files using a pre-built database.

```bash
locate file.txt
```

---

## updatedb

Updates the database used by the `locate` command.

```bash
updatedb
```

---

## mlocate

`mlocate` is the package that provides the `locate` command.

---

# 13. Users and Groups

Linux supports multiple users with different permission levels.

### Types of Users

- Root User
- Regular User
- Service/System User

---

## User Information Commands

Display first user entry

```bash
head -1 /etc/passwd
```

Display user information

```bash
id vagrant
```

Display group information

```bash
grep vagrant /etc/group
```

Display last few lines

```bash
tail -4 /etc/passwd
```

---

## User Management

Create user

```bash
useradd aws
```

Set password

```bash
passwd aws
```

Switch user

```bash
su - ansible
```

Display login history

```bash
last
```

Display open files of a user

```bash
lsof -u vagrant
```

Delete user

```bash
userdel aws
```

Delete user with home directory

```bash
userdel -r aws
```

---

## Group Management

Create group

```bash
groupadd devops
```

Delete group

```bash
groupdel devops
```

---

# Practical Commands Practiced

- uptime
- free -m
- df -h
- echo
- (>)
- (>>)
- /dev/null
- |
- find
- locate
- updatedb
- head
- tail
- id
- grep
- useradd
- userdel
- userdel -r
- passwd
- su
- last
- lsof
- groupadd
- groupdel

---

# 14. File Permissions

Linux uses file permissions to control who can read, write, or execute files and directories.

## Permission Types

| Permission | Symbol | Meaning |
|------------|--------|---------|
| Read | r | View the contents of a file |
| Write | w | Modify the contents of a file |
| Execute | x | Execute a file or access a directory |

## Permission Categories

- User (Owner)
- Group
- Others

Example:

```text
-rwxr-xr--
```

Where:

- `-` → Regular file
- `rwx` → Owner permissions
- `r-x` → Group permissions
- `r--` → Others permissions

---

## Viewing File Permissions

```bash
ls -l
```

Displays detailed information, including file permissions.

---

## Changing Permissions – Symbolic Method

The symbolic method uses letters to add or remove permissions.

Common symbols:

- `+` → Add permission
- `-` → Remove permission
- `=` → Assign exact permission

Examples:

```bash
chmod u+x file.txt
chmod g+w file.txt
chmod o-r file.txt
chmod a+r file.txt
```

Where:

- `u` → User
- `g` → Group
- `o` → Others
- `a` → All users

---

## Changing Permissions – Numeric Method

The numeric method uses numbers.

| Permission | Value |
|------------|------:|
| Read (r) | 4 |
| Write (w) | 2 |
| Execute (x) | 1 |

Examples:

| Number | Permission |
|--------:|------------|
| 7 | rwx |
| 6 | rw- |
| 5 | r-x |
| 4 | r-- |
| 0 | --- |

Example:

```bash
chmod 755 file.sh
chmod 644 notes.txt
chmod 777 test.sh
```

Common Permission Values

| Permission | Meaning |
|------------|---------|
| 755 | Owner: rwx, Group: r-x, Others: r-x |
| 644 | Owner: rw-, Group: r--, Others: r-- |
| 700 | Owner only has full access |
| 777 | Everyone has full access (not recommended) |

---

## Changing Ownership

Change file owner:

```bash
chown username file.txt
```

Change file group:

```bash
chgrp groupname file.txt
```

Change both owner and group:

```bash
chown username:groupname file.txt
```

---

# 15. Sudo

Sudo (Super User Do) allows a permitted user to execute commands with administrative (root) privileges.

Instead of logging in as the root user, users can perform administrative tasks using `sudo`.

Example:

```bash
sudo command
```

Examples:

```bash
sudo yum update
sudo systemctl restart sshd
sudo useradd developer
```

---

## Why Use Sudo?

- Provides temporary administrative access.
- Improves system security.
- Reduces the need to log in as the root user.
- Allows administrators to control which users can execute privileged commands.

---

## Checking Sudo Access

```bash
sudo -l
```

Displays the commands the current user is allowed to run using sudo.

```md
# Commands Practiced

```bash
ls -l
chmod
chown
chgrp
sudo
sudo -l


# 16. Package Management

Package management is the process of installing, updating, removing, and managing software packages in Linux.

Different Linux distributions use different package managers.

| Distribution | Package Manager |
|--------------|-----------------|
| RHEL / CentOS | yum / dnf / rpm |
| Ubuntu / Debian | apt / dpkg |

---
## RPM (Red Hat Package Manager)

List installed packages

```bash
rpm -qa
```

Install an RPM package
```bash
rpm -ivh package.rpm

Where:

-`i` → Install
-`v` → Verbose
-`h` → Progress bar

## DPKG (Debian Package Manager)

List installed packages

```bash
dpkg -l
```
## Download Packages

Download a file from the internet.
```bash
whet <URL>
```
Example
```bash
wget https://example.com/file.rpm
```

## YUM Package Manager

Install package
```bash
yum install httpd
```
Install automatically
```bash
yum install httpd -y
```
Upgrade packages
```bash
yum upgrade
```
## DNF Package Manager

Install package
```bash
dnf install httpd
```
## Telnet

Used for testing network connectivity.
```bash
telnet hostname port
```
---

# 17. Linux Services

Linux services are background programs managed by systemd.

Common service management commands:

Check service status
```bash
systemctl status httpd
```
Start service
```bash
systemctl start httpd
```
Stop service
```bash
systemctl stop httpd
```
Enable service at boot
```bash
systemctl enable httpd
```
Check if service is active
```bash
systemctl is-active httpd
```
View enabled service link
```bash
cat /etc/systemd/system/multi-user.target.wants/httpd.service
```
---

# 18. Linux Processes

A process is a running instance of a program.
Viewing Processes

Interactive process monitor
```bash
top
```
List ll processes
``bash
ps aux
```
Another process listing
```bash
ps -ef
```
Search process
```bash
ps -ef | grep httpd
```
## Killing Processes

Terminate process
```bash
kill PID
```
Force terminate
```bash
kill -9 PID
```
Kill multiple processes
```bash
ps -ef | grep httpd | grep -v grep | awk '{print $2}' | xargs kill -9
```
---
# 19. Archiving & Compression

Archiving combines multiple files into one file.

Compression reduces file size.

TAR Archive

Create archive
```bash
tar -czvf archive.tar.gz folder
```
Options:

-`c` → Create
-`z` → Compress (gzip)
-`v` → Verbose
-`f` → File name

Extract archive
```bash
tar -xzvf archive.tar.gz
```
Extract to another directory
```bash
tar -xzvf archive.tar.gz -C /opt/
```

# ZIP Archive

Install zip utilities
```bash
yum install zip unzip -y
```
Create zip
```bash
zip -r archive.zip folder
```
Extract zip
```bash
unzip archive.zip
```
Checking Archive Type
```bash
file archive.tar.gz
```
---
# Practical Commands Practiced

- rpm -qa
- rpm -ivh
- dpkg -l
- wget
- yum install
- yum upgrade
- dnf install
- telnet
- systemctl
- top
- ps aux
- ps -ef
- grep
- kill
- kill -9
- awk
- xargs
- tar
- zip
- unzip
- file
---
# Module Status

**Status:** 🚧 In Progress

**Topics Completed:** 19

**Next Module**

- Networking Basics

