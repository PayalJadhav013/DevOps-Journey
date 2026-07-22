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

### Features

- Open Source
- Multi-user
- Multitasking
- Secure
- Stable
- Portable
- Command Line Interface (CLI)

### Why Linux in DevOps?

- Most cloud servers run Linux.
- Automation and scripting are easier.
- Lightweight and reliable.
- Widely used with Docker, Kubernetes, Jenkins, AWS and Terraform.

---

# 2. Linux File System

Everything in Linux is considered a file.

Root directory

```
/
```

Common directories

```
/home      User home directories
/root      Root user's home
/bin       Essential user commands
/sbin      System administration commands
/etc       Configuration files
/usr       User applications
/var       Log and variable data
/tmp       Temporary files
/dev       Device files
/proc      Process information
```

---

# 3. Basic Linux Commands

### Current directory

```bash
pwd
```

Shows the current working directory.

---

### List files

```bash
ls
```

Lists files and folders.

Useful options

```bash
ls -l
```

Long listing.

```bash
ls -a
```

Shows hidden files.

---

### Change directory

```bash
cd directory_name
```

Move into directory.

```bash
cd ..
```

Move one level back.

```bash
cd ~
```

Go to home directory.

---

### Clear terminal

```bash
clear
```

---

### Current user

```bash
whoami
```

Displays logged-in username.

---

### Command history

```bash
history
```

Displays previously executed commands.

---

# 4. File and Directory Operations

### Create Directory

```bash
mkdir project
```

Creates a new directory.

---

### Create Empty File

```bash
touch file.txt
```

---

### Copy Files

```bash
cp source destination
```

Copy directories

```bash
cp -r folder1 folder2
```

---

### Move or Rename

```bash
mv old.txt new.txt
```

---

### Delete File

```bash
rm file.txt
```

Delete directory

```bash
rm -r folder
```

---

### Display File

```bash
cat file.txt
```

---

### View Beginning

```bash
head file.txt
```

---

### View End

```bash
tail file.txt
```

---

# 5. Vim Editor

Vim is a command-line text editor.

## Modes

### Normal Mode

Default mode.

### Insert Mode

Press

```
i
```

to edit.

### Command Mode

Press

```
Esc
```

then use commands.

Save

```
:w
```

Quit

```
:q
```

Save & Quit

```
:wq
```

Quit without saving

```
:q!
```

---

# 6. Linux File Types

Linux supports different file types.

| File Type | Description |
|-----------|-------------|
| Regular File | Normal files |
| Directory | Stores files and folders |
| Symbolic Link | Shortcut to another file |
| Character Device | Keyboard, terminal |
| Block Device | Hard disk, SSD |
| Socket | Process communication |
| Named Pipe (FIFO) | Inter-process communication |

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

# Module Status

Completed:
- Linux Introduction
- Linux File System
- Basic Commands
- File Operations
- Vim Editor
- Linux File Types

Next Module:
- Users & Groups