# Part 2 — File Permissions

## Objective

Practice Linux file and directory permissions using numeric and symbolic methods. Also practice user/group ownership and verify permissions by accessing the directories as a different user.

---

## 1. Create Project Directories

Created the main project directory and four subdirectories:

```bash
mkdir -p /opt/devops-project/{scripts,logs,backup,configs}
```
Verify:
```bash
ls -l /opt/devops-project/
```
The following directories were created:
```text
backup
configs
logs
scripts
```
## 2. Create User

Created a user named ansible:
```bash
useradd ansible
```
Verify:
```bash
id ansible
```
## 3. Add User to Existing Group

The devops group was already created during Part 1.

Added ansible to the devops supplementary group:
```bash
usermod -aG devops ansible
```
Verify:
```bash
id ansible
```
Output:
```text
uid=1002(ansible) gid=1002(ansible) groups=1002(ansible),1006(devops)
```
## 4. Change Ownership

Changed the owner and group of the project directory:
```bash
chown -R ansible:devops /opt/devops-project/
```
Verify:
```bash
ls -ld /opt/devops-project
```
The project directory is owned by:
```text
ansible:devops
```
## 5. Numeric Permission Method

Applied different numeric permissions to the directories:
```bash
chmod 755 /opt/devops-project/scripts
chmod 750 /opt/devops-project/logs
chmod 700 /opt/devops-project/backup
chmod 640 /opt/devops-project/configs
```
Verify:
```bash
ls -ld /opt/devops-project/*
```
### Permission Correction

The configs directory initially used:
```bash
chmod 640 /opt/devops-project/configs
```
This resulted in:
```text
drw-r-----
```
Since directories generally require execute (x) permission for access, the permission was corrected to:
```bash
chmod 750 /opt/devops-project/configs
```
## 6. Symbolic Permission Method

Modified permissions using the symbolic method.

Give group write permission to logs:
```bash
chmod g+w /opt/devops-project/logs
```
Remove read permission from others for configs:
```bash
chmod o-r /opt/devops-project/configs
```
Add execute permission for the owner of scripts:
```bash
chmod u+x /opt/devops-project/scripts
```
Verify:
```bash
ls -ld /opt/devops-project/*
```
Final permissions:
```text
backup   → 700
configs  → 750
logs     → 770
scripts  → 755
```
## 7. Test Permissions as ansible

Switch to the ansible user:
```bash
su - ansible
```
Verify the current user:
```bash
whoami
```
Output:
```text
ansible
```
Navigate through the project directories:
```text
cd /opt/devops-project
cd scripts
cd ../logs
cd ../backup
cd ../configs
```
The directories could be accessed successfully by the owner ansible.

Exit the user:
```bash
exit
```
---
## Concepts Practiced
- Linux file and directory permissions
- User, group, and others permissions
- Numeric permission method
- Symbolic permission method
- chmod
- chown
- User and group ownership
- Supplementary groups
- Permission verification using ls -ld
- Testing permissions with another user
---
Final Verification
```bash
ls -ld /opt/devops-project/*
```
Final structure:
```text
/opt/devops-project/
├── backup/
├── configs/
├── logs/
└── scripts/
```
Ownership:
```text
ansible:devops
```
Permissions:
```text
backup   → 700
configs  → 750
logs     → 770
scripts  → 755
Status
```
---
## Status
✅ **Part 2** — File Permissions Completed