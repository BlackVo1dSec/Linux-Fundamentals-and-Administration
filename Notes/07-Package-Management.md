# 07 - Package Management

> **Module:** Linux Fundamentals & Administration
> **Status:** 🟡 In Progress
> **Difficulty:** Beginner → Intermediate
> **Last Updated:** YYYY-MM-DD

---

# Learning Objectives

By the end of this chapter I should be able to:

- [ ] Explain what a package manager is.
- [ ] Understand software repositories.
- [ ] Install, update, upgrade, and remove packages.
- [ ] Search for software packages.
- [ ] View installed packages.
- [ ] Understand package dependencies.
- [ ] Troubleshoot common package management issues.

---

# Topic Overview

Write a brief summary of what this chapter covers.

Example:

Package managers simplify installing, updating, removing, and maintaining software. Instead of downloading applications manually, Linux retrieves software from trusted repositories while automatically handling dependencies.

---

# Key Concepts

## Package

### Definition

A bundled collection of software files and metadata used to install an application.

### Notes

-

---

## Package Manager

### Definition

Software that installs, updates, removes, and manages packages.

### Examples

- APT (Debian/Ubuntu/Kali)
- DNF (Fedora)
- YUM (Older RHEL/CentOS)
- Pacman (Arch Linux)
- Zypper (openSUSE)

---

## Repository

### Definition

An online or local source that stores software packages.

### Notes

-

---

## Dependency

### Definition

Software required by another application to function correctly.

### Notes

-

---

## Package Cache

### Definition

Locally stored package information used by the package manager.

---

# Package Management Workflow

```text
Update Package Lists
        │
        ▼
Search for Package
        │
        ▼
Install Package
        │
        ▼
Verify Installation
        │
        ▼
Update & Maintain
        │
        ▼
Remove When No Longer Needed
```

---

# Common Package Managers

| Distribution | Package Manager | Package Format |
|--------------|-----------------|----------------|
| Debian | APT | `.deb` |
| Ubuntu | APT | `.deb` |
| Kali Linux | APT | `.deb` |
| Fedora | DNF | `.rpm` |
| RHEL | DNF | `.rpm` |
| Arch Linux | Pacman | `.pkg.tar.zst` |
| openSUSE | Zypper | `.rpm` |

---

# Commands Learned

## apt update

### Purpose

Update the local package index.

```bash
sudo apt update
```

Notes

-

---

## apt upgrade

### Purpose

Upgrade installed packages.

```bash
sudo apt upgrade
```

Notes

-

---

## apt install

### Purpose

Install a package.

```bash
sudo apt install package-name
```

Example

```bash
sudo apt install tree
```

Notes

-

---

## apt remove

### Purpose

Remove a package while keeping configuration files.

```bash
sudo apt remove package-name
```

Notes

-

---

## apt purge

### Purpose

Remove a package and its configuration files.

```bash
sudo apt purge package-name
```

Notes

-

---

## apt autoremove

### Purpose

Remove unnecessary dependencies.

```bash
sudo apt autoremove
```

Notes

-

---

## apt search

### Purpose

Search for available packages.

```bash
apt search package-name
```

Notes

-

---

## apt show

### Purpose

Display package information.

```bash
apt show package-name
```

Notes

-

---

## dpkg -l

### Purpose

List installed packages.

```bash
dpkg -l
```

Notes

-

---

## dpkg -i

### Purpose

Install a local `.deb` package.

```bash
sudo dpkg -i package.deb
```

Notes

-

---

# Common Command Options

| Option | Description |
|---------|-------------|
| `-y` | Automatically answer "yes" to prompts |
| `--fix-broken` | Attempt to fix broken dependencies |
| `-f install` | Fix dependency issues (with `apt`) |
| `-i` | Install a local package (`dpkg`) |
| `-l` | List installed packages (`dpkg`) |

---

# Practical Exercises

## Exercise 1

Update package lists.

```bash
sudo apt update
```

Observations

```
_____________________________________
```

---

## Exercise 2

Upgrade installed packages.

