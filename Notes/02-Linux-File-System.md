# 02 - Linux File System

> **Module:** Linux Fundamentals & Administration
> **Status:** 🟡 In Progress
> **Difficulty:** Beginner
> **Last Updated:** YYYY-MM-DD

---

# Learning Objectives

By the end of this section I should be able to:

- [ ] Understand the Linux file system hierarchy.
- [ ] Navigate directories efficiently.
- [ ] Identify important system directories.
- [ ] Understand absolute and relative paths.
- [ ] Locate files using Linux commands.

---

# Overview

This topic consist of the foundation and basics of a linux Operating Systems.

Topics will cover:

Linux file Hierachy
Linux navigation
Directories


The Linux file system is organized as a single hierarchical tree which begins with the root directory (`/`).

Everything in Linux is considered and treated as a file,
including hardware devices and processes.

- `/` represents the root directory
- `/dev/sda1` serves as the hardware  file for the disk partition
- `/proc/<PID>` serves as the process file which shows information for a specific process

---

# Key Concepts

## Root Directory (/)

### Definition

The starting point of the Linux file system.

### Notes

- Every directory branches from `/`
- Only the root user has unrestricted permissions.

---

## Home Directory (/home)

### Definition

Contains personal user directories.

### Notes

- Each user normally has their own folder.
- Stores documents, downloads, configuration files, etc.

---

## Important Directories

| Directory | Purpose | Notes |
|-----------|---------|------|
| `/` | Root of the filesystem | Top-level directory |
| `/home` | User files | Personal directories |
| `/root` | Root user's home | Not the same as `/` |
| `/etc` | Configuration files | System settings |
| `/bin` | Essential commands | Basic binaries |
| `/sbin` | System administration tools | Usually root only |
| `/usr` | User applications | Programs and libraries |
| `/var` | Variable data | Logs, mail, cache |
| `/tmp` | Temporary files | Often cleared automatically |
| `/dev` | Device files | Hardware interfaces |
| `/proc` | Process information | Virtual filesystem |
| `/sys` | Kernel information | Hardware and drivers |
| `/opt` | Optional software | Third-party applications |
| `/mnt` | Temporary mounts | Manual mounting |
| `/media` | External drives | USB/DVD devices |

---

# Commands Learned

## pwd

**Purpose**

Print the current users working directory.

```bash
pwd
```

- Example 

```BlackVo1d@localhost
 pwd
```

- Output
/home/blackvoid


Notes

- Shows your current location.

---

## ls

**Purpose**

List files and directories.

```bash
ls
```

Useful options

```bash
ls -l
ls -la
ls -lh
```

My Notes

-

---

## cd

**Purpose**

Change directories.

```bash
cd /home
```

Examples

```bash
cd ..
cd ~
cd /
cd -
```

My Notes

-

---

# Absolute vs Relative Paths

## Absolute Path

Starts from `/`

Example

```text
/home/blackvoid/Documents
```

---

## Relative Path

Starts from the current directory.

Example

```text
Documents/Notes
```

---

# Commands Practiced

| Command | Purpose | Practiced |
|----------|----------|-----------|
| pwd | Print working directory | ✅ |
| ls | List files | ✅ |
| cd | Change directory | ✅ |
| tree | Display directory tree | ⬜ |
| find | Search for files | ⬜ |
| locate | Locate files | ⬜ |

---

# Examples

Example 1

```bash
cd /etc
pwd
```

Output

```text
/etc
```

---

Example 2

```bash
cd ~
ls -la
```

Notes

Explain what happened.

---

# Common Mistakes

- Forgetting the leading `/` in absolute paths.
- Confusing `/` with `/root`.
- Using `rm` in the wrong directory.
- Forgetting hidden files start with `.`

---

# Tips & Best Practices

- Always run `pwd` if you're unsure where you are.
- Use `ls -la` frequently.
- Learn important directories by memory.
- Never run commands as root unless necessary.

---

# My Personal Notes

Write anything you discovered while practicing.

Example:

- `/proc` is not a real folder.
- `cd -` switches to the previous directory.
- Hidden files begin with a period (`.`).

---

# Mini Challenge

Complete these without looking up the answers.

- [ ] Navigate to your home directory.
- [ ] Go to `/etc`.
- [ ] Return to your previous directory.
- [ ] List all hidden files.
- [ ] Find the current directory.
- [ ] Navigate to the root directory.

---

# Cheat Sheet

| Command | Description |
|----------|-------------|
| `pwd` | Current directory |
| `ls` | List files |
| `ls -la` | Show hidden files |
| `cd` | Change directory |
| `cd ..` | Up one directory |
| `cd ~` | Home directory |
| `cd -` | Previous directory |
| `tree` | Directory tree |
| `find` | Search files |
| `locate` | Locate files |

---

# Knowledge Check

Can I answer these?

- [ ] What is the root directory?
- [ ] What is `/etc` used for?
- [ ] Difference between `/` and `/root`?
- [ ] Difference between absolute and relative paths?
- [ ] Where are user files stored?

---

# Resources

- Linux Manual Pages
- `man pwd`
- `man ls`
- `man cd`
- Linux Documentation Project

---

# Revision Log

| Date | What I Learned |
|------|----------------|
| YYYY-MM-DD | Started learning Linux File System |
| YYYY-MM-DD | Learned directory hierarchy |
| YYYY-MM-DD | Practiced navigation |

---

# Completion Status

- [ ] Read
- [ ] Practiced
- [ ] Understood
- [ ] Reviewed
- [ ] Can Explain to Someone Else
