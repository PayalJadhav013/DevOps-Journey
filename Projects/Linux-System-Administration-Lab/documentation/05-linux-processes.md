# Part 5 — Linux Processes

## Objective

Practice Linux process management by viewing running processes, monitoring system activity, searching for specific processes, identifying process IDs (PIDs), and terminating processes.

---

## 1. Monitor Processes Using `top`

The `top` command provides a real-time view of running processes and system resource usage.

```bash
top
```
During the practice, the system showed:
```text
Tasks: 127 total,   1 running, 126 sleeping,   0 stopped,   0 zombie
```
This showed that the system currently had no zombie processes.

The `top` command also displayed CPU and memory utilization and individual process information.

## 2. Display Running Processes

Used `ps` aux to display detailed information about running processes:
```bash
ps aux
```
This displays information such as:
- User
- Process ID (PID)
- CPU usage
- Memory usage
- Process status
- Command

## 3. Display Processes Using `ps -ef`

Used:
```bash
ps -ef
```
This displays processes in full-format listing.

Important columns include:

- UID
- PID
- PPID
- CPU start time
- Terminal
- Process time
- Command

## 4. Search for Apache Processes

Searched for Apache (httpd) processes:
```bash
ps -ef | grep httpd
```
This displays processes containing httpd.

To avoid displaying the grep command itself:
```bash
ps -ef | grep httpd | grep -v 'grep'
```
## 5. Identify Apache Process IDs

Used awk to extract only the process IDs:
```bash
ps -ef | grep httpd | grep -v 'grep' | awk '{print $2}'
```
Example output:
```text
614
701
706
707
708
```
The numbers represent the PIDs of the Apache processes.

## 6. Terminate a Process

A process can be terminated using its PID:
```bash
kill PID
```
Example:
```text
kill 4280
```
The kill command sends a termination signal to the specified process.

## 7. Force Terminate a Process

Used:
```bash
kill -9 PID
```
Example:
```text
kill -9 4511
```
Signal -9 sends SIGKILL, which immediately terminates the process and cannot be caught or ignored by the process.

## 8. Kill Multiple Processes

Used awk and `xargs` to extract Apache PIDs and terminate multiple processes:
```bash
ps -ef | grep httpd | grep -v 'grep' | awk '{print $2}' | xargs kill -9
```
The command works as follows:
```text
ps -ef
   ↓
Find running processes

grep httpd
   ↓
Find Apache processes

grep -v 'grep'
   ↓
Remove the grep process from the results

awk '{print $2}'
   ↓
Extract the PID

xargs kill -9
   ↓
Forcefully terminate the selected processes
```
## 9. Process ID (PID)

Every running process in Linux has a unique Process ID (PID).

Example:
```text
root   614   ... /usr/sbin/httpd -DFOREGROUND
```
Here:
```text
614 → PID
```
PIDs are used to identify and manage individual processes.

## 10. Parent Process ID (PPID)

Linux processes also have a Parent Process ID (PPID).

Example:
```text
PID     PPID
3381    3380
```
The PPID identifies the process that created the current process.

## 11. Orphan Processes

An orphan process is a process whose parent process has terminated while the child process is still running.

Linux reassigns orphan processes to another system process, traditionally PID 1.

## Concept Practiced
- Parent process
- Child process
- Process adoption
- PID 1

## 12. Zombie Processes

A zombie process is a process that has finished execution but still has an entry in the process table because its parent has not yet collected its exit status.

The top output during the practice showed:
```text
0 zombie
```
Therefore, no zombie processes were present at that time.

---

## Commands Practiced

| Command | Purpose |
|---|---|
| `top` | Monitor processes and system resources |
| `ps aux` | Display detailed process information |
| `ps -ef` | Display full-format process information |
| `ps -ef` | grep httpd	Search for Apache processes |
| `grep -v 'grep'| Exclude the grep process |
| `kill PID`| Send a termination signal to a process |
| `kill -9 PID` | Forcefully terminate a process |
| `awk '{print $2}'` | Extract the PID column |
|`xargs kill -9` | Pass multiple PIDs to kill -9 |

---

## Concepts Practiced
- Linux processes
- Process IDs (PID)
- Parent Process IDs (PPID)
- Process monitoring
- Process searching
- Apache process management
- Graceful process termination
- Forceful process termination
- grep
- awk
- xargs
- Orphan processes
- Zombie processes

## Troubleshooting

During the practice, a process ID was passed to kill -9 after the process had already terminated.

Example:
```bash
ps -ef | grep httpd | grep -v 'grep' | awk '{print $2}' | xargs kill -9 3381
```
The system returned:
```text
kill: sending signal to 3381 failed: No such process
```
This means that PID 3381 no longer existed when the command attempted to terminate it.

This demonstrates that process IDs can change or disappear as processes start and terminate.

---

## Status

✅ **Part 5** — Linux Processes Completed