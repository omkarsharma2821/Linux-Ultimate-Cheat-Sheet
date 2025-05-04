# Who Controls Your Files in Linux? Discover the Power of Permissions 🔐

When working in a multi-user Linux environment, not everything is open to everyone—and that’s for a reason. File permissions are a cornerstone of Linux security, ensuring that only the right people can access or modify critical files. Whether you're a budding sysadmin or a curious developer, understanding how Linux handles file access is crucial to maintaining control and security.

Let’s break it down 👇

---

## 🔑 Introduction to File Permissions

Linux file permissions determine **who** can **read**, **write**, or **execute** files and directories. Each file or directory is governed by three levels of access:

- **Owner (User)** – The creator of the file.
- **Group** – Users who belong to the assigned group.
- **Others** – Everyone else.

Permissions are represented in two ways:

- **Read (r or 4)** – View file contents.
- **Write (w or 2)** – Modify file contents.
- **Execute (x or 1)** – Run the file as a program or script.

---

## 🛠️ Changing Permissions with `chmod`

### 🔹 Symbolic Mode

You can modify permissions using symbols:

- **+** to add  
- **-** to remove  
- **=** to set exactly

**Examples:**
```bash
chmod u+x filename        # Add execute for user  
chmod g-w filename        # Remove write for group  
chmod o=r filename        # Set read-only for others  
chmod u=rwx,g=rx,o= filename  # Full for user, read/execute for group, none for others  
```

## 🔢 Numeric (Octal) Mode
Each permission has a value:

- Read = 4
- Write = 2
- Execute = 1

Add the values to define access levels.

**Examples:**

```
chmod 755 filename  # User (rwx), Group (r-x), Others (r-x)  
chmod 644 filename  # User (rw-), Group (r--), Others (r--)  
chmod 700 filename  # User (rwx), No access for group/others 
```
 
## 👤 Changing Ownership with chown

The chown command is used to modify the file owner and group.

**Examples:**

```
chown newuser filename             # Change owner  
chown newuser:newgroup filename   # Change owner and group  
chown :newgroup filename          # Change only group  
```
Recursively change ownership:

```
chown -R newuser:newgroup directory/
```
## 👥 Changing Group Ownership with chgrp
To change only the group without affecting the owner:

**Examples:**

```bash
chgrp newgroup filename           # Change group  
chgrp -R newgroup directory/      # Recursively change group
```