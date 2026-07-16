# 06 - Processes and Services

> **Module:** Linux Fundamentals & Administration
> **Status:** 🟡 In Progress
> **Difficulty:** Beginner → Intermediate
> **Last Updated:** YYYY-MM-DD

---

# Learning Objectives

By the end of this chapter I should be able to:

- [ ] Explain what a process is.
- [ ] Identify running processes.
- [ ] Monitor system resources.
- [ ] Understand foreground and background processes.
- [ ] Manage jobs.
- [ ] Terminate processes safely.
- [ ] Understand Linux services (daemons).
- [ ] Manage services using `systemctl`.

---

# Topic Overview

Write a brief summary of what this chapter covers.

Example:

A process is an instance of a running program. Linux provides powerful tools to monitor, manage, and troubleshoot processes. Many applications run as background services (daemons), which are managed by the operating system.

---

# Key Concepts

## Process

### Definition

A running instance of a program.

### Notes

-

---

## Process ID (PID)

### Definition

A unique number assigned to every running process.

### Notes

-

---

## Parent Process (PPID)

### Definition

The process that started another process.

### Notes

-

---

## Foreground Process

### Definition

Runs in the active terminal and receives keyboard input.

---

## Background Process

### Definition

Runs without occupying the terminal.

---

## Daemon (Service)

### Definition

A background process that provides system or application functionality.

Examples

- SSH
- Cron
- Networking
- Web servers

---

## Signals

### Definition

Messages sent to processes to control their behavior.

Common signals

| Signal | Number | Purpose |
|---------|--------|---------|
| SIGTERM | 15 | Gracefully terminate |
| SIGKILL | 9 | Force terminate |
| SIGINT | 2 | Interrupt (Ctrl+C) |
| SIGHUP | 1 | Reload configuration |

---

# Process Lifecycle

```text
Program
    │
    ▼
Process Created
    │
    ▼
Running
    │
    ├──────────────┐
    ▼              ▼
Sleeping       Waiting
    │              │
    └──────┬───────┘
           ▼
      Terminated
```

---

# Commands Learned

## ps

### Purpose

Display running processes.

```bash
ps
```

Useful Options

```bash
ps aux
ps -ef
```

Notes

-

---

## top

### Purpose

Display live system activity.

```bash
top
```

Notes

-

---

## htop

### Purpose

Interactive process viewer.

```bash
htop
```

Notes

-

---

## jobs

### Purpose

View background jobs in the current shell.

```bash
jobs
```

Notes

-

---

## bg

### Purpose

Resume a job in the background.

```bash
bg
```

---

## fg

### Purpose

Bring a background job to the foreground.

```bash
fg
```

---

## kill

### Purpose

Terminate a process by PID.

```bash
kill PID
```

Example

```bash
kill 1234
```

---

## killall

### Purpose

Terminate all processes with a given name.

```bash
killall firefox
```

---

## pgrep

### Purpose

Find process IDs by name.

```bash
pgrep ssh
```

---

## pkill

### Purpose

Terminate processes by name.

```bash
pkill firefox
```

---

## systemctl

### Purpose

Manage system services.

Examples

```bash
systemctl status ssh
systemctl start ssh
systemctl stop ssh
systemctl restart ssh
systemctl enable ssh
systemctl disable ssh
```

Notes

-

---

# Common Command Options

| Option | Description |
|---------|-------------|
| `-e` | Every process |
| `-f` | Full output |
| `-u` | Filter by user |
| `-p` | Specify PID |
| `-9` | Send SIGKILL |
| `status` | Show service status |
| `restart` | Restart service |
| `enable` | Start service at boot |
| `disable` | Prevent service from starting at boot |

---

# Practical Exercises

## Exercise 1

Display running processes.

```bash
ps aux
```

Observations

```
_____________________________________
```

---

## Exercise 2

Monitor system activity.

```bash
top
```

Observations

```
_____________________________________
```

---

## Exercise 3

Start a background job.

```bash
sleep 300 &
```

Check jobs.

```bash
jobs
```

Result

```
_____________________________________
```

---

## Exercise 4

Bring the job back to the foreground.

```bash
fg
```

Observations

```
_____________________________________
```

---

## Exercise 5

Terminate the process.

```bash
kill PID
```

Replace `PID` with the process ID from your system.

Result

```
_____________________________________
```

---

## Exercise 6

Check a service.

```bash
systemctl status ssh
```

Observations

```
_____________________________________
```

---

# Real-World Examples

## Find a Running Process

```bash
pgrep ssh
```

---

## Restart a Service

```bash
sudo systemctl restart ssh
```

---

## View Memory Usage

```bash
top
```

---

## Stop a Hung Application

```bash
kill -15 PID
```

If it doesn't respond:

```bash
kill -9 PID
```

---

# Common Mistakes

- Using `kill -9` before trying `SIGTERM`.
- Killing the wrong process due to an incorrect PID.
- Forgetting to verify a service's status after restarting it.
- Running `pkill` or `killall` without confirming the target process.
- Assuming every Linux distribution uses `systemd`.

---

# Best Practices

- Use `SIGTERM` before `SIGKILL`.
- Verify the PID before terminating a process.
- Monitor resource usage regularly.
- Restart services only when necessary.
- Understand what a service does before stopping or disabling it.

---

# My Notes

Write anything you discovered while practicing.

Example

- `top` updates in real time.
- `Ctrl+C` sends `SIGINT`.
- `systemctl status` provides useful troubleshooting information.

---

# Cheat Sheet

| Command | Purpose |
|----------|---------|
| `ps` | View processes |
| `ps aux` | Detailed process list |
| `top` | Live process monitor |
| `htop` | Interactive process monitor |
| `jobs` | List shell jobs |
| `bg` | Resume job in background |
| `fg` | Bring job to foreground |
| `kill` | Terminate by PID |
| `killall` | Terminate by process name |
| `pgrep` | Find PID by process name |
| `pkill` | Kill by process name |
| `systemctl` | Manage services |

---

# Knowledge Check

Can I answer these?

- [ ] What is a process?
- [ ] What is a PID?
- [ ] What is the difference between a process and a service?
- [ ] What is the difference between a foreground and background process?
- [ ] What does `kill -9` do?
- [ ] Why should `SIGTERM` usually be used before `SIGKILL`?
- [ ] How do you view running processes?
- [ ] How do you restart a service?
- [ ] How do you enable a service at boot?

---

# Lab Challenges

## Beginner

- [ ] View all running processes.
- [ ] Find your shell's PID.
- [ ] Start a background job.
- [ ] Bring it back to the foreground.

---

## Intermediate

- [ ] Identify the top five memory-consuming processes.
- [ ] Restart a non-critical service.
- [ ] Find a process using `pgrep`.
- [ ] Gracefully terminate a process.

---

## Advanced

- [ ] Compare the output of `ps`, `top`, and `htop`.
- [ ] Record the status of multiple services.
- [ ] Explain the difference between `kill`, `killall`, and `pkill`.
- [ ] Practice managing jobs using `jobs`, `bg`, and `fg`.

---

# Revision Log

| Date | What I Learned |
|------|----------------|
| YYYY-MM-DD | Learned about Linux processes |
| YYYY-MM-DD | Practiced process monitoring |
| YYYY-MM-DD | Managed background jobs |
| YYYY-MM-DD | Managed services with `systemctl` |

---

# Completion Checklist

- [ ] Read the chapter
- [ ] Practiced every command
- [ ] Understand process management
- [ ] Understand services
- [ ] Completed all exercises
- [ ] Completed all lab challenges
- [ ] Can explain Linux process management without notes
