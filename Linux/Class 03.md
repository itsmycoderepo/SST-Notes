# 📖 Class 03 - Umask, Sudo, Users, Groups, Ownership & Linux Architecture
**Date:** 05-05-2026

---

# 🔐 Umask

`umask` defines the **default permissions** assigned to newly created files and directories.

---

## Default Permissions

### Files

```text
666
```

Meaning:

```text
rw-rw-rw-
```

---

### Directories

```text
777
```

Meaning:

```text
rwxrwxrwx
```

---

## Example: Umask Calculation

### Current Umask

```bash
umask 002
```

Calculation:

```text
Files:

666
002
---
664

Directories:

777
002
---
775
```

Result:

```text
File      : 664
Directory : 775
```

---

## View Current Umask

```bash
umask
```

---

## Change Umask Temporarily

### Syntax

```bash
umask <value>
```

### Example

```bash
umask 000
```

Calculation:

```text
Files:

666
000
---
666

Directories:

777
000
---
777
```

---

## Make Umask Permanent

Edit:

```bash
sudo vi /etc/profile
```

Add:

```bash
umask 002
```

Save and restart the session.

---

# 🚀 Sudo

`sudo` stands for:

```text
Super User Do
```

It allows a normal user to execute commands with root privileges.

---

## Run a Command as Root

### Syntax

```bash
sudo <command>
```

### Example

```bash
sudo yum install git
```

---

## Switch to Root User

```bash
sudo su -
```

---

## Exit Root User

```bash
exit
```

Returns to the previous user.

---

# 👤 User Management

Linux is a multi-user operating system.

---

## Create a User

### Syntax

```bash
sudo useradd <user_name>
```

### Example

```bash
sudo useradd ss
```

---

## Set Password

### Syntax

```bash
sudo passwd <user_name>
```

### Example

```bash
sudo passwd ss
```

---

## Delete User

### Syntax

```bash
sudo userdel <user_name>
```

### Example

```bash
sudo userdel ss
```

---

# 📋 List All Users

### Method 1

```bash
getent passwd
```

### Method 2

```bash
cat /etc/passwd
```

---

## User Entry Format

Example:

```text
ss:x:1001:1001::/home/ss:/bin/bash
```

Format:

```text
username:x:UID:GID::Home_Directory:Shell
```

### Explanation

| Field | Description |
|---------|------------|
| username | User name |
| UID | User ID |
| GID | Group ID |
| Home Directory | User's home folder |
| Shell | Default shell |

---

# 🔄 Switch User

### Syntax

```bash
su - <user_name>
```

### Example

```bash
su - ss
```

---

## Why Use `-` ?

The `-`:

- Loads user environment variables
- Switches to user's home directory

Without `-`, only the user changes.

---

# 🛡️ Granting Sudo Access

To provide sudo permission:

Edit:

```bash
sudo vi /etc/sudoers
```

---

## User-Level Sudo Access

```text
ss ALL=(ALL) NOPASSWD: ALL
```

Meaning:

- User `ss`
- Can execute any command
- No password required

---

## Group-Level Sudo Access

```text
%training ALL=(ALL) NOPASSWD: ALL
```

Meaning:

- Every user in group `training`
- Gets sudo access

---

# 🔑 Enable Password Authentication

Become root:

```bash
sudo su -
```

Edit SSH configuration:

```bash
vi /etc/ssh/sshd_config
```

Change:

```text
PasswordAuthentication yes
```

Restart SSH:

```bash
systemctl restart sshd
```

---

# 👥 Group Management

Groups help manage multiple users together.

---

## Create Group

### Syntax

```bash
sudo groupadd <group_name>
```

### Example

```bash
sudo groupadd training
```

---

## Delete Group

### Syntax

```bash
sudo groupdel <group_name>
```

### Example

```bash
sudo groupdel training
```

---

# 📋 List All Groups

### Method 1

```bash
getent group
```

### Method 2

```bash
cat /etc/group
```

---

## Important Note

> When a user is created, Linux automatically creates a group with the same name.

Example:

```bash
useradd ss
```

Creates:

```text
User  : ss
Group : ss
```

---

# ➕ Add User to Group

### Syntax

```bash
sudo usermod -aG <group_name> <user_name>
```

