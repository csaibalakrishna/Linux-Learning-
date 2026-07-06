# Episode 06 - Grep & Piping

## Overview

In this episode, I learned how to search for specific text using the `grep` command and how to combine multiple commands using pipes (`|`). These are two of the most powerful and frequently used features in Linux, especially in cybersecurity and system administration.

---

# Learning Objectives

- Understand what `grep` is and how it works
- Search for text inside files
- Use common `grep` options
- Understand Linux pipes (`|`)
- Combine commands to process data efficiently
- Learn why `grep` and piping are heavily used in cybersecurity

---

# What is grep?

`grep` stands for **Global Regular Expression Print**.

It searches for text or patterns inside files or command output.

Instead of manually reading hundreds or thousands of lines, `grep` quickly finds only the lines that match your search.

---

# Basic Syntax

```bash
grep "pattern" filename
```

Example:

```bash
grep "error" logs.txt
```

Output:

```text
[ERROR] Failed login
[ERROR] Connection refused
```

Only the matching lines are displayed.

---

# Common grep Examples

### Search for a word

```bash
grep "root" users.txt
```

---

### Ignore case

```bash
grep -i "linux" notes.txt
```

Matches:

```text
Linux
linux
LINUX
```

---

### Show line numbers

```bash
grep -n "error" logs.txt
```

Example:

```text
15: Error occurred
42: Another error
```

---

### Count matching lines

```bash
grep -c "failed" auth.log
```

Output:

```text
12
```

---

### Search recursively

```bash
grep -r "password" .
```

Searches every file in the current directory and its subdirectories.

---

### Invert the search

```bash
grep -v "success" logs.txt
```

Displays every line **except** those containing "success".

---

# What is a Pipe (`|`)?

A pipe (`|`) sends the output of one command as the input to another command.

Instead of saving data to a file, commands can work together directly.

General syntax:

```bash
command1 | command2
```

Think of it as a pipeline:

```text
Command 1
      │
      ▼
Output
      │
      ▼
Command 2
```

---

# Pipe Examples

### List files and search for `.txt`

```bash
ls | grep ".txt"
```

Example output:

```text
notes.txt
report.txt
todo.txt
```

---

### Search running processes

```bash
ps aux | grep firefox
```

Shows only Firefox-related processes.

---

### Find SSH services

```bash
systemctl list-units | grep ssh
```

---

### Find logged-in users

```bash
who | grep alice
```

---

### Search network connections

```bash
ss -tuln | grep 22
```

Shows services listening on port 22 (SSH).

---

# Why grep is Important in Cybersecurity

Cybersecurity professionals often deal with:

- Huge log files
- Thousands of running processes
- Network connections
- Authentication logs
- System events

Instead of manually reading everything, `grep` filters only the relevant information.

Example:

Authentication log:

```text
User john logged in
User alice failed login
User mike logged in
User alice failed login
```

Search only failed logins:

```bash
grep "failed" auth.log
```

Output:

```text
User alice failed login
User alice failed login
```

---

# Why Piping is Important in Cybersecurity

Pipes allow multiple commands to work together.

Example:

```bash
cat auth.log | grep "Failed"
```

The flow:

```text
auth.log
     │
     ▼
cat
     │
     ▼
grep
     │
     ▼
Only failed logins
```

Instead of opening the file and searching manually, Linux does it instantly.

---

# Real-World Cybersecurity Examples

### Find failed SSH logins

```bash
grep "Failed password" /var/log/auth.log
```

---

### Check if SSH is running

```bash
systemctl status ssh | grep Active
```

---

### Find suspicious processes

```bash
ps aux | grep python
```

---

### Search for a specific IP address

```bash
grep "192.168.1.10" access.log
```

---

### Find open SSH connections

```bash
ss -tuln | grep 22
```

---

# Commands Learned

| Command | Purpose |
|----------|---------|
| `grep` | Search for text or patterns |
| `grep -i` | Ignore letter case |
| `grep -n` | Show line numbers |
| `grep -c` | Count matching lines |
| `grep -v` | Show non-matching lines |
| `grep -r` | Search recursively |
| `|` | Pass output from one command to another |

---

# Key Takeaways

- `grep` is used to quickly search for text or patterns in files and command output.
- Pipes (`|`) connect commands, allowing them to work together efficiently.
- Combining `grep` with other Linux commands makes log analysis and troubleshooting much faster.
- Both `grep` and piping are essential skills for Linux administrators, SOC analysts, incident responders, and penetration testers.

---

# Hands-on Practice

- [x] Searched text inside files using `grep`
- [x] Ignored case using `grep -i`
- [x] Counted matching lines with `grep -c`
- [x] Displayed line numbers with `grep -n`
- [x] Combined commands using pipes (`|`)
- [x] Filtered running processes
- [x] Filtered network connections
- [x] Practiced searching log files

---

# Next Episode

- Package management, process management, or the next topic in the Linux Essentials playlist.