```bash
sudo apt upgrade
```

Observations

```
_____________________________________
```

---

## Exercise 3

Search for a package.

```bash
apt search tree
```

Result

```
_____________________________________
```

---

## Exercise 4

Install a package.

```bash
sudo apt install tree
```

Verify

```bash
tree --version
```

Result

```
_____________________________________
```

---

## Exercise 5

Display package information.

```bash
apt show tree
```

Notes

```
_____________________________________
```

---

## Exercise 6

Remove the package.

```bash
sudo apt remove tree
```

Result

```
_____________________________________
```

---

## Exercise 7

Remove unused dependencies.

```bash
sudo apt autoremove
```

Observations

```
_____________________________________
```

---

# Real-World Examples

## Install Git

```bash
sudo apt update
sudo apt install git
```

---

## Install HTOP

```bash
sudo apt install htop
```

---

## Search for OpenSSH

```bash
apt search openssh
```

---

## Install a Local Package

```bash
sudo dpkg -i application.deb
sudo apt --fix-broken install
```

---

# Common Mistakes

- Installing software without updating package lists first.
- Interrupting package installation.
- Forgetting `sudo` when administrative privileges are required.
- Ignoring dependency errors.
- Removing critical system packages without understanding their purpose.

---

# Best Practices

- Run `sudo apt update` before installing new software.
- Keep your system up to date with regular upgrades.
- Install software from trusted repositories whenever possible.
- Review package details before installation.
- Remove unused packages to keep the system clean.

---

# My Notes

Write observations from your labs.

Example

- `apt update` refreshes package information but does not install updates.
- `apt upgrade` installs available updates.
- `apt autoremove` helps remove unnecessary dependencies.

---

# Troubleshooting Notes

| Issue | Cause | Solution |
|-------|-------|----------|
| Package not found | Repository information outdated | Run `sudo apt update` |
| Broken dependencies | Incomplete installation | `sudo apt --fix-broken install` |
| Permission denied | Missing administrative privileges | Use `sudo` if appropriate |

---

# Cheat Sheet

| Command | Purpose |
|----------|---------|
| `apt update` | Refresh package lists |
| `apt upgrade` | Upgrade installed packages |
| `apt install` | Install a package |
| `apt remove` | Remove a package |
| `apt purge` | Remove package and configuration |
| `apt autoremove` | Remove unused dependencies |
| `apt search` | Search repositories |
| `apt show` | View package details |
| `dpkg -l` | List installed packages |
| `dpkg -i` | Install a local `.deb` package |

---

# Knowledge Check

Can I answer these?

- [ ] What is a package manager?
- [ ] What is a software repository?
- [ ] What is a dependency?
- [ ] What is the difference between `apt update` and `apt upgrade`?
- [ ] When would you use `apt purge` instead of `apt remove`?
- [ ] What does `apt autoremove` do?
- [ ] How do you install a local `.deb` package?
- [ ] How do you list installed packages?

---

# Lab Challenges

## Beginner

- [ ] Update package lists.
- [ ] Search for a package.
- [ ] Install a package.
- [ ] Verify the installation.

---

## Intermediate

- [ ] Install three useful administration tools.
- [ ] View package information.
- [ ] Remove a package.
- [ ] Clean unused dependencies.

---

## Advanced

- [ ] Install a local `.deb` package.
- [ ] Resolve a dependency issue.
- [ ] Compare APT with another Linux package manager.
- [ ] Explain the package management workflow from memory.

---

# Revision Log

| Date | What I Learned |
|------|----------------|
| YYYY-MM-DD | Learned package management basics |
| YYYY-MM-DD | Installed software with APT |
| YYYY-MM-DD | Removed software and dependencies |
| YYYY-MM-DD | Practiced package troubleshooting |

---

# Completion Checklist

- [ ] Read the chapter
- [ ] Practiced every command
- [ ] Understand repositories
- [ ] Understand dependencies
- [ ] Completed all exercises
- [ ] Completed all lab challenges
- [ ] Can manage software confidently without notes