### Example

```bash
sudo usermod -aG training ss
```

Meaning:

```text
training → Group
ss       → User
```

---

# 📁 Ownership

Example:

```text
-rw-r--r-- 1 ec2-user ec2-user 0 Jun 21 03:10 f1
```

---

## Components

| Field | Description |
|---------|------------|
| Permission | Access Rights |
| User | Owner |
| Group | Group Owner |
| Size | File Size |
| Date | Creation/Modification Date |
| File | File Name |

---

# 👤 Change Owner

### Syntax

```bash
chown <user_name> <file>
```

### Example

```bash
chown ss f1
```

---

# 👥 Change Group

### Syntax

```bash
chgrp <group_name> <file>
```

### Example

```bash
chgrp training f1
```

---

# 🔄 Change Owner and Group Together

### Syntax

```bash
chown -R <user>:<group> <file_or_directory>
```

### Example

```bash
chown -R ss:training f4
```

---

# 🏗️ Linux Architecture

Linux architecture consists of multiple layers.

```text
Hardware
   ↓
Kernel
   ↓
Shell
   ↓
Applications
   ↓
User
```

---

## Hardware

Physical resources:

- CPU
- RAM
- Storage

---

## Kernel

The core component of Linux.

Responsibilities:

- Memory Management
- Process Management
- Device Management
- File System Management

---

### Important Note

> If the kernel crashes, the system becomes unusable and users cannot connect to the server.

---

## Shell

The interface between:

```text
User ↔ Kernel
```

The shell:

- Accepts commands
- Sends them to kernel
- Displays output

Example:

```bash
free -h
```

---

# 🖥️ System Information Commands

---

## Who Is Logged In

```bash
who
```

Displays all logged-in users.

---

## Current User

```bash
whoami
```

Displays current user.

---

## Hostname

```bash
hostname
```

Displays hostname.

---

## Short Hostname

```bash
hostname -s
```

Displays short hostname.

---

## Public IP

```bash
curl ifconfig.me
```

Displays public IP address.

---

## Operating System

```bash
uname
```

Displays operating system name.

---

## Full OS Information

```bash
uname -a
```

Displays complete system information.

---

## Kernel Version

```bash
uname -r
```

Displays kernel version.

---

## Memory Usage

```bash
free -h
```

Displays RAM usage.

---

## Disk Usage

```bash
df -h
```

Displays disk usage.

---

## CPU Count

```bash
nproc
```

Displays number of CPUs.

---

## File/Directory Size

### Syntax

```bash
du -sh <file_or_directory>
```

### Example

```bash
du -sh demo
```

---

# 📝 Assignment

### 1. List Volume Blocks

Research:

```bash
lsblk
```

---

### 2. What is Sticky Bit?

Learn:

```text
Sticky Bit
```

and its use in shared directories.

---

### 3. Create a User With Sudo Access

Requirements:

- Create user
- Provide sudo permission
- Install Git

---

### 4. Check Login History

Find:

- Logged-in users
- Last logged-in user

Commands to explore:

```bash
last
who
```

---

### 5. Extend Password Validity for 30 Days

Research:

```bash
chage
```

---

### 6. Change User Password

Practice:

```bash
passwd
```

---

# 📚 Quick Command Cheat Sheet

| Command | Description |
|----------|------------|
| `umask` | Default permissions |
| `sudo` | Execute as root |
| `useradd` | Create user |
| `passwd` | Set password |
| `userdel` | Delete user |
| `su -` | Switch user |
| `groupadd` | Create group |
| `groupdel` | Delete group |
| `usermod -aG` | Add user to group |
| `chown` | Change owner |
| `chgrp` | Change group |
| `who` | Logged-in users |
| `whoami` | Current user |
| `hostname` | Host name |
| `uname` | OS information |
| `free -h` | Memory usage |
| `df -h` | Disk usage |
| `nproc` | CPU count |
| `du -sh` | File/Directory size |

---

> 💡 **DevOps Tip**
>
> Always use:
>
> ```bash
> sudo visudo
> ```
>
> instead of directly editing:
>
> ```bash
> /etc/sudoers
> ```
>
> because it validates syntax before saving and prevents sudo access issues.
