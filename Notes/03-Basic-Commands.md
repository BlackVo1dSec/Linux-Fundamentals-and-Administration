# 03 - Basic Linux Commands

> **Module:** Linux Fundamentals & Administration
> **Status:** 🟡 In Progress
> **Difficulty:** Beginner
> **Last Updated:** YYYY-MM-DD

---

# Learning Objectives

By the end of this chapter I should be able to:

- [ ] Navigate the Linux file system.
- [ ] Manage files and directories.
- [ ] View file contents.
- [ ] Search for files.
- [ ] Use command options effectively.
- [ ] Read command documentation.

---

# Topic Overview

Write a brief explanation of what this chapter covers.

Example:

Basic Linux commands are the foundation of working in a Linux terminal. Learning them allows you to navigate the system, manage files, inspect information, and perform everyday administrative tasks efficiently.

---

# Command Categories

## Navigation

- pwd
- ls
- cd

## File Management

- touch
- cp
- mv
- rm

## Directory Management

- mkdir
- rmdir

## Viewing Files

- cat
- less
- more
- head
- tail

## Searching

- find
- locate
- which
- whereis

## System Information

- whoami
- hostname
- uname
- date
- uptime

## Help

- man
- --help
- info

---

# Command Template

> Copy this section for every command you learn.

---

# Command: pwd

## Purpose

Displays the current working directory.

---

## Syntax

```bash
pwd
```

---

## Common Options

| Option | Description |
|---------|-------------|
| None | Displays the current directory |

---

## Example

```bash
pwd
```

Example Output

```text
/home/blackvoid
```

---

## Explanation

Returns the full path of your current location.

---

## When to Use

- Before creating files
- Before deleting files
- When unsure where you are

---

## Notes

- One of the safest commands.
- Useful in shell scripts.

---

## Related Commands

- cd
- ls

---

# Commands Learned

| Command | Purpose | Confidence |
|----------|----------|------------|
| pwd | Show current directory | ⭐⭐⭐⭐⭐ |
| ls | List directory contents | ⭐⭐⭐⭐☆ |
| cd | Change directory | ⭐⭐⭐⭐☆ |
| mkdir | Create directory | ⭐⭐⭐☆☆ |
| touch | Create file | ⭐⭐⭐☆☆ |
| cp | Copy files | ⭐⭐☆☆☆ |
| mv | Move or rename files | ⭐⭐☆☆☆ |
| rm | Delete files | ⭐⭐☆☆☆ |

---

# Frequently Used Options

| Option | Meaning |
|----------|----------|
| -a | Show hidden files |
| -l | Long listing |
| -h | Human-readable sizes |
| -r | Recursive |
| -f | Force |
| -i | Interactive |
| -v | Verbose |

---

# Terminal Practice

## Exercise 1

Create a directory.

```bash
mkdir Practice
```

Result

```
____________________________________________________
```

---

## Exercise 2

Create a file.

```bash
touch notes.txt
```

Result

```
____________________________________________________
```

---

## Exercise 3

Rename the file.

```bash
mv notes.txt linux.txt
```

Result

```
____________________________________________________
```

---

## Exercise 4

Copy the file.

```bash
cp linux.txt backup.txt
```

Result

```
____________________________________________________
```

---

## Exercise 5

Delete the backup.

```bash
rm backup.txt
```

Result

```
____________________________________________________
```

---

# Real-World Examples

## Example 1

Create a project folder.

```bash
mkdir Linux-Lab
cd Linux-Lab
touch README.md
```

---

## Example 2

Create multiple files.

```bash
touch file1.txt file2.txt file3.txt
```

---

## Example 3

List detailed information.

```bash
ls -lah
```

---

## Example 4

Search for a file.

```bash
find . -name "*.md"
```

---

# Common Mistakes

- Running `rm` without checking the directory.
- Forgetting quotes around filenames with spaces.
- Using `cp` instead of `mv`.
- Accidentally deleting the wrong file.
- Forgetting hidden files with `ls`.

---

# Best Practices

- Always use `pwd` before deleting files.
- Use `ls -lah` frequently.
- Start with `rm -i` instead of `rm`.
- Read the manual page for unfamiliar commands.
- Practice commands in a test directory.

---

# My Notes

Write anything useful you discover while practicing.

Example

- `cp -r` copies entire directories.
- `mv` can rename files.
- `touch` updates timestamps.

---

# Command Cheat Sheet

| Command | Description |
|----------|-------------|
| pwd | Current directory |
| ls | List files |
| ls -la | Show hidden files |
| cd | Change directory |
| mkdir | Create directory |
| rmdir | Remove empty directory |
| touch | Create file |
| cp | Copy files |
| mv | Move or rename |
| rm | Delete |
| cat | Display file |
| less | Scroll file |
| head | First lines |
| tail | Last lines |
| find | Search |
| locate | Locate files |
| which | Command location |
| whereis | Command information |
| man | Manual page |

---

# Mini Challenges

## Beginner

- [ ] Create a folder.
- [ ] Create three files.
- [ ] Rename one file.
- [ ] Copy one file.
- [ ] Delete one file.

---

## Intermediate

- [ ] Find every Markdown file.
- [ ] Display the first 10 lines of a file.
- [ ] Display the last 20 lines of a log.
- [ ] Copy an entire directory.

---

## Advanced

- [ ] Build a directory tree from the terminal.
- [ ] Use only terminal commands to organize a project.
- [ ] Locate a command using `which`.
- [ ] Read the manual for `find`.

---

# Knowledge Check

Can I answer these questions?

- [ ] What is the difference between `cp` and `mv`?
- [ ] What does `pwd` display?
- [ ] How do I list hidden files?
- [ ] What command deletes directories?
- [ ] How do I search for a file?
- [ ] How do I display a file without editing it?

---

# Revision Log

| Date | Progress |
|------|----------|
| YYYY-MM-DD | Started learning Linux commands |
| YYYY-MM-DD | Practiced navigation |
| YYYY-MM-DD | Learned file management |
| YYYY-MM-DD | Learned searching |

---

# Completion Checklist

- [ ] Read the chapter
- [ ] Practiced every command
- [ ] Understood every option
- [ ] Completed exercises
- [ ] Completed challenges
- [ ] Reviewed notes
- [ ] Confident using commands without reference
