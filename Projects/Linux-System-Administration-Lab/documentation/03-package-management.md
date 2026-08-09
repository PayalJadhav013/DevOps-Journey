# Part 3 — Package Management

## Objective

Practice Linux package management using RPM and DNF by downloading, installing, querying, verifying, and removing an RPM package.

---

## 1. Download an RPM Package

Used `wget` to download the Telnet RPM package:

```bash
wget https://rpmfind.net/linux/centos-stream/9-stream/AppStream/x86_64/os/Packages/t/telnet-0.17-85.el9.x86_64.rpm
```
The package was downloaded successfully to the current directory.

## 2. Install RPM Package

Initially, an incorrect filename was used:

rpm -ivh telnet-0.17-85.el9.x86_6.rpm

This resulted in:
```text
error: open of telnet-0.17-85.el9.x86_6.rpm failed: No such file or directory
```
Checked the downloaded filename using:
```bash
ls
```
The correct filename was:
```bash
telnet-0.17-85.el9.x86_64.rpm
```
Installed the package using:
```bash
rpm -ivh telnet-0.17-85.el9.x86_64.rpm
```
The installation completed successfully.

## 3. Verify Installed Package

Checked whether the Telnet package was installed:
```bash
rpm -qa | grep telnet-0.17-85.el9.x86_64
```
Output:
```text
telnet-0.17-85.el9
```
This confirms that the Telnet RPM package was installed successfully.

## 4. Test the Telnet Command

Before installing the package, the `telnet` command was not available:
```bash
telnet
```
returned:
```text
-bash: telnet: command not found
```
After installing the correct RPM package, the package was successfully registered with RPM.

## 5. Remove Package Using DNF

Removed the Telnet package using DNF:
```bash
dnf remove telnet -y
```
DNF displayed the transaction summary:
```text
Remove  1 Package
```
The Telnet package was successfully removed.

## 6. Check Installed Package Count

Checked the number of installed RPM packages:
```bash
rpm -qa | wc -l
```
The system reported:
```text
511
```
This command counts the installed RPM packages on the system.

The exact package count can vary depending on the Linux system and installed software.

## 7. Check DNF Version

Verified the installed DNF version:
```bash
dnf --version
```
Output showed:
```text
4.14.0
```
This confirms that DNF is available and working on the system.

---
## Commands Practiced

| Command | Purpose |
|---|---|
| `wget <URL>` | Download a file from a URL |
| `ls` | List files and directories |
| `rpm -ivh <package.rpm>` | Install an RPM package |
| `rpm -qa` | List installed RPM packages |
| `rpm -qa \| grep <package>` | Search for an installed package |
| `dnf remove <package> -y` | Remove a package using DNF |
| `rpm -qa \| wc -l` | Count installed RPM packages |
| `dnf --version` | Display DNF version |
---
## Concepts Practiced
- RPM package management
- DNF package management
- Downloading RPM packages using `wget`
- Installing local RPM packages
- Verifying installed packages
- Removing packages using DNF
- Checking installed package information
- Troubleshooting incorrect package filenames
- Verifying package manager availability
---
## Troubleshooting

During the practice, an incorrect RPM filename was provided to `rpm -ivh`.

Incorrect:
```bash
rpm -ivh telnet-0.17-85.el9.x86_6.rpm
```
The system returned:
```text
No such file or directory
```
The downloaded file was checked using:
```bash
ls
```
The correct filename was identified:
```text
telnet-0.17-85.el9.x86_64.rpm
```
The package was then installed successfully.

This demonstrated the importance of checking the exact filename before installing a local RPM package.

---
## Status

✅ **Part 3** — Package Management Completed