# 05 - File Permissions

> **Module:** Linux Fundamentals & Administration
> **Status:** 🟡 In Progress
> **Difficulty:** Beginner → Intermediate
> **Last Updated:** YYYY-MM-DD

---

# Learning Objectives

By the end of this chapter I should be able to:

- [ ] Explain Linux file permissions.
- [ ] Interpret symbolic permission strings.
- [ ] Understand octal (numeric) permissions.
- [ ] Change permissions using `chmod`.
- [ ] Change ownership using `chown`.
- [ ] Change group ownership using `chgrp`.
- [ ] Understand the purpose of `umask`.
- [ ] Apply permissions following the principle of least privilege.

---

# Topic Overview

Write a short summary of what this topic covers.

Example:

Linux file permissions determine who can read, write, or execute files and directories. Every file has an owner, an associated group, and permissions that control access for the owner, group members, and everyone else.

---

# Key Concepts

## File Owner

### Definition

The user who owns the file or directory.

### Notes

- Usually the creator of the file.
- Can change permissions if authorized.

---

## Group Owner

### Definition

The group associated with a file.

### Notes

- Members of the group may receive different permissions than other users.

---

## Others

### Definition

Anyone who is not the owner or a member of the file's group.

---

## Permission Types

| Permission | Symbol | Value | Meaning |
|------------|--------|------:|---------|
| Read | `r` | 4 | View file contents or list a directory |
| Write | `w` | 2 | Modify a file or create/delete items in a directory (with appropriate permissions) |
| Execute | `x` | 1 | Run a file or access/traverse a directory |

---

# Permission Structure

Example output:

```bash
-rwxr-xr--
```

Breakdown:

| Section | Meaning |
|---------|---------|
| `-` | File type (`d` = directory, `-` = file, `l` = symbolic link) |
| `rwx` | Owner permissions |
| `r-x` | Group permissions |
| `r--` | Others permissions |

---

# Numeric (Octal) Permissions

| Number | Binary | Symbolic |
|--------:|--------|----------|
| 0 | 000 | `---` |
| 1 | 001 | `--x` |
| 2 | 010 | `-w-` |
| 3 | 011 | `-wx` |
| 4 | 100 | `r--` |
| 5 | 101 | `r-x` |
| 6 | 110 | `rw-` |
| 7 | 111 | `rwx` |

---

# Common Permission Values

| Numeric | Symbolic | Typical Use |
|----------|----------|-------------|
| 777 | `rwxrwxrwx` | Rarely appropriate; everyone has full access |
| 755 | `rwxr-xr-x` | Executable files and many directories |
| 750 | `rwxr-x---` | Private shared directories |
| 700 | `rwx------` | Private scripts or directories |
| 644 | `rw-r--r--` | Standard text/configuration files |
| 640 | `rw-r-----` | Sensitive files shared within a group |
| 600 | `rw-------` | Private files (e.g., SSH keys) |
| 400 | `r--------` | Read-only for the owner |

---

# Commands Learned

## ls -l

### Purpose

Display detailed file information including permissions.

```bash
ls -l
```

Example Output

```text
-rw-r--r-- 1 blackvoid users 1024 Jul 16 notes.txt
```

Notes

-

---

## chmod

### Purpose

Change file or directory permissions.

#### Symbolic Mode

```bash
chmod u+x script.sh
```

#### Numeric Mode

```bash
chmod 755 script.sh
```

Notes

-

---

## chown

### Purpose

Change file ownership.

```bash
sudo chown alice notes.txt
```

```bash
sudo chown alice:developers project/
```

Notes

-

---

## chgrp

### Purpose

Change the group owner.

```bash
sudo chgrp developers notes.txt
```

Notes

-

---

## umask

### Purpose

Display or set the default permissions for newly created files and directories.

```bash
umask
```

Example Output

```text
0022
```

Notes

-

---

# Symbolic chmod Examples

