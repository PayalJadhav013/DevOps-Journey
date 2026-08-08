# Part 1 — Users & Groups

## Objective

Practice Linux user and group management by creating a user, creating a group, assigning the user to the group, setting a password, and verifying user and group information.

---

## 1. Create a User

```bash
useradd devuser
```
Created a regular user named `devuser`.


## 2. Create a Group
```bash
groupadd devops
```
Created a group named `devops`.

## 3. Add User to Group
```bash
usermod -aG devops devuser
```
Added `devuser` to the `devops` supplementary group.

Verify:
```bash
id devuser
```
Output:
```text
uid=1001(devuser) gid=1001(devuser) groups=1001(devuser),1006(devops)
```
This confirms that `devuser` belongs to the `devops` group.

## 4. Set User Password
```bash
passwd devuser
```
A password was configured successfully for `devuser`.

## 5. Check User Groups
```bash
groups devuser
```
Output:
```text
devuser : devuser devops
```
This confirms that `devuser` belongs to both the primary group `devuser` and the supplementary group `devops`.

## 6. View Group Information
```bash
getent group
```
The command displays available groups and their members.

Relevant entry:
```text
devops:x:1006:devuser
```
This confirms that `devuser` is a member of the `devops` group.

## 7. Switch to the User
```bash
su - devuser
```
Verify the current user:
```bash
whoami
```
Output:
```text
devuser
```
Check the user's home directory:
```bash
pwd
```
Output:
```text
/home/devuser
```
---
## Concepts Practiced
- Creating Linux users
- Creating Linux groups
- Adding users to supplementary groups
- Setting user passwords
- Checking user and group information
- Switching between users
- Verifying user home directories
---

## Status

✅ **Part 1** — Users & Groups Completed