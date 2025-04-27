## User Management in Linux
Linux is a multi-user operating system, meaning multiple users can operate on a system simultaneously. Proper user management ensures security, controlled access, and system integrity.

## Types of Users in Linux

- **Root User / Superuser**:  Has full control over the system. Can perform any task such as installing software, changing system settings, and managing other users.

- **Regular User / Standard User**:  Has limited access. Can read, write, and execute files, but restricted from critical system areas.

- **System User**:  Non-human users that run background services and processes. These accounts are intangible to regular users.

## Key Files Involved in User Management

- `/etc/passwd` – Stores user account details.
- `/etc/shadow` – Stores encrypted user passwords.
- `/etc/group` – Stores group information.
- `/etc/gshadow` – Stores secure group details.

## Commands for Creating Users and Groups

- Create a new user:
  ```bash
  useradd username
  ```

- Create a user with a specific UID:
  ```bash
  useradd -u UID username
  ```

- Create a new group:
  ```bash
  groupadd groupname
  ```

- Create a group with a specific GID:
  ```bash
  groupadd -g GID groupname
  ```
## Managing User Passwords
- To set or change a user’s password:

```
passwd username
```

## Enforcing Password Policies

 - Password expiration: Set password expiry days

```
chage -M 90 username
```
- Lock a user account

```
passwd -l username

```
- Unlock a user account

```
passwd -u username
```
## Modifying Users and Groups

- Change an existing username:
  ```bash
  usermod -l new_username old_username
  ```

- Change an existing group name:
  ```bash
  groupmod -n new_groupname old_groupname
  ```

- Check groups a user belongs to:
  ```bash
  groups username
  ```

- Create a user with a specific UID and primary group (group must exist):
  ```bash
  useradd -u UID -g groupname username
  ```
  or
  ```bash
  useradd -u UID -g GID username
  ```

- Append a user to another group (without removing them from existing groups):
  ```bash
  usermod -aG groupname username
  ```

- Change a user’s UID:
  ```bash
  usermod -u UID username
  ```

- Change a user’s primary GID:
  ```bash
  usermod -g GID username
  ```
## Deleting Users

- To remove a user but keep their home directory:

```
userdel username
```
- To remove a user and their home directory:

```
userdel -r username
```

![Linux meme](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/h4i5x4cwezpsf88ghxem.jpg)