| Command | Meaning |
|---------|---------|
| `chmod u+x file` | Add execute permission for the owner |
| `chmod g+w file` | Add write permission for the group |
| `chmod o-r file` | Remove read permission from others |
| `chmod a+r file` | Give everyone read permission |
| `chmod u=rw file` | Set owner permissions exactly to read/write |

---

# Practical Exercises

## Exercise 1

View permissions.

```bash
ls -l
```

Observations

```
_____________________________________
```

---

## Exercise 2

Create a file.

```bash
touch test.txt
```

Check its permissions.

```bash
ls -l test.txt
```

Result

```
_____________________________________
```

---

## Exercise 3

Make a script executable.

```bash
chmod +x script.sh
```

Verify

```bash
ls -l script.sh
```

Result

```
_____________________________________
```

---

## Exercise 4

Use numeric permissions.

```bash
chmod 644 notes.txt
```

Result

```
_____________________________________
```

---

## Exercise 5

Check your umask.

```bash
umask
```

Result

```
_____________________________________
```

---

# Real-World Examples

## Secure an SSH Private Key

```bash
chmod 600 ~/.ssh/id_ed25519
```

---

## Make a Script Executable

```bash
chmod 755 backup.sh
```

---

## Share a Project Directory with a Team

```bash
sudo chown alice:developers project
chmod 770 project
```

---

## View File Ownership

```bash
ls -l
```

---

# Common Mistakes

- Using `chmod 777` without understanding the security implications.
- Forgetting that directories require execute (`x`) permission to be traversed.
- Running `chmod -R` in the wrong directory.
- Confusing ownership with permissions.
- Forgetting to verify changes with `ls -l`.

---

# Best Practices

- Follow the **Principle of Least Privilege**.
- Use groups instead of granting permissions to everyone.
- Verify permission changes after modifying them.
- Avoid world-writable files unless absolutely necessary.
- Keep private files restricted to the owner.

---

# My Notes

Write observations from your labs.

Example

- `755` is common for executable scripts.
- `644` is common for regular files.
- SSH private keys require restrictive permissions such as `600`.

---

# Cheat Sheet

| Command | Purpose |
|----------|---------|
| `ls -l` | View permissions |
| `chmod` | Change permissions |
| `chown` | Change owner |
| `chgrp` | Change group |
| `umask` | View or set default permissions |

---

# Knowledge Check

Can I answer these?

- [ ] What do `r`, `w`, and `x` represent?
- [ ] What do the owner, group, and others permission sets mean?
- [ ] What does `chmod 755` do?
- [ ] What is the difference between symbolic and numeric permissions?
- [ ] What is the purpose of `umask`?
- [ ] Why is `chmod 777` usually discouraged?
- [ ] How do you change a file's owner?
- [ ] How do you make a script executable?

---

# Lab Challenges

## Beginner

- [ ] Create a file.
- [ ] View its permissions.
- [ ] Change it to `644`.
- [ ] Change it to `600`.

---

## Intermediate

- [ ] Create a script.
- [ ] Make it executable.
- [ ] Change the owner (if you have the required privileges).
- [ ] Change the group owner.

---

## Advanced

- [ ] Build a shared project directory with appropriate group permissions.
- [ ] Experiment with different `umask` values and record the default permissions for new files and directories.
- [ ] Compare symbolic and numeric `chmod` by performing the same permission changes using both methods.

---

# Revision Log

| Date | What I Learned |
|------|----------------|
| YYYY-MM-DD | Learned Linux permissions |
| YYYY-MM-DD | Practiced `chmod` |
| YYYY-MM-DD | Practiced ownership changes |
| YYYY-MM-DD | Learned about `umask` |

---

# Completion Checklist

- [ ] Read the chapter
- [ ] Practiced every command
- [ ] Understand symbolic permissions
- [ ] Understand numeric permissions
- [ ] Completed all exercises
- [ ] Completed all lab challenges
- [ ] Can explain Linux permissions without notes
