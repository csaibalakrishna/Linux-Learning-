# Episode 04 - File & Directory Permissions

## Overview

In this episode, I learned how Linux controls access to files and directories using permissions. I explored how to view permissions, understand their meaning, and modify them using both symbolic and octal notation.

---

# Learning Objectives

- Understand Linux file permissions
- Differentiate between file and directory permissions
- View permissions using `ls -alh`
- Change permissions using `chmod`
- Learn symbolic and octal permission notation
- Apply permissions recursively

---

# Viewing File Permissions

To view file permissions, use:

```bash
ls -alh
```

### Example Output

```text
-rwxr-xr-- 1 kali kali 2.3K Jul 10 notes.txt
```

---

# Understanding Permission Format

Example:

```text
-rwxr-xr--
```

Breakdown:

```text
- rwx r-x r--
│ │   │   │
│ │   │   └── Others
│ │   └────── Group
│ └────────── Owner
└──────────── File Type
```

### File Type

| Symbol | Meaning |
|--------|---------|
| `-` | Regular file |
| `d` | Directory |
| `l` | Symbolic link |

---

# Permission Types

Each permission has a specific meaning.

| Symbol | Permission | Description |
|--------|------------|-------------|
| `r` | Read | View file contents |
| `w` | Write | Modify file contents |
| `x` | Execute | Run the file as a program |

---

# File Permissions

For files:

| Permission | Meaning |
|------------|---------|
| `r` | Read the file |
| `w` | Edit the file |
| `x` | Execute the file |

---

# Directory Permissions

Directory permissions behave differently.

| Permission | Meaning |
|------------|---------|
| `r` | View directory contents |
| `w` | Create, delete, or rename files in the directory |
| `x` | Enter (traverse) the directory |

---

# Changing Permissions with chmod

The `chmod` command changes file or directory permissions.

---

## Method 1: Symbolic Mode

### Add Execute Permission

```bash
chmod +x script.sh
```

### Remove Write Permission

```bash
chmod -w notes.txt
```

### Give Owner Read & Write

```bash
chmod u+rw file.txt
```

### Give Group Execute Permission

```bash
chmod g+x file.txt
```

### Remove Read Permission from Others

```bash
chmod o-r file.txt
```

### Apply Permission to Everyone

```bash
chmod a+r file.txt
```

---

## Symbol Reference

| Symbol | Meaning |
|--------|---------|
| `u` | User (Owner) |
| `g` | Group |
| `o` | Others |
| `a` | All users |

---

# Method 2: Octal (Numeric) Mode

Each permission has a numeric value.

| Permission | Value |
|------------|------:|
| Read (`r`) | 4 |
| Write (`w`) | 2 |
| Execute (`x`) | 1 |

Add the values together to form a permission.

| Permission | Binary | Octal |
|------------|--------|------:|
| `rwx` | 111 | 7 |
| `rw-` | 110 | 6 |
| `r-x` | 101 | 5 |
| `r--` | 100 | 4 |
| `---` | 000 | 0 |

### Examples

Give the owner full access, group read & execute, others read only:

```bash
chmod 754 file.txt
```

Owner can read/write, group can read only, others can read only:

```bash
chmod 644 file.txt
```

Owner has full access, everyone else can read and execute:

```bash
chmod 755 script.sh
```

---

# Recursive Permissions

The `-R` option applies permissions to a directory and everything inside it.

```bash
chmod -R 755 Projects/
```

Example:

```bash
chmod -R u+rwx Linux/
```

> ⚠️ Be cautious when using `-R`, as it modifies all files and subdirectories recursively.

---

# Common Permission Values

| Octal | Meaning |
|------:|---------|
| `777` | Everyone has full access (Not recommended) |
| `755` | Owner full access, others read & execute |
| `700` | Owner only |
| `644` | Owner read/write, others read only |
| `600` | Owner read/write only |

---

# Commands Learned

| Command | Purpose |
|---------|---------|
| `ls -alh` | View detailed file permissions |
| `chmod` | Change file permissions |
| `chmod +x` | Make a file executable |
| `chmod 755` | Set permissions using octal notation |
| `chmod -R` | Apply permissions recursively |

---

# Key Takeaways

- Linux permissions control access to files and directories.
- Permissions are assigned separately to the owner, group, and others.
- `chmod` can modify permissions using symbolic or numeric notation.
- Numeric (octal) notation is commonly used in system administration and scripting.
- Recursive permission changes (`-R`) should be used carefully to avoid unintended modifications.

---

# Hands-on Practice

- [x] Viewed file permissions using `ls -alh`
- [x] Changed permissions using symbolic notation
- [x] Changed permissions using octal notation
- [x] Made a file executable
- [x] Applied recursive permissions using `chmod -R`

---

# Next Episode

- Users, groups, or the next topic in the Linux Essentials playlist.
