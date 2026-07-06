# Episode 05 - File & Directory Ownership

## Overview

In this episode, I learned how Linux manages file ownership. Every file and directory in Linux has an **owner**, belongs to a **group**, and has permissions for **others**. I also learned how to change ownership using the `chown` and `chgrp` commands.

---

# Learning Objectives

- Understand file ownership in Linux
- Differentiate between Owner, Group, and Others
- View ownership information
- Change file ownership
- Change group ownership
- Understand why ownership is important for Linux security

---

# Understanding File Ownership

Every file and directory in Linux belongs to:

1. **Owner (User)**
2. **Group**
3. **Others**

You can view ownership using:

```bash
ls -alh
```

Example:

```text
-rwxr-xr-- 1 kali developers 2.3K Jul 12 notes.txt
```

Breakdown:

```text
-rwxr-xr--
│
Permissions

1
│
Hard Links

kali
│
Owner

developers
│
Group

2.3K
│
File Size

notes.txt
│
File Name
```

---

# Owner (User)

The **owner** is the user who created the file (or the user to whom ownership has been assigned).

The owner has a separate set of permissions.

### Example

User:

```text
kali
```

File:

```text
notes.txt
```

Output:

```text
-rw-r--r-- 1 kali developers notes.txt
```

Here,

- **Owner = kali**

The owner can have different permissions than everyone else.

---

# Group

A **group** is a collection of users.

Instead of giving permissions to individual users one by one, Linux allows assigning permissions to a group.

Example:

Suppose there are three users:

```text
Alice
Bob
Charlie
```

All three belong to the group:

```text
developers
```

If a file belongs to the **developers** group:

```text
notes.txt
```

then every member of the **developers** group receives the group permissions assigned to that file.

---

# Others

Others refers to **everyone else** who is neither:

- the owner
- nor a member of the assigned group

Example:

Owner:

```text
kali
```

Group:

```text
developers
```

User:

```text
john
```

If **john** is **not** the owner and **not** a member of the **developers** group, then Linux applies the **Others** permissions when John accesses the file.

---

# Why is Ownership Important?

Ownership helps Linux control access to files securely.

For example:

- Only the owner may edit a personal document.
- Members of a team can collaborate through a shared group.
- Everyone else may have read-only or no access.

This prevents unauthorized users from modifying sensitive files.

---

# Viewing Ownership

Use:

```bash
ls -alh
```

Example:

```text
-rwxr-xr-- 1 kali developers report.txt
```

Owner:

```text
kali
```

Group:

```text
developers
```

---

# Changing Owner using chown

The `chown` command changes the owner of a file or directory.

### Syntax

```bash
sudo chown <new_owner> <file>
```

Example:

```bash
sudo chown john report.txt
```

Now,

Owner:

```text
john
```

---

# Change Owner and Group Together

```bash
sudo chown john:developers report.txt
```

Now,

Owner:

```text
john
```

Group:

```text
developers
```

---

# Changing Group using chgrp

The `chgrp` command changes only the group ownership.

### Syntax

```bash
sudo chgrp <group_name> <file>
```

Example:

```bash
sudo chgrp developers report.txt
```

Only the group changes.

The owner remains the same.

---

# Recursive Ownership

Change ownership for an entire directory:

```bash
sudo chown -R john Projects/
```

Change owner and group recursively:

```bash
sudo chown -R john:developers Projects/
```

Change group recursively:

```bash
sudo chgrp -R developers Projects/
```

> ⚠️ The `-R` option applies changes to all files and subdirectories.

---

# Example Scenario

Suppose we have:

```text
Owner : kali
Group : developers
File  : notes.txt
```

Permissions:

```text
-rw-r----- notes.txt
```

Meaning:

| User | Access |
|------|--------|
| Owner (`kali`) | Read & Write |
| Group (`developers`) | Read Only |
| Others | No Access |

Now run:

```bash
sudo chown john notes.txt
```

Result:

```text
Owner : john
Group : developers
```

Now **John** becomes the owner and receives the owner's permissions.

---

# Commands Learned

| Command | Purpose |
|----------|---------|
| `ls -alh` | View ownership and permissions |
| `chown` | Change file owner |
| `chown owner:group` | Change owner and group together |
| `chgrp` | Change group ownership |
| `chown -R` | Change ownership recursively |
| `chgrp -R` | Change group recursively |

---

# Key Takeaways

- Every Linux file has an owner, a group, and permissions for others.
- The owner is usually the user who created the file.
- Groups allow multiple users to share access efficiently.
- Others refers to users who are neither the owner nor members of the assigned group.
- `chown` changes the owner.
- `chgrp` changes the group.
- Recursive ownership changes should be used carefully.

---

# Hands-on Practice

- [x] Viewed file ownership using `ls -alh`
- [x] Changed file owner using `chown`
- [x] Changed group using `chgrp`
- [x] Changed both owner and group
- [x] Applied ownership changes recursively

---

# Next Episode

- User management, package management, or the next topic in the Linux Essentials playlist.
