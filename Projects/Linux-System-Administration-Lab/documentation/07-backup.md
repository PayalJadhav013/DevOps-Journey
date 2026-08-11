# Part 7 — Backup & Archiving

## Objective

Practice creating, inspecting, moving, and extracting compressed backups using `tar`, `gzip`, `zip`, and `unzip`.

---

## 1. Navigate to Log Directory

```bash
cd /var/log/
```
Check the current directory:
```bash
pwd
```
Output:
```text
/var/log
```
List the available log files and directories:
```bash
ls
```
## 2. Create a Compressed TAR Backup

Created a compressed archive of the `samba` directory:
```bash
tar -czvf samba_06122020.tar.gz samba
```
Options used

- `-c` → Create a new archive
- `-z` → Compress using `gzip`
- `-v` → Display files being processed
- `-f` → Specify the archive filename

The archive was created successfully:
```text
samba_06122020.tar.gz
```
## 3. Verify the Backup File

List the backup file:
```bash
ls -l
```
Check the file type:
```bash
file samba_06122020.tar.gz
```
Output:
```text
samba_06122020.tar.gz: gzip compressed data
```
This confirms that the file is a gzip-compressed archive.

## 4. Move the Backup to `/tmp`

Moved the backup archive from `/var/log` to `/tmp`:
```bash
mv samba_06122020.tar.gz /tmp/
```
Navigate to `/tmp`:
```bash
cd /tmp/
```
Verify the backup:
```bash
ls
```
The backup file was present:
```text
samba_06122020.tar.gz
```
## 5. Extract the TAR Backup

Extracted the compressed archive:
```bash
tar -xzvf samba_06122020.tar.gz
```
Options used
- `-x` → Extract files
- `-z` → Decompress gzip archive
- `-v` → Display extracted files
- `-f` → Specify archive file

Output:
```text
samba/
samba/old/
```
This confirms that the backup was successfully extracted.

## 6. View TAR Help

Used the following command to view available TAR options:
```bash
tar --help
```
This displays the available TAR operations, extraction options, compression options, and other parameters.

## 7. Verify the Original Directory

Returned to the log directory:
```bash
cd /var/log/
```
Checked the Samba directory:
```bash
ls
```
Verified its contents:
```bash
ls -ltr samba*
```
## 8. Install ZIP and UNZIP

Installed the required ZIP utilities:
```bash
yum install zip unzip -y
```
The system reported that both packages were already installed:
```text
Package zip-3.0-35.el9.x86_64 is already installed.
Package unzip-6.0-59.el9.x86_64 is already installed.
```
Therefore, no additional installation was required.

---

## Concepts Practiced
- Navigating `/var/log`
- Creating TAR archives
- GZIP compression
- Extracting `.tar.gz` archives
- Checking archive file types
- Moving backup files
- Viewing TAR help
- Working with ZIP and UNZIP utilities
- Troubleshooting missing archive files
- Verifying installed compression utilities

---

## Commands Practiced

| Command | Purpose |
|---|---|
| `cd /var/log/` | Navigate to log directory |
| `ls` | List files and directories |
|`pwd` | Display current directory |
| `tar -czvf` |	Create gzip-compressed TAR archive |
| `ls -l`| Display detailed file information |
| `ls -ltr`| List files by modification time |
| `file` | Identify file type |
| `mv` | Move backup file |
| `cd /tmp/` | Navigate to `/tmp` |
| `tar -xzvf` |	Extract `.tar.gz` archive |
| `tar --help` | Display TAR help |
| `unzip` | Extract ZIP archive |
| `yum install zip unzip -y` | Install ZIP/UNZIP utilities |

---
## Status

✅ **Part 7** — Backup & Archiving Completed
