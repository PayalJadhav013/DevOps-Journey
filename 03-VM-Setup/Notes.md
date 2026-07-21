# 📝 Virtual Machine (VM) Setup Notes

## What is Virtualization?

Virtualization is the process of creating a virtual version of a physical computer. It allows multiple operating systems to run independently on a single physical machine.

### Benefits of Virtualization

- Better hardware utilization
- Cost reduction
- Easy testing and development
- Isolation between environments
- Faster deployment
- Supports cloud computing

---

# Hypervisor

A hypervisor is software that creates and manages virtual machines.

## Types of Hypervisors

### Type 1 (Bare Metal)

Runs directly on physical hardware.

Examples:
- VMware ESXi
- Microsoft Hyper-V
- Xen Server

### Type 2 (Hosted)

Runs on top of an existing operating system.

Examples:
- Oracle VM VirtualBox
- VMware Workstation
- VMware Player

---

# Oracle VM VirtualBox

Oracle VM VirtualBox is a free and open-source Type 2 hypervisor used to create and manage virtual machines.

### Features

- Cross-platform support
- Snapshot functionality
- Shared folders
- USB support
- Multiple operating system support

---

# Virtual Machine (VM)

A Virtual Machine is a software-based computer that behaves like a physical computer.

Each VM has its own:

- CPU
- RAM
- Storage
- Network
- Operating System

---

# Manual VM Creation

Steps followed:

1. Install Oracle VM VirtualBox.
2. Download Ubuntu ISO image.
3. Create a new virtual machine.
4. Allocate RAM.
5. Create a virtual hard disk.
6. Attach Ubuntu ISO.
7. Install Ubuntu.
8. Login to Ubuntu.

---

# What is Vagrant?

Vagrant is an open-source tool used to automate the creation and management of virtual machines.

Instead of creating VMs manually every time, Vagrant creates identical environments using a configuration file called **Vagrantfile**.

---

# Advantages of Vagrant

- Infrastructure as Code (IaC)
- Repeatable environments
- Easy collaboration
- Faster VM provisioning
- Supports multiple providers
- Version-controlled environments

---

# Vagrant Workflow

```
Vagrantfile
      │
      ▼
vagrant up
      │
      ▼
Virtual Machine Created
      │
      ▼
vagrant ssh
      │
      ▼
Access Linux VM
```

---

# Vagrant Commands

## Check Version

```bash
vagrant --version
```

Displays the installed Vagrant version.

---

## Initialize a Project

```bash
vagrant init
```

Creates a default `Vagrantfile`.

---

## Start Virtual Machine

```bash
vagrant up
```

Downloads the configured box (if required) and starts the VM.

---

## Connect to VM

```bash
vagrant ssh
```

Logs into the Linux virtual machine.

---

## Check VM Status

```bash
vagrant status
```

Displays the current state of the VM.

---

## Reload VM

```bash
vagrant reload
```

Restarts the VM and applies any configuration changes.

---

## Suspend VM

```bash
vagrant suspend
```

Pauses the VM while preserving its current state.

---

## Resume VM

```bash
vagrant resume
```

Resumes a suspended VM.

---

## Stop VM

```bash
vagrant halt
```

Gracefully shuts down the virtual machine.

---

## Destroy VM

```bash
vagrant destroy
```

Deletes the virtual machine and frees allocated resources.

---

## Global Status

```bash
vagrant global-status
```

Lists all Vagrant virtual machines available on the system.

---

# Vagrantfile

A **Vagrantfile** is the configuration file used by Vagrant.

It defines:

- Base operating system
- Memory allocation
- CPU allocation
- Network configuration
- Shared folders
- Provisioning scripts

---

# Tools Used

- Oracle VM VirtualBox
- Ubuntu Linux
- Vagrant
- Git Bash / PowerShell
- Windows 11

---

# Learning Outcome

After completing this module, I was able to:

- Understand virtualization concepts.
- Differentiate between Type 1 and Type 2 hypervisors.
- Install and configure Oracle VM VirtualBox.
- Create Ubuntu virtual machines manually.
- Install and configure Vagrant.
- Create VMs automatically using Vagrant.
- Manage the complete VM lifecycle using Vagrant commands.
- Connect to Linux virtual machines using SSH.

---


