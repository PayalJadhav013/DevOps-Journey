# Part 4 — Linux Services

## Objective

Practice managing Linux services using `systemctl` by installing Apache HTTP Server, checking its status, starting and restarting the service, enabling it at boot, and verifying its active and enabled states.

---

## 1. Install Apache HTTP Server

Installed Apache HTTP Server using `yum`:

```bash
yum install httpd -y
```
Output indicated that Apache was already installed:
```text
Package httpd-2.4.62-14.el9.x86_64 is already installed.
```
This confirms that the `httpd` package is available on the system.

## 2. Check Apache Service Status

Checked the current status of the Apache service:
```bash
systemctl status httpd
```
The service was running successfully.

Relevant output:
```text
Active: active (running)
```
The output also showed Apache worker processes running under the httpd service.

Apache was configured to listen on:
```text
port 80
```
## 3. Start Apache Service

Started the Apache service:
```bash
systemctl start httpd
```
This starts the Apache HTTP Server if it is not already running.

## 4. Restart Apache Service

Restarted Apache using:
```bash
systemctl restart httpd
```
Restarting stops and starts the service again, which is useful after configuration changes.

## 5. Reload Apache Service

Reloaded Apache configuration using:
```bash
systemctl reload httpd
```
Reloading applies configuration changes without completely stopping the service.

## 6. Enable Apache at Boot

Enabled Apache to start automatically when the system boots:
```bash
systemctl enable httpd
```
Output:
```text
Created symlink /etc/systemd/system/multi-user.target.wants/httpd.service
```
This confirms that Apache has been configured to start automatically during system boot.

## 7. Check Service Active State

Verified whether Apache is currently running:
```bash
systemctl is-active httpd
```
Output:
```text
active
```
This confirms that the Apache service is currently running.

## 8. Check Service Enabled State

Verified whether Apache is configured to start automatically at boot:
```bash
systemctl is-enabled httpd
```
Output:
```text
enabled
```
This confirms that Apache will automatically start when the system boots.

---
## Commands Practiced

| Command | Purpose |
|---|---|
| `yum install httpd -y` | Install Apache HTTP Server |
| `systemctl status httpd` | Check service status |
| `systemctl start httpd` | Start the service |
| `systemctl restart httpd` | Restart the service | 
| `systemctl reload httpd` | Reload service configuration |
| `systemctl enable httpd` | Enable service at boot |
| `systemctl is-active httpd` | Check whether service is currently active |
| `systemctl is-enabled httpd` | Check whether service starts automatically at boot |

---

## Concepts Practiced

- Linux service management
- Apache HTTP Server (httpd)
- systemctl
- Starting services
- Restarting services
- Reloading service configuration
- Checking service status
- Enabling services at boot
- Checking active service state
- Checking enabled service state

---

## Status

✅ **Part 4** — Linux Services Completed