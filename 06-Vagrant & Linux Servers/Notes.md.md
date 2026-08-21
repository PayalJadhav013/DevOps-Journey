# Vagrant & Linux Servers Notes

## 1. Vagrant IP, RAM & CPU

Vagrant is used to create and manage virtual machines using a `Vagrantfile`.

### Vagrant Commands

Check Vagrant version:

```bash
vagrant --version
```

Initialize a Vagrant project:

```bash
vagrant init ubuntu/jammy64
```

Start the virtual machine:

```bash
vagrant up
```

Check VM status:

```bash
vagrant status
```

Connect to the VM:

```bash
vagrant ssh
```

Stop the VM:

```bash
vagrant halt
```

Restart the VM:

```bash
vagrant reload
```

Destroy the VM:

```bash
vagrant destroy
```

### Configure IP, RAM & CPU

Example configuration in `Vagrantfile`:

```ruby
config.vm.network "private_network", ip: "192.168.56.17"

config.vm.provider "virtualbox" do |vb|
  vb.memory = 1024
  vb.cpus = 2
end
```

- `ip` → Sets the VM private IP address
- `memory` → Allocates RAM to the VM
- `cpus` → Allocates CPU cores to the VM

---

## 2. Vagrant Sync Directories

Vagrant synced directories allow files from the host machine to be shared with the virtual machine.

Example:

```ruby
config.vm.synced_folder "./data", "/vagrant_data"
```

Here:

- `./data` → Directory on the host machine
- `/vagrant_data` → Directory inside the VM

The default synced directory is:

```text
/vagrant
```

Check the synced directory inside the VM:

```bash
ls /vagrant
```

---

## 3. Vagrant Provisioning

Provisioning is used to automatically configure a virtual machine after it is created.

Example:

```ruby
config.vm.provision "shell", inline: <<-SHELL
  yum install httpd -y
  systemctl start httpd
  systemctl enable httpd
SHELL
```

Run provisioning:

```bash
vagrant provision
```

Provisioning can be used to:

- Install packages
- Configure services
- Create files
- Prepare the server environment

---

# 4. Website Setup

## Change Hostname

Edit the hostname file:

```bash
vi /etc/hostname
```

Set the hostname:

```bash
hostname finance
```

Exit the server:

```bash
exit
```

---

## Check Linux OS

```bash
cat /etc/os-release
```

Displays information about the Linux distribution.

---

## Install Required Packages

```bash
yum install httpd wget vim unzip zip -y
```

Installs Apache HTTP Server, wget, Vim, unzip, and zip.

---

## Start and Enable Apache

```bash
systemctl start httpd
systemctl enable httpd
```

---

## Check Server IP

```bash
ip addr show
```

Displays network interfaces and IP addresses.

---

## Website Directory

Apache website files are stored in:

```bash
/var/www/html/
```

Move to the website directory:

```bash
cd /var/www/html/
```

Create or edit the main page:

```bash
vim index.html
```

Restart Apache:

```bash
systemctl restart httpd
```

---

## Download Website Template

Move to the temporary directory:

```bash
cd /tmp/
```

Download the website template:

```bash
wget https://www.tooplate.com/zip-templates/2108_dashboard.zip
```

Check the downloaded file:

```bash
ls
```

Extract the template:

```bash
unzip 2108_dashboard.zip
```

Move into the extracted directory:

```bash
cd 2108_dashboard/
```

Check the directory:

```bash
pwd
ls
```

---

## Deploy Website

Copy the website files to Apache's document root:

```bash
cp -r * /var/www/html/
```

Check the website files:

```bash
ls /var/www/html/
```

Restart Apache:

```bash
systemctl restart httpd
```

Check Apache status:

```bash
systemctl status httpd
```

---

## Check Firewall

```bash
systemctl status firewalld
```

Checks the status of the Linux firewall service.

---

# Practical Commands Practiced

```bash
vagrant --version
vagrant init ubuntu/jammy64
vagrant up
vagrant status
vagrant ssh
vagrant halt
vagrant reload
vagrant destroy
vagrant provision
ls /vagrant
vi /etc/hostname
hostname finance
cat /etc/os-release
yum install httpd wget vim unzip zip -y
systemctl start httpd
systemctl enable httpd
systemctl restart httpd
systemctl status httpd
ip addr show
cd /var/www/html/
ls
vim index.html
cd /tmp/
wget https://www.tooplate.com/zip-templates/2108_dashboard.zip
ls
unzip 2108_dashboard.zip
cd 2108_dashboard/
pwd
ls
cp -r * /var/www/html/
ls /var/www/html/
systemctl status firewalld
```
---

# Module Status

**Status:** 🚧 In Progress

**Practical Work:** Vagrant configuration and Linux server website setup practiced with screenshots saved in the `screenshots/` folder.