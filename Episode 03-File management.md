# Episode 03 - File Management & Manipulation

## Overview

In this episode, I learned the basic Linux commands used to navigate the filesystem and manage files and directories. These commands form the foundation of working with Linux from the command line.

---

# Learning Objectives

- Navigate the Linux filesystem
- Create, view, edit, move, and delete files
- Create and remove directories
- Understand file listings and hidden files
- Practice basic terminal-based file management

---

# Commands Learned

## 1. `pwd` (Print Working Directory)

Displays the current directory.

### Syntax

```bash
pwd
```

### Example

```bash
pwd
```

**Output**

```text
/home/kali/Documents
```

---

## 2. `ls` (List Files)

Lists files and directories.

### Syntax

```bash
ls
```

---

## 3. `ls -l`

Displays files in long listing format.

### Example

```bash
ls -l
```

Shows:

- Permissions
- Owner
- Group
- File size
- Modification date
- File name

---

## 4. `ls -a`

Displays all files, including hidden files.

```bash
ls -a
```

Hidden files begin with a `.`

Example:

```text
.bashrc
.profile
.git
```

---

## 5. `ls -al`

Combines long listing and hidden files.

```bash
ls -al
```

---

## 6. `ls -alh`

Displays files in a human-readable format.

```bash
ls -alh
```

Example:

```text
2K
15M
1.4G
```

instead of

```text
2048
15728640
1503238553
```

---

## 7. `cd` (Change Directory)

Moves between directories.

### Enter a directory

```bash
cd Documents
```

### Go back one directory

```bash
cd ..
```

### Go to the home directory

```bash
cd ~
```

---

## 8. `cat`

Displays the contents of a file.

```bash
cat file.txt
```

It can also create a file:

```bash
cat > notes.txt
```

Press **Ctrl + D** to save.

---

## 9. `touch`

Creates an empty file.

```bash
touch notes.txt
```

Multiple files:

```bash
touch file1.txt file2.txt file3.txt
```

---

## 10. `nano`

Simple terminal text editor.

```bash
nano notes.txt
```

Useful shortcuts:

- `Ctrl + O` → Save
- `Ctrl + X` → Exit

---

## 11. `vi`

Advanced terminal text editor.

```bash
vi notes.txt
```

Basic workflow:

- Press `i` → Insert mode
- Press `Esc`
- Type `:wq` → Save & Exit
- Type `:q!` → Exit without saving

---

## 12. `mkdir`

Creates a directory.

```bash
mkdir Projects
```

Create multiple directories:

```bash
mkdir Linux Cybersecurity Splunk
```

---

## 13. `rmdir`

Removes an empty directory.

```bash
rmdir Projects
```

---

## 14. `rm`

Deletes files.

```bash
rm notes.txt
```

Delete multiple files:

```bash
rm file1.txt file2.txt
```

Delete a directory and its contents:

```bash
rm -r folder
```

> ⚠️ Be careful with `rm`. Deleted files cannot be recovered easily.

---

## 15. `mv`

Moves or renames files.

### Rename a file

```bash
mv notes.txt linux_notes.txt
```

### Move a file

```bash
mv notes.txt Documents/
```

---

# Common Workflow Example

```bash
mkdir Linux
cd Linux

touch notes.txt

nano notes.txt

cat notes.txt

mkdir Commands

mv notes.txt Commands/

ls -al

cd Commands

pwd
```

---

# Key Takeaways

- Linux file management is performed through terminal commands.
- Navigation starts with `pwd`, `ls`, and `cd`.
- Files can be created using `touch` or `cat`.
- `nano` is beginner-friendly, while `vi` is a powerful editor used by many Linux administrators.
- Always verify your current directory before deleting files.
- Use `rm` carefully because it permanently removes files.

---

# Commands Summary

| Command | Purpose |
|----------|---------|
| `pwd` | Show current directory |
| `ls` | List files |
| `ls -l` | Long file listing |
| `ls -a` | Show hidden files |
| `ls -al` | Long listing including hidden files |
| `ls -alh` | Human-readable file sizes |
| `cd` | Change directory |
| `cd ..` | Move to parent directory |
| `cd ~` | Go to home directory |
| `cat` | View or create file |
| `touch` | Create empty file |
| `nano` | Edit file |
| `vi` | Advanced text editor |
| `mkdir` | Create directory |
| `rmdir` | Remove empty directory |
| `rm` | Delete file |
| `mv` | Move or rename file |

---

# Hands-on Practice

- [x] Navigated between directories
- [x] Listed files using different `ls` options
- [x] Created files using `touch`
- [x] Created directories using `mkdir`
- [x] Edited files with `nano`
- [x] Viewed file contents with `cat`
- [x] Renamed files using `mv`
- [x] Removed files using `rm`
- [x] Removed empty directories using `rmdir`

---

# Next Episode

- File permissions and ownership (or the next topic in the playlist)
