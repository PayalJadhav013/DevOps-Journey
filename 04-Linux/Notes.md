# Linux Notes

## Module Completed

- Introduction to Linux
- Linux File System
- Basic Linux Commands
- File & Directory Operations
- Vim Editor
- Linux File Types

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

# Module Status

Completed

- Linux Introduction
- Linux File System
- Basic Linux Commands
- File & Directory Operations
- Vim Editor
- Linux File Types
- Linux Filters
- Linux Log Files
- Search & Replace

**Next Module**

- IO & Directions