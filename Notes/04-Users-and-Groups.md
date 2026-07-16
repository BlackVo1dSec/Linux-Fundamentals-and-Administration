# 04 - Users and Groups

> **Module:** Linux Fundamentals & Administration
> **Status:** 🟡 In Progress
> **Difficulty:** Beginner → Intermediate
> **Last Updated:** YYYY-MM-DD

---

# Learning Objectives

By the end of this chapter I should be able to:

- [ ] Understand users and groups.
- [ ] Explain the difference between root and regular users.
- [ ] Create and manage users.
- [ ] Create and manage groups.
- [ ] Change ownership of files and directories.
- [ ] Understand Linux permissions.
- [ ] Use sudo safely.

---

# Topic Overview

Write a short summary of what this topic is about.

Example:

Linux is a multi-user operating system where every file, process, and service belongs to a user and a group. Proper user and group management is essential for security, collaboration, and system administration.

---

# Key Concepts

## User

### Definition

A user is an account that can log into the Linux system.

### Notes

- Has a unique username.
- Identified by a User ID (UID).
- Owns files and processes.

---

## Group

### Definition

A collection of users that share permissions.

### Notes

- Identified by a Group ID (GID).
- Simplifies permission management.

---

## Root User

### Definition

The superuser with unrestricted access.

### Notes

- Username: `root`
- UID: `0`
- Can modify any file or configuration.

⚠️ Be careful when working as root.

---

## Regular User

### Notes

- Limited permissions.
- Uses `sudo` for administrative tasks.
- Safer for everyday work.

---

# Important Files

| File | Purpose |
|------|---------|
| `/etc/passwd` | User account information |
| `/etc/shadow` | Encrypted passwords |
| `/etc/group` | Group information |
| `/etc/gshadow` | Group passwords |

---

# Commands Learned

## whoami

### Purpose

Displays the current logged-in user.

```bash
whoami
```

Example Output

```text
blackvoid
```

Notes

-

---

## id

### Purpose

Displays user and group IDs.

```bash
id
```

Example Output

```text
uid=1000(user)
gid=1000(user)
groups=1000(user),27(sudo)
```

Notes

-

---

## sudo

### Purpose

Run commands with administrator privileges.

```bash
sudo apt update
```

Notes

- Requires authorization.
- Use only when necessary.

---

## useradd

### Purpose

Create a new user.

```bash
sudo useradd username
```

Notes

-

---

## adduser

### Purpose

Interactive user creation.

```bash
sudo adduser username
```

Notes

-

---

## passwd

### Purpose

Set or change a password.

```bash
passwd username
```

Notes

-

---

## usermod

### Purpose

Modify an existing user.

Example

```bash
sudo usermod -aG sudo username
```

Notes

-

---

## groupadd

### Purpose

Create a new group.

```bash
sudo groupadd developers
```

Notes

-

---

## groups

### Purpose

Display group membership.

```bash
groups
```

Notes

-

---

## chown

### Purpose

Change file ownership.

```bash
sudo chown user:filegroup filename
```

Notes

-

---

## chgrp

### Purpose

Change group ownership.

```bash
chgrp developers filename
```

Notes

-

---

# Common Command Options

| Option | Meaning |
|---------|---------|
| `-a` | Append |
| `-G` | Supplementary groups |
| `-g` | Primary group |
| `-r` | Recursive |
| `-R` | Recursive (directories) |
| `-m` | Create home directory |

---

# User Management Workflow

```text
Create User
      │
      ▼
Assign Password
      │
      ▼
Assign Group
      │
      ▼
Grant sudo (if required)
      │
      ▼
Verify with id
```

---

# Practical Exercises

## Exercise 1

Check your current user.

```bash
whoami
```

Result

```
_____________________________________
```

---

## Exercise 2

View your UID and groups.

```bash
id
```

Result

```
_____________________________________
```

---

## Exercise 3

List your groups.

```bash
groups
```

Result

```
_____________________________________
```

---

## Exercise 4

View user information.

```bash
cat /etc/passwd
```

Observations

```
_____________________________________
```

---

## Exercise 5

View groups.

```bash
cat /etc/group
```

Observations

```
_____________________________________
```

---

# Real-World Examples

## Create a User

```bash
sudo adduser alice
```

---

## Add User to sudo Group

```bash
sudo usermod -aG sudo alice
```

---

## Create Developers Group

```bash
sudo groupadd developers
```

---

## Add User to Group

```bash
sudo usermod -aG developers alice
```

---

## Change Ownership

```bash
sudo chown alice:developers project/
```

---

# Common Mistakes

- Forgetting `-a` when using `usermod -G`.
- Running everything as root.
- Changing ownership of the wrong directory.
- Forgetting to verify group membership.
- Editing `/etc/passwd` manually without care.

---

# Best Practices

- Use regular accounts for daily work.
- Use `sudo` only when needed.
- Give users the minimum permissions required.
- Organize users into groups instead of assigning permissions individually.
- Verify changes after modifying users or groups.

---

# My Notes

Write down discoveries from your labs.

Example

- UID `0` always belongs to root.
- Every user has a primary group.
- `sudo` logs administrative actions.

---

# Cheat Sheet

| Command | Purpose |
|----------|---------|
| `whoami` | Current user |
| `id` | User and group IDs |
| `groups` | List groups |
| `sudo` | Run as administrator |
| `adduser` | Create user |
| `useradd` | Create user (basic) |
| `passwd` | Change password |
| `usermod` | Modify user |
| `groupadd` | Create group |
| `groupdel` | Delete group |
| `chown` | Change owner |
| `chgrp` | Change group |

---

# Knowledge Check

Can I answer these?

- [ ] What is a UID?
- [ ] What is a GID?
- [ ] Why should you avoid logging in as root?
- [ ] Difference between `useradd` and `adduser`?
- [ ] What does `sudo` do?
- [ ] How do you add a user to a group?
- [ ] How do you change file ownership?
- [ ] What files store user and group information?

---

# Lab Challenges

## Beginner

- [ ] Display your username.
- [ ] Display your UID.
- [ ] List your groups.

---

## Intermediate

- [ ] Create a test user.
- [ ] Create a test group.
- [ ] Add the user to the group.
- [ ] Verify membership.

---

## Advanced

- [ ] Create multiple users.
- [ ] Organize them into groups.
- [ ] Assign ownership of a project directory.
- [ ] Verify permissions.

---

# Revision Log

| Date | What I Learned |
|------|----------------|
| YYYY-MM-DD | Learned users and groups |
| YYYY-MM-DD | Practiced user management |
| YYYY-MM-DD | Practiced ownership |
| YYYY-MM-DD | Practiced sudo |

---

# Completion Checklist

- [ ] Read the material
- [ ] Practiced every command
- [ ] Completed all labs
- [ ] Understood users and groups
- [ ] Understand ownership
- [ ] Understand sudo
- [ ] Can explain the concepts without notes
