## Confused by the Linux Directory Tree? Here's What You Need to Know

Before diving into the Linux folder hierarchy, let’s first look at what you see when you open a terminal on a Linux system.

When you're logged in as root on a local Linux machine, you’ll typically see something like:

![root directory](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ru20n4hf35mta8iwndo9.png)

This tells us:

- root – the username you're logged in as.
- hostname – the name of the machine.
- / – the current directory (this is the root directory).
- #-signifies you're logged in as the root user (administrator privileges).

If you're using an AWS EC2 Ubuntu instance, the prompt might look like:

```
ubuntu@ip-<your-ec2-ip>:~$
```

Here:

- ubuntu – the default user.
- ip-<your-ec2-ip> – your instance’s hostname.
- ~ – your current directory, which is the home directory of the ubuntu user.
- $ – indicates you're a normal (non-root) user.

To explore the system folders fully, switch to the root user:

```
sudo su
```
Then navigate to the root directory:

```
cd /
```

## **Understanding the Folder Structure**
**Explanation of System Directories**

```
Directory	Description
/sbin -> /usr/sbin	System binaries for administrative commands (linked to /usr/sbin).
/bin -> /usr/bin	Essential user binaries (linked to /usr/bin).
/lib -> /usr/lib	Shared libraries and kernel modules (linked to /usr/lib).
```
**Important System Directories**
```
Directory	Description
/boot	Stores files needed for booting the system (not relevant in containers).
/usr	Contains most user-installed applications and libraries.
/var	Stores logs, caches, and temporary files that change frequently.
/etc	Stores system configuration files.
```
**User & Application-Specific Directories**

```
Directory	Description
/home	Default location for user home directories.
/opt	Used for installing optional third-party software.
/srv	Holds data for services like web servers (rarely used in containers).
/root	Home directory for the root user.
```
**Temporary & Volatile Directories**

```
Directory	Description
/tmp	Temporary files (cleared on reboot).
/run	Holds runtime data for processes.
/proc	Virtual filesystem for process and system information.
/sys	Virtual filesystem for hardware and kernel information.
/dev	Contains device files (e.g., /dev/null, /dev/sda).
```
**Mount Points**

```
Directory	Description
/mnt	Temporary mount point for external filesystems.
/media	Mount point for removable media (USB, CDs).
/data	Likely your mounted volume from Windows (C:/ubuntu-data).
```